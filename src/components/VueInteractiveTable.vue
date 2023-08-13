<script setup>
import { ref } from "vue";
import Draggable from "vue3-draggable";
import VuetableSettings from "./modalWindows/VuetableSettings.vue";

const row = ref([
  {
    id: 1,
    title: "Мраморный щебень фр. 2-5 мм, 25кг",
    price: "1231",
    quantuty: "5",
    productName: "Мраморный щебень",
    result: "1231",
  },
  {
    id: 2,
    title: "Мраморный щебень фр. 2-5 мм, 25кг",
    price: "123",
    quantuty: "3",
    productName: "Мраморный щебень",
    result: "1231",
  },
  {
    id: 3,
    title: "Мраморный щебень фр. 2-5 мм, 25кг",
    price: "12",
    quantuty: "8",
    productName: "Мраморный щебень",
    result: "1231",
  },
  {
    id: 4,
    title: "Мраморный щебень",
    price: "1",
    quantuty: "45",
    productName: "Мраморный щебень",
    result: "1231",
  },
]);
const tableSettingsModal = ref(false);

const settingsFillter = () => {
  tableSettingsModal.value = true;
};
const closeSettingsWindow = (valueFromChild) => {
  tableSettingsModal.value = valueFromChild;
};

const name = ref(true);
const nameColIsTrue = (value) => {
  name.value = value;
};
const nameColIsFalse = (value) => {
  name.value = value;
};

const price = ref(true);
const priceColIsTrue = (value) => {
  price.value = value;
};
const priseCollIsFalse = (value) => {
  price.value = value;
};

const quantity = ref(true);
const quantityColIsTrue = (value) => {
  quantity.value = value;
};
const quantityCollIsFalse = (value) => {
  quantity.value = value;
};

const productName = ref(true);
const productNameCollIsTrue = (value) => {
  productName.value = value;
};
const productNameCollIsFalse = (value) => {
  productName.value = value;
};
</script>

<template>
  <div
    class="mt-[25px] bg-white rounded-[10px] mb-14 shadow-xl border border-white"
  >
    <div class="h-[32px] flex items-center justify-end mx-[15px]">
      <img
        @click="settingsFillter"
        class="cursor-pointer"
        src="../assets/svg/settings.svg"
        alt=""
      />
    </div>
    <div>
      <vuetable-settings
        @closeModal="closeSettingsWindow"
        @nameColIsTrue="nameColIsTrue"
        @nameColIsFalse="nameColIsFalse"
        @priceColIsTrue="priceColIsTrue"
        @priseCollIsFalse="priseCollIsFalse"
        @quantityColIsTrue="quantityColIsTrue"
        @quantityCollIsFalse="quantityCollIsFalse"
        @productNameCollIsTrue="productNameCollIsTrue"
        @productNameCollIsFalse="productNameCollIsFalse"
        v-if="tableSettingsModal"
      />
    </div>

    <header class="_table-header grid grid-flow-col border border-[#eeeff1]">
      <span>Номе</span>
      <span>Д</span>
      <span v-show="name">Наименование еденицы</span>
      <span v-show="price">Цена</span>
      <span v-show="quantity">Кол-во</span>
      <span v-show="productName">Название товара</span>
      <span>Итого</span>
    </header>
    <draggable v-model="row">
      <template v-slot:item="{ item }">
        <div class="_table-items grid grid-flow-col">
          <div>
            <img
              class="cursor-move"
              src="../assets/svg/combined-shape.svg"
              alt=""
            />
          </div>
          <div><img src="../assets/svg/dots.svg" alt="" /></div>
          <div v-show="name">
            <p>{{ item.title }}</p>
          </div>
          <div v-show="price">
            <p>{{ item.price }}</p>
          </div>
          <div v-show="quantity">
            <p>{{ item.quantuty }}</p>
          </div>
          <div v-show="productName">
            <p>{{ item.productName }}</p>
          </div>
          <div>
            <p>{{ item.result }}</p>
          </div>
        </div>
      </template>
    </draggable>
  </div>
</template>
