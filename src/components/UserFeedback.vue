<template>
   <div class="flex justify-center items-center">
     <div class="lg:w-[450px] md:w-[450px] w-full lg:h-full md:h-full h-[100vh] flex flex-col bg-white md:rounded-[1.9rem] lg:md:rounded-[1.9rem] lg:p-10 md:p-10 px-6 lg:my-32 md:my-32 justify-center items-center">
       <div class="flex justify-start w-full pb-6">
         <img class="w-12 h-12" :src="successIcon" alt="Success Icon">
       </div>
       <h1 class="font-bold text-5xl text-darkSlateGrey pb-6 ">Thanks for subscribing!</h1>
       <p class="text-base">
         A confirmation email has been sent to <span class="font-bold">{{email}}</span> .
         Please open it and click the button inside to confirm your subscription.
       </p>
       <div class="w-full lg:pt-8 lg:pb-2 md:pt-8 md:pb-2 pt-44 flex ">
         <Button :label="'Dismiss message'" :type="'button'" @handleClick="emits('backToForm')"/>
       </div>
     </div>
   </div>
</template>
<script setup>
import Button from "./Button.vue";
import successIcon from "../../public/icon-success.svg";

defineProps(["email"])
const emits = defineEmits(['submitForm', "backToForm"])
</script>
