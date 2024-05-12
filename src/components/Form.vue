<template>
  <form @submit.prevent="handleSubmit" class="flex flex-col gap-y-4">
    <div class="flex flex-col">
      <div class="flex justify-between font-bold py-2">
        <label class="" for="email">Email address</label>
        <div v-if="msg.validation" class="text-tomato">{{msg.validation}}</div>
      </div>
      <input class="border border-grey rounded-lg h-12 placeholder:px-6 hover:cursor-pointer  px-6"
             :class="[msg.validation ? 'bg-red-200 border border-tomato text-tomato px-6': '']"
             required
             v-model="email" type="email" id="email"
             placeholder="email@company.com"
             @blur="validateEmail"/>
    </div>
    <Button :label="'Subscribe to monthly newsletter'" :type="'submit'"/>
  </form>
</template>

<script setup>
import {ref} from "vue";
import Button from "./Button.vue";

const emits = defineEmits(['submitForm']);
const email = ref('');
const msg = ref({validation: ""});
const handleSubmit = (event)=>{
  if(event)emits('submitForm', email)
  email.value = '';
  msg.value.validation = '';
}
const validateEmail =()=> {
  const regex = /^[a-zA-Z0–9._-]+@[a-zA-Z0–9.-]+\.[a-zA-Z]{2,4}$/;
  if (regex.test(email.value)){
    msg.value.validation = '';
  } else {
    msg.value.validation = 'Valid email required';
  }
}
</script>