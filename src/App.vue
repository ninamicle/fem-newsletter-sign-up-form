<template>
  <keep-alive>
    <component :is="activeComponent" :contents="contents" :email="email" @submitForm="setUserEmail"  @backToForm="removeUserEmail"/>
  </keep-alive>
</template>

<script setup>
import NewsletterSignUpForm from "./components/NewsletterSignUpForm.vue";
import UserFeedback from "./components/UserFeedback.vue";
import {ref, shallowRef} from 'vue'

const email = ref('');
const activeComponent = shallowRef(NewsletterSignUpForm);

const setUserEmail = (data) => {
  if(data){
    email.value = data;
    activeComponent.value = UserFeedback;
  }
}
const removeUserEmail = (data) => {
  if(!data) {
    email.value = '';
    activeComponent.value = NewsletterSignUpForm;
  }
}
const contents = [
  { id: 1, text: 'Product discovery and building what matters' },
  { id: 2, text: 'Measuring to ensure updates are a success' },
  { id: 3, text: 'And much more!' }
];

</script>

