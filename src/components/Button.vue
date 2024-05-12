<template>
  <button class="bg-darkSlateGrey text-white font-bold tracking-wide h-12 rounded-lg w-full
                 hover:shadow-lg	 hover:shadow-tomato hover:bg-gradient-to-r from-tomato via-tomato to-orange-500"
          :type="type"
          @click="handleClick">
    {{ label }}
  </button>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue';

defineProps(['label', 'type']);
const emits = defineEmits(['handleClick']);

const handleClick = () => {
  emits('handleClick');
};
</script>
