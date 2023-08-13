<script setup>
// import { defineEmits } from "vue";

// const emit = defineEmits(["closeFromBody"]);

// const close = () => {
//   emit("closeFromBody");
// };
</script>

<template>
  <div
    @click="close"
    class="absolute top-2/4 left-2/4 -translate-x-2/4 -translate-y-2/4 bg-[#00000078] h-full w-full flex items-center justify-center"
  >
    <div><slot></slot></div>
  </div>
</template>
