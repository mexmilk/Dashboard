<template>
    <div class="realtive w-80 rounded-xl bg-white">
      <label
        class="flex cursor-pointer bg-gray-100 rounded-t-xl items-center justify-between p-3 text-slate-500 text-sm"
      >
        สถานะช่องจอด
        <div class="relative inline-block">
          <input
            type="checkbox"
            class="peer h-6 w-10 cursor-pointer appearance-none rounded-full border border-gray-300 bg-white checked:bg-green-400 checked:border-green-300 focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-gray-900 focus-visible:ring-offset-2"
            v-model="open"
          />
          <span
            class="pointer-events-none absolute left-1 top-1 block h-4 w-4 rounded-full bg-gray-400 transition-all duration-200 peer-checked:left-5 peer-checked:bg-white"
          ></span>
        </div>
      </label>
      <div v-if="open">
        <transition
          enter-active-class="transition ease-out duration-200"
          enter-from-class="opacity-0 translate-y-1"
          enter-to-class="opacity-100 translate-y-0"
          leave-active-class="transition ease-in duration-150"
          leave-from-class="opacity-100 translate-y-0"
          leave-to-class="opacity-0 translate-y-1"
        >
          <div class="absolute">
            <div
              class="w-80 flex-auto overflow-hidden rounded-b-xl bg-gray-100 text-sm leading-6"
            >
              <div>
                <p class="pt-1 text-center text-slate-500 text-sm">
                  ยืนยันการปิดช่องจอด
                </p>
                <p class="pt-3 text-center text-slate-300 text-sm">
                  การปิดช่องจอดมีผลต่อการใช้บริการของลูกค้าระบบจะมีการส่ง SMS
                  แจ้งให้ลูกค้าดังนี้
                </p>
                <p class="pt-5 text-center text-[#26ADC9] text-sm">
                  "Planet EV
                  มีการปิดปรับปรุงช่องจอดชั่วคราวกรุณาจองช่องจอดเข้ามาใหม่อีกครั้ง
                  ขออภัยในความไม่สะดวก ขอบคุณค่ะ"
                </p>
              </div>
              <div class="grid grid-cols-2 p-3">
                <button
                  class="inline-block cursor-pointer rounded-3xl bg-[#26ADC9] px-2 py-3 m-5 text-center text-xs text-white transition duration-200 ease-in-out hover:bg-[#2badcf] focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-gray-700 focus-visible:ring-offset-2 active:scale-95"
                  @click="closeCheckbox"
                >
                  ยืนยัน
                </button>
                <button
                  class="inline-block cursor-pointer rounded-3xl bg-gray-700 px-2 py-3 m-5 text-center text-xs text-white transition duration-200 ease-in-out hover:bg-gray-800 focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-gray-700 focus-visible:ring-offset-2 active:scale-95"
                  @click="navigateToSetting();"
                >
                  แก้ไขข้อความ
                </button>
              </div>
            </div>
          </div>
        </transition>
      </div>
    </div>
  </template>
  
  <script>
  import Setting from "./Setting.vue";
  import { ref } from "vue";
  import VueRouter from "vue-router";
  
  const open = ref(false);
  
  const router = new VueRouter({
    routes: [
      {
        path: "/setting",
        component: Setting,
      },
    ],
  });
  
  export default {
    comments: {
      Setting,
    },
  
    data() {
      return {
        open: false,
      };
    },
  
  
    methods: {
      closeCheckbox() {
        this.open = false;
      },
  
      navigateToSetting() {
        this.$router.push('/setting');
      },
    },
  };
  </script>
  
  <!-- <button
            class="inline-block cursor-pointer rounded-md bg-gray-700 px-4 py-3.5 text-center text-sm font-semibold uppercase text-white transition duration-200 ease-in-out hover:bg-gray-800 focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-gray-700 focus-visible:ring-offset-2 active:scale-95"
          >
            Save
          </button> -->
  <!-- @click="open = !open" -->
  