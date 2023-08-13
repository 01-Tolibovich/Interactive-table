<script setup>
import { ref } from 'vue';

const tabButtons = ref([
  {
    text: "Общее",
  },
  {
    text: "Товар списания",
  },
  {
   text: "Доп. расходы",
  },
]);

</script>

<template>
  <nav class="flex mt-[25px] gap-[20px]">
    <div v-for="(button, index) in tabButtons" :key="index">
      <button
        type="button"
        class="_btn-tab font-semibold hover:text-black transition-colors"
        
      >
        {{ button.text }}
      </button>
    </div>
  </nav>
</template>
