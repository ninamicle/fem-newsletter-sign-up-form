<script setup>
import {ref} from "vue";

const email = ref("")
const handleSubmit = ()=>{
console.log(email.value);
}
</script>

<template>
  <form @submit.prevent="handleSubmit" class="flex flex-col gap-y-4">
    <div class="flex flex-col">
      <label class="font-bold py-2" for="email">Email address</label>
      <input class="border border-grey rounded-lg h-12 placeholder:px-6"
             v-model="email" type="email" id="email"
             placeholder="email@company.com"/>
    </div>
    <button class="bg-darkSlateGrey text-white font-bold tracking-wide h-12 rounded-lg w-full" type="submit">Subscribe to monthly newsletter</button>
  </form>
</template>

<style scoped>

</style>