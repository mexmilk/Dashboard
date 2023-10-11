<template>
    <div class="w-80 rounded-xl bg-gray-100">
      <p class="text-slate-500 text-sm mt-3 ml-6">แผงควบคุมไฟ / เสียง</p>
      <div class="flex flex-col gap-2 p-8">
        <label class="flex cursor-pointer items-center justify-between p-1 text-slate-500 text-sm">
          จอดเกินเวลา
          <div class="relative inline-block">
            <input
              type="checkbox"
              id="blink" 
              v-model="blinkChecked"
              @change="changeBlink"
              class="peer h-6 w-10 cursor-pointer appearance-none rounded-full border border-gray-300 bg-white checked:bg-green-400 checked:border-green-300 focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-gray-900 focus-visible:ring-offset-2"
            />
            <span
              class="pointer-events-none absolute left-1 top-1 block h-4 w-4 rounded-full bg-gray-400 transition-all duration-200 peer-checked:left-5 peer-checked:bg-white"
            ></span>
          </div>
        </label>
        <label class="flex cursor-pointer items-center justify-between p-1 text-slate-500 text-sm">
          ห้ามจอด
          <div class="relative inline-block">
            <input
              type="checkbox"
              id="red" 
              v-model="redChecked" 
              @change="changeRed"
              class="peer h-6 w-10 cursor-pointer appearance-none rounded-full border border-gray-300 bg-white checked:bg-green-400 checked:border-green-300 focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-gray-900 focus-visible:ring-offset-2"
            />
            <span
              class="pointer-events-none absolute left-1 top-1 block h-4 w-4 rounded-full bg-gray-400 transition-all duration-200 peer-checked:left-5 peer-checked:bg-white"
            ></span>
          </div>
        </label>
        <label class="flex cursor-pointer items-center justify-between p-1 text-slate-500 text-sm">
          กำลังใช้บริการ
          <div class="relative inline-block">
            <input
              type="checkbox"
              id="yellow" 
              v-model="yellowChecked" 
              @change="changeYellow"
              class="peer h-6 w-10 cursor-pointer appearance-none rounded-full border border-gray-300 bg-white checked:bg-green-400 checked:border-green-300 focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-gray-900 focus-visible:ring-offset-2"
            />
            <span
              class="pointer-events-none absolute left-1 top-1 block h-4 w-4 rounded-full bg-gray-400 transition-all duration-200 peer-checked:left-5 peer-checked:bg-white"
            ></span>
          </div>
        </label>
        <label class="flex cursor-pointer items-center justify-between p-1 text-slate-500 text-sm">
          จอดได้
          <div class="relative inline-block">
            <input
              type="checkbox"
              id="green" 
              v-model="greenChecked" 
              @change="changeGreen"
              class="peer h-6 w-10 cursor-pointer appearance-none rounded-full border border-gray-300 bg-white checked:bg-green-400 checked:border-green-300 focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-gray-900 focus-visible:ring-offset-2"
            />
            <span
              class="pointer-events-none absolute left-1 top-1 block h-4 w-4 rounded-full bg-gray-400 transition-all duration-200 peer-checked:left-5 peer-checked:bg-white"
            ></span>
          </div>
        </label>
        <label class="flex cursor-pointer items-center justify-between p-1 text-slate-500 text-sm">
          แจ้งเตือนด้วยเสียง
          <div class="relative inline-block">
            <input
              type="checkbox"
              class="peer h-6 w-10 cursor-pointer appearance-none rounded-full border border-gray-300 bg-white checked:bg-green-400 checked:border-green-300 focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-gray-900 focus-visible:ring-offset-2"
            />
            <span
              class="pointer-events-none absolute left-1 top-1 block h-4 w-4 rounded-full bg-gray-400 transition-all duration-200 peer-checked:left-5 peer-checked:bg-white"
            ></span>
          </div>
        </label>
      </div>
    </div>
  </template>




<script>
export default {
  data() {
    return {
      redChecked: false,
      yellowChecked: false,
      greenChecked: false,
      blinkChecked: false,
    }
  },

  methods: {
    change(status, num) {
      const url = 'http://127.0.0.1:1880/eiei';
      const data = {
        "value": [status],
        "fc": 15,
        "unitid": 1,
        "address": num,
        "quantity": 1
      };

      fetch("http://127.0.0.1:1880/eiei", {
      method: "POST",
      body: JSON.stringify(data),
      headers: {
        "Content-type": "application/json"
        }
      })
      .then((response) => response.json())
      .then((response) => console.log(json));
    },

    changeRed() {
      this.change(this.redChecked, 0);
    },

    changeYellow() {
      this.change(this.yellowChecked, 1);
    },

    changeGreen() {
      this.change(this.greenChecked, 2);
    },

    changeBlink() {
      let i = 1;

      const myLoop = () => {
        setTimeout(() => {
          if (i % 2 == 0){
            this.change(true, 0);
            console.log("t");
          }
          else {
            this.change(false, 0);
            console.log("A");
            console.log(i);
          }
          i++;

          if (this.blinkChecked) {
            myLoop();
          }
        },
        500);
      };

      if (this.blinkChecked){
        myLoop();
      }
      else {
        this.change(false, 0);
      }
    },

    changeOpen() {
      if(this.openChecked) {
        this.change(true, 0);
        this.change(true, 1);
        this.change(true, 2);
      }
      else {
        this.change(false, 0);
        this.change(false, 1);
        this.change(false, 2);
      }
    },
  },
};
</script>
  
  