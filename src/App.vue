<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Form from "./components/Form.vue";
import desktopImg  from "/public/illustration-sign-up-desktop.svg";
import mobileImg  from "/public/illustration-sign-up-mobile.svg";
import successIcon  from "/public/icon-success.svg";

</script>

<template>
  <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-2 items-center bg-white rounded-[1.9rem] pl-16 pr-6 py-6">
    <div class="h-full my-20">
      <div class="flex flex-col pt-4 ">
        <h1 class="font-bold text-[3.4rem] text-darkSlateGrey tracking-wide">Stay updated!</h1>
        <p class="text-base">
          Join 60.000+ product managers receiving monthly updates on:
        </p>
        <div class="flex gap-4">
          <img class="w-5 h-5" v-bind:src="successIcon" alt="Success Icon">
          <p>Product discovery and building what matters</p>
        </div>
        <div class="flex gap-4">
          <img class="w-5 h-5" v-bind:src="successIcon" alt="Success Icon">
          <p>Measuring to ensure updates are a success</p>
        </div>
        <div class="flex gap-4">
          <img class="w-5 h-5" v-bind:src="successIcon" alt="Success Icon">
          <p>And much more!</p>
        </div>
      </div>
      <Form></Form>
    </div>
    <div class="flex justify-end">
      <img v-bind:src="desktopImg" alt="Sign up to our newsletter"/>
    </div>
  </div>

</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
