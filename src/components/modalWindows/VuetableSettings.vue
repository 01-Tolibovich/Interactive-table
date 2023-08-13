<script setup>
import { defineEmits, ref } from "vue";
import VueModalWindow from "./VueModalWindow.vue";

const checkboxValue = true;
const isChecked1 = ref(checkboxValue);
const isChecked2 = ref(checkboxValue);
const isChecked3 = ref(checkboxValue);
const isChecked4 = ref(checkboxValue);

const emit = defineEmits([
  "closeModal",
  "nameColIsTrue",
  "nameColIsFalse",
  "priceColIsTrue",
  "priseCollIsFalse",
  "quantityColIsTrue",
  "quantityCollIsFalse",
  "productNameCollIsTrue",
  "productNameCollIsFalse",
]);

const checkbox = () => {
  if (isChecked1.value) {
    emit("nameColIsTrue", true);
  } else if (!isChecked1.value) {
    emit("nameColIsFalse", false);
  }
  if (isChecked2.value) {
    emit("priceColIsTrue", true);
  } else if (!isChecked2.value) {
    emit("priseCollIsFalse", false);
  }
  if (isChecked3.value) {
    emit("quantityColIsTrue", true);
  } else if (!isChecked3.value) {
    emit("quantityCollIsFalse", false);
  }
  if (isChecked4.value) {
    emit("productNameCollIsTrue", true);
  } else if (!isChecked4.value) {
    emit("productNameCollIsFalse", false);
  }
};

const closeSettings = () => {
  emit("closeModal", false);
};
</script>

<template>
  <VueModalWindow @closeFromBody="closeSettings">
    <div class="bg-white p-2 border border-black rounded-md grid gap-4 w-fit">
      <div @click="closeSettings" class="flex gap-2 items-center">
        <img
          class="h-[12px]"
          src="../../assets/svg/arrow-ios-back-svgrepo-com.svg"
          alt=""
        />
        <div class="font-semibold">Отображение столбцов</div>
      </div>
      <div @change="checkbox" class="flex items-center gap-1">
        <input
          class="cursor-pointer"
          type="checkbox"
          v-model="isChecked1"
          name=""
          id="name"
        />
        <label class="cursor-pointer" for="name">Наименование еденицы</label>
      </div>
      <div @change="checkbox" class="flex items-center gap-1">
        <input
          class="cursor-pointer"
          type="checkbox"
          v-model="isChecked2"
          name=""
          id="prise"
        />
        <label class="cursor-pointer" for="prise">Цена</label>
      </div>
      <div @change="checkbox" class="flex items-center gap-1">
        <input
          class="cursor-pointer"
          type="checkbox"
          v-model="isChecked3"
          name=""
          id="quantity"
        />
        <label class="cursor-pointer" for="quantity">Колличество</label>
      </div>
      <div @change="checkbox" class="flex items-center gap-1">
        <input
          class="cursor-pointer"
          type="checkbox"
          v-model="isChecked4"
          name=""
          id="product-name"
        />
        <label class="cursor-pointer" for="product-name">Название товара</label>
      </div>
    </div>
  </VueModalWindow>
</template>
