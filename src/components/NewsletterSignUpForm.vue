<template>
  <div class="flex lg:my-32 md:my-32 justify-center items-center w-full">
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-2 bg-white md:rounded-[1.9rem] lg:md:rounded-[1.9rem] lg:p-6 md:p-6">
      <div class=" my-16 lg:order-1 md:order-1 order-2 lg:pl-10 md:pl-10 lg:pr-0 md:pr-0 px-6">
        <div class="flex flex-col pt-4 ">
          <h1 class="font-bold text-6xl text-darkSlateGrey pb-8 ">Stay updated!</h1>
          <p class="text-base lg:w-5/6">
            Join 60.000+ product managers receiving monthly updates on:
          </p>
          <div class="my-6">
            <div v-for="content in contents" :key="content.id" class="flex gap-4 py-2">
              <img class="w-5 h-5" :src="successIcon" alt="Success Icon">
              <p>{{ content.text }}</p>
            </div>
          </div>
        </div>
        <Form @submitForm="sendEmail"></Form>
      </div>
      <div class="flex lg:justify-end md:justify-end justify-center lg:order-2 md:order-2 order-1">
        <img  :src="imageUrl" alt="Sign up to our newsletter"/>
      </div>
    </div>
  </div>
</template>

  <script setup>
    import Form from './Form.vue';
    import { onMounted, onUnmounted, ref } from 'vue';
    import successIcon  from "../assets/icon-success.svg";
    import desktopImg  from "../assets/illustration-sign-up-desktop.svg";
    import mobileImg  from "../assets/illustration-sign-up-mobile.svg";

    defineProps(['contents']);
    const emits = defineEmits(['submitForm']);
    const imageUrl = ref('');
    const sendEmail = (data) => {
      emits('submitForm', data.value);
    }
    const setResponsiveImage = () => {
      const screenWidth = window.innerWidth;
      if (screenWidth < 768) {
        imageUrl.value = mobileImg;
      } else {
        imageUrl.value = desktopImg;
      }
    };
    onMounted(() => {
      setResponsiveImage();
      window.addEventListener('resize', setResponsiveImage);
    });

    onUnmounted(() => {
      window.removeEventListener('resize', setResponsiveImage);
    });

  </script>
