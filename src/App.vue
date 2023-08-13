<script setup>
import VueInteractiveTable from "./components/VueInteractiveTable.vue";
import VueSidebar from "./components/VueSideBar.vue";
import VueTabs from "./components/VueTabs.vue";
</script>

<template>
  <div class="flex bg-[#fbfcfd]">
    <VueSidebar/>
      <div class="w-full px-[25px]">
        <h1 class="text-[36px] mt-[25px]">Проведение ТО и мелкий ремонт</h1>
        <VueTabs />
        <div
          class="bg-white px-[25px] py-[20px] shadow-xl rounded-[10px] mt-[25px]"
        >
          <button
            class="bg-[#2f8cff] text-white text-sm py-[10px] px-[15px] rounded-[5px]"
          >
            Добавить строку
          </button>
        </div>

        <VueInteractiveTable />
      </div>
  </div>
</template>
