<template>
  <div class="h-full flex mt-1">
    <div class="flex justify-between w-full">
      <div class="flex flex-col h-full w-[35%] text-center text-[#0F3157]">
        <div
          class="flex-grow border-t-2 border-l-2 border-b-2 border-dotted flex items-center justify-center cursor-pointer"
          @click="p1n = !p1n"
        >
          <div
            class="flex"
            :class="[
              'flex',
              'items-center',
              'justify-center',
              'text-sm lg:text-xl sm:text-sm',
              'cursor-pointer',
              { 'bg-gray-300 rounded-[10px] h-4/5 w-[90%] lg:w-4/5': !p1n },
            ]"
          >
            P1 -
            <p class="text-[#008890] pl-1" :class="{ 'text-red-500': !p1n }">
              {{ p1n ? "AC" : "AC Close" }}
            </p>
          </div>
        </div>
        <div
          class="flex-grow border-l-2 border-b-2 border-dotted flex items-center justify-center cursor-pointer"
          @click="p2n = !p2n"
        >
          <div
            class="flex"
            :class="[
              'flex',
              'items-center',
              'justify-center',
              'text-sm lg:text-xl sm:text-sm',
              'cursor-pointer',
              { 'bg-gray-300 rounded-[10px] h-4/5 w-[90%] lg:w-4/5': !p2n },
            ]"
          >
            P2 -
            <p class="text-[#008890] pl-1" :class="{ 'text-red-500': !p2n }">
              {{ p2n ? "AC" : "AC Close" }}
            </p>
          </div>
        </div>
        <div
          class="flex-grow border-l-2 border-b-2 border-dotted flex items-center justify-center cursor-pointer"
          @click="p3n = !p3n"
        >
          <div
            class="flex"
            :class="[
              'flex',
              'items-center',
              'justify-center',
              'text-sm lg:text-xl sm:text-sm',
              'cursor-pointer',
              { 'bg-gray-300 rounded-[10px] h-4/5 w-[90%] lg:w-4/5': !p3n },
            ]"
          >
            P3 -
            <p class="text-[#008890] pl-1" :class="{ 'text-red-500': !p3n }">
              {{ p3n ? "DC" : "DC Close" }}
            </p>
          </div>
        </div>

        <div
          class="flex-grow border-l-2 border-b-2 border-dotted flex items-center justify-center cursor-pointer"
          @click="p4n = !p4n"
        >
          <div
            class="flex"
            :class="[
              'flex',
              'items-center',
              'justify-center',
              'text-sm lg:text-xl sm:text-sm',
              'cursor-pointer',
              { 'bg-gray-300 rounded-[10px] h-4/5 w-[90%] lg:w-4/5': !p4n },
            ]"
          >
            P4 -
            <p class="text-[#008890] pl-1" :class="{ 'text-red-500': !p4n }">
              {{ p4n ? "DC" : "DC Close" }}
            </p>
          </div>
        </div>
        <div
          class="flex-grow border-l-2 border-b-2 border-dotted flex items-center justify-center cursor-pointer"
          @click="p5n = !p5n"
        >
          <div
            class="flex"
            :class="[
              'flex',
              'items-center',
              'justify-center',
              'text-sm lg:text-xl sm:text-sm',
              'cursor-pointer',
              { 'bg-gray-300 rounded-[10px] h-4/5 w-[90%] lg:w-4/5': !p5n },
            ]"
          >
            P5 -
            <p class="text-[#008890] pl-1" :class="{ 'text-red-500': !p5n }">
              {{ p5n ? "DC" : "DC Close" }}
            </p>
          </div>
        </div>
        <div
          class="flex-grow border-l-2 border-b-2 border-dotted flex items-center justify-center cursor-pointer"
          @click="p6n = !p6n"
        >
          <div
            class="flex"
            :class="[
              'flex',
              'items-center',
              'justify-center',
              'text-sm lg:text-xl sm:text-sm',
              'cursor-pointer',
              { 'bg-gray-300 rounded-[10px] h-4/5 w-[90%] lg:w-4/5': !p6n },
            ]"
          >
            P6 -
            <p class="text-[#008890] pl-1" :class="{ 'text-red-500': !p6n }">
              {{ p6n ? "DC" : "DC Close" }}
            </p>
          </div>
        </div>
      </div>

      <div class="text-[#D3D3D7] text-2xl font-extralight pt-5">ทางเข้า</div>

      <div class="flex flex-col h-full w-[35%] text-center text-[#0F3157]">

        <input
          type="button"
          value="P7 - Public"
          class="flex-grow border-t-2 text-center border-r-2 border-b-2 border-dotted flex items-center justify-center text-sm lg:text-xl sm:text-sm cursor-pointer"
          @click="p7n = true"
        />
        <!-- P7 - Public -->
        <div class="flex z-50 absolute" v-show="p7n">
          <div
            class="fixed inset-0 hidden bg-gray-500 bg-opacity-75 transition-opacity md:block"
          >
            <div class="fixed inset-0 z-10 overflow-y-auto">
              <div
                class="flex min-h-full items-stretch justify-center text-center md:items-center md:px-2 lg:px-4"
              >
                <TransitionChild
                  as="template"
                  enter="ease-out duration-300"
                  enter-from="opacity-0 translate-y-4 md:translate-y-0 md:scale-95"
                  enter-to="opacity-100 translate-y-0 md:scale-100"
                  leave="ease-in duration-200"
                  leave-from="opacity-100 translate-y-0 md:scale-100"
                  leave-to="opacity-0 translate-y-4 md:translate-y-0 md:scale-95"
                >
                  <DialogPanel
                    class="flex w-full transform text-left text-base transition md:max-w-2xl md:px-4 lg:max-w-4xl"
                  >
                    <div
                      class="relative flex w-full items-center overflow-hidden bg-white px-4 pb-8 pt-14 shadow-2xl rounded-2xl sm:px-6 sm:pt-8 md:p-6 lg:p-8"
                    >
                      <p class="absolute text-lg left-4 top-6 text-gray-800">
                        ตั้งค่าช่องจอด P7
                      </p>
                      <button
                        class="absolute right-2 top-2 text-gray-400 hover:text-gray-500 sm:right-6 sm:top-8 md:right-6 md:top-6 lg:right-8 lg:top-8"
                        @click="closeP7"
                      >
                        Close
                      </button>

                      <div
                        class="grid w-full grid-cols-2 gap-x-3 gap-y-3 mt-5 -mb-3"
                      >
                        <div class="flex m-10"><p>สถานะช่อง :</p></div>
                        <div class="flex m-10"><p>ทะเบียน :</p></div>
                        <div class="flex m-10"><p>เวลาเริ่มต้น :</p></div>
                        <div class="flex m-10"><p>เวลาสิ้นสุด :</p></div>
                        <Status />
                        <Control />
                      </div>
                    </div>
                  </DialogPanel>
                </TransitionChild>
              </div>
            </div>
          </div>
        </div>
        <!-- END P7 - Public -->

        <input
        type="button"
          value="P8 - Public"
          class="flex-grow border-r-2 border-b-2 border-dotted text-center flex items-center justify-center text-sm lg:text-xl sm:text-sm cursor-pointer"
          @click="p8n = true"
        />
        <!-- P8 - Public -->
        <div class="flex z-50 absolute" v-show="p8n">
          <div
            class="fixed inset-0 hidden bg-gray-500 bg-opacity-75 transition-opacity md:block"
          >
            <div class="fixed inset-0 z-10 overflow-y-auto">
              <div
                class="flex min-h-full items-stretch justify-center text-center md:items-center md:px-2 lg:px-4"
              >
                <TransitionChild
                  as="template"
                  enter="ease-out duration-300"
                  enter-from="opacity-0 translate-y-4 md:translate-y-0 md:scale-95"
                  enter-to="opacity-100 translate-y-0 md:scale-100"
                  leave="ease-in duration-200"
                  leave-from="opacity-100 translate-y-0 md:scale-100"
                  leave-to="opacity-0 translate-y-4 md:translate-y-0 md:scale-95"
                >
                  <DialogPanel
                    class="flex w-full transform text-left text-base transition md:max-w-2xl md:px-4 lg:max-w-4xl"
                  >
                    <div
                      class="relative flex w-full items-center overflow-hidden bg-white px-4 pb-8 pt-14 shadow-2xl rounded-2xl sm:px-6 sm:pt-8 md:p-6 lg:p-8"
                    >
                      <p class="absolute text-lg left-4 top-6 text-gray-800">
                        ตั้งค่าช่องจอด P8
                      </p>
                      <button
                        class="absolute right-2 top-2 text-gray-400 hover:text-gray-500 sm:right-6 sm:top-8 md:right-6 md:top-6 lg:right-8 lg:top-8"
                        @click="closeP8"
                      >
                        Close
                      </button>

                      <div
                        class="grid w-full grid-cols-2 gap-x-3 gap-y-3 mt-5 -mb-3"
                      >
                        <div class="flex m-10"><p>สถานะช่อง :</p></div>
                        <div class="flex m-10"><p>ทะเบียน :</p></div>
                        <div class="flex m-10"><p>เวลาเริ่มต้น :</p></div>
                        <div class="flex m-10"><p>เวลาสิ้นสุด :</p></div>
                        <Status />
                        <Control />
                      </div>
                    </div>
                  </DialogPanel>
                </TransitionChild>
              </div>
            </div>
          </div>
        </div>
        <!-- END P8 - Public -->

        <input
        type="button"
          value="P9 - Public"
          class="flex-grow border-r-2 border-b-2 border-dotted text-center flex items-center justify-center text-sm lg:text-xl sm:text-sm cursor-pointer"
          @click="p9n = true"
        />
        <!-- P9 - Public -->
        <div class="flex z-50 absolute" v-show="p9n">
          <div
            class="fixed inset-0 hidden bg-gray-500 bg-opacity-75 transition-opacity md:block"
          >
            <div class="fixed inset-0 z-10 overflow-y-auto">
              <div
                class="flex min-h-full items-stretch justify-center text-center md:items-center md:px-2 lg:px-4"
              >
                <TransitionChild
                  as="template"
                  enter="ease-out duration-300"
                  enter-from="opacity-0 translate-y-4 md:translate-y-0 md:scale-95"
                  enter-to="opacity-100 translate-y-0 md:scale-100"
                  leave="ease-in duration-200"
                  leave-from="opacity-100 translate-y-0 md:scale-100"
                  leave-to="opacity-0 translate-y-4 md:translate-y-0 md:scale-95"
                >
                  <DialogPanel
                    class="flex w-full transform text-left text-base transition md:max-w-2xl md:px-4 lg:max-w-4xl"
                  >
                    <div
                      class="relative flex w-full items-center overflow-hidden bg-white px-4 pb-8 pt-14 shadow-2xl rounded-2xl sm:px-6 sm:pt-8 md:p-6 lg:p-8"
                    >
                      <p class="absolute text-lg left-4 top-6 text-gray-800">
                        ตั้งค่าช่องจอด P9
                      </p>
                      <button
                        class="absolute right-2 top-2 text-gray-400 hover:text-gray-500 sm:right-6 sm:top-8 md:right-6 md:top-6 lg:right-8 lg:top-8"
                        @click="closeP9"
                      >
                        Close
                      </button>

                      <div
                        class="grid w-full grid-cols-2 gap-x-3 gap-y-3 mt-5 -mb-3"
                      >
                        <div class="flex m-10"><p>สถานะช่อง :</p></div>
                        <div class="flex m-10"><p>ทะเบียน :</p></div>
                        <div class="flex m-10"><p>เวลาเริ่มต้น :</p></div>
                        <div class="flex m-10"><p>เวลาสิ้นสุด :</p></div>
                        <Status />
                        <Control />
                      </div>
                    </div>
                  </DialogPanel>
                </TransitionChild>
              </div>
            </div>
          </div>
        </div>
        <!-- END P9 - Public -->

        <input
        type="button"
          value="P10 - Public"
          class="flex-grow border-r-2 border-b-2 border-dotted text-center flex items-center justify-center text-sm lg:text-xl sm:text-sm cursor-pointer"
          @click="p10n = true"
        />
        <!-- P10 - Public -->
        <div class="flex z-50 absolute" v-show="p10n">
          <div
            class="fixed inset-0 hidden bg-gray-500 bg-opacity-75 transition-opacity md:block"
          >
            <div class="fixed inset-0 z-10 overflow-y-auto">
              <div
                class="flex min-h-full items-stretch justify-center text-center md:items-center md:px-2 lg:px-4"
              >
                <TransitionChild
                  as="template"
                  enter="ease-out duration-300"
                  enter-from="opacity-0 translate-y-4 md:translate-y-0 md:scale-95"
                  enter-to="opacity-100 translate-y-0 md:scale-100"
                  leave="ease-in duration-200"
                  leave-from="opacity-100 translate-y-0 md:scale-100"
                  leave-to="opacity-0 translate-y-4 md:translate-y-0 md:scale-95"
                >
                  <DialogPanel
                    class="flex w-full transform text-left text-base transition md:max-w-2xl md:px-4 lg:max-w-4xl"
                  >
                    <div
                      class="relative flex w-full items-center overflow-hidden bg-white px-4 pb-8 pt-14 shadow-2xl rounded-2xl sm:px-6 sm:pt-8 md:p-6 lg:p-8"
                    >
                      <p class="absolute text-lg left-4 top-6 text-gray-800">
                        ตั้งค่าช่องจอด P10
                      </p>
                      <button
                        class="absolute right-2 top-2 text-gray-400 hover:text-gray-500 sm:right-6 sm:top-8 md:right-6 md:top-6 lg:right-8 lg:top-8"
                        @click="closeP10"
                      >
                        Close
                      </button>

                      <div
                        class="grid w-full grid-cols-2 gap-x-3 gap-y-3 mt-5 -mb-3"
                      >
                        <div class="flex m-10"><p>สถานะช่อง :</p></div>
                        <div class="flex m-10"><p>ทะเบียน :</p></div>
                        <div class="flex m-10"><p>เวลาเริ่มต้น :</p></div>
                        <div class="flex m-10"><p>เวลาสิ้นสุด :</p></div>
                        <Status />
                        <Control />
                      </div>
                    </div>
                  </DialogPanel>
                </TransitionChild>
              </div>
            </div>
          </div>
        </div>
        <!-- END P10 - Public -->

        <input
        type="button"
          value="P11 - Public"
          class="flex-grow border-r-2 border-b-2 border-dotted text-center flex items-center justify-center text-sm lg:text-xl sm:text-sm cursor-pointer"
          @click="p11n = true"
        />
        <!-- P11 - Public -->
        <div class="flex z-50 absolute" v-show="p11n">
          <div
            class="fixed inset-0 hidden bg-gray-500 bg-opacity-75 transition-opacity md:block"
          >
            <div class="fixed inset-0 z-10 overflow-y-auto">
              <div
                class="flex min-h-full items-stretch justify-center text-center md:items-center md:px-2 lg:px-4"
              >
                <TransitionChild
                  as="template"
                  enter="ease-out duration-300"
                  enter-from="opacity-0 translate-y-4 md:translate-y-0 md:scale-95"
                  enter-to="opacity-100 translate-y-0 md:scale-100"
                  leave="ease-in duration-200"
                  leave-from="opacity-100 translate-y-0 md:scale-100"
                  leave-to="opacity-0 translate-y-4 md:translate-y-0 md:scale-95"
                >
                  <DialogPanel
                    class="flex w-full transform text-left text-base transition md:max-w-2xl md:px-4 lg:max-w-4xl"
                  >
                    <div
                      class="relative flex w-full items-center overflow-hidden bg-white px-4 pb-8 pt-14 shadow-2xl rounded-2xl sm:px-6 sm:pt-8 md:p-6 lg:p-8"
                    >
                      <p class="absolute text-lg left-4 top-6 text-gray-800">
                        ตั้งค่าช่องจอด P11
                      </p>
                      <button
                        class="absolute right-2 top-2 text-gray-400 hover:text-gray-500 sm:right-6 sm:top-8 md:right-6 md:top-6 lg:right-8 lg:top-8"
                        @click="closeP11"
                      >
                        Close
                      </button>

                      <div
                        class="grid w-full grid-cols-2 gap-x-3 gap-y-3 mt-5 -mb-3"
                      >
                        <div class="flex m-10"><p>สถานะช่อง :</p></div>
                        <div class="flex m-10"><p>ทะเบียน :</p></div>
                        <div class="flex m-10"><p>เวลาเริ่มต้น :</p></div>
                        <div class="flex m-10"><p>เวลาสิ้นสุด :</p></div>
                        <Status />
                        <Control />
                      </div>
                    </div>
                  </DialogPanel>
                </TransitionChild>
              </div>
            </div>
          </div>
        </div>
        <!-- END P11 - Public -->

        <input
        type="button"
          value="P12 - Public"
          class="flex-grow border-r-2 border-b-2 border-dotted text-center flex items-center justify-center text-sm lg:text-xl sm:text-sm cursor-pointer"
          @click="p8n = true"
        />
        <!-- P8 - Public -->
        <div class="flex z-50 absolute" v-show="p12n">
          <div
            class="fixed inset-0 hidden bg-gray-500 bg-opacity-75 transition-opacity md:block"
          >
            <div class="fixed inset-0 z-10 overflow-y-auto">
              <div
                class="flex min-h-full items-stretch justify-center text-center md:items-center md:px-2 lg:px-4"
              >
                <TransitionChild
                  as="template"
                  enter="ease-out duration-300"
                  enter-from="opacity-0 translate-y-4 md:translate-y-0 md:scale-95"
                  enter-to="opacity-100 translate-y-0 md:scale-100"
                  leave="ease-in duration-200"
                  leave-from="opacity-100 translate-y-0 md:scale-100"
                  leave-to="opacity-0 translate-y-4 md:translate-y-0 md:scale-95"
                >
                  <DialogPanel
                    class="flex w-full transform text-left text-base transition md:max-w-2xl md:px-4 lg:max-w-4xl"
                  >
                    <div
                      class="relative flex w-full items-center overflow-hidden bg-white px-4 pb-8 pt-14 shadow-2xl rounded-2xl sm:px-6 sm:pt-8 md:p-6 lg:p-8"
                    >
                      <p class="absolute text-lg left-4 top-6 text-gray-800">
                        ตั้งค่าช่องจอด P12
                      </p>
                      <button
                        class="absolute right-2 top-2 text-gray-400 hover:text-gray-500 sm:right-6 sm:top-8 md:right-6 md:top-6 lg:right-8 lg:top-8"
                        @click="closeP12"
                      >
                        Close
                      </button>

                      <div
                        class="grid w-full grid-cols-2 gap-x-3 gap-y-3 mt-5 -mb-3"
                      >
                        <div class="flex m-10"><p>สถานะช่อง :</p></div>
                        <div class="flex m-10"><p>ทะเบียน :</p></div>
                        <div class="flex m-10"><p>เวลาเริ่มต้น :</p></div>
                        <div class="flex m-10"><p>เวลาสิ้นสุด :</p></div>
                        <Status />
                        <Control />
                      </div>
                    </div>
                  </DialogPanel>
                </TransitionChild>
              </div>
            </div>
          </div>
        </div>
        <!-- END P8 - Public -->

      </div>
    </div>
  </div>
</template>

<script>
import Control from "./Control.vue";
import Status from "./Status.vue";
import { ref } from "vue";

const open = ref(false);

export default {
  components: {
    Control,
    Status,
  },

  data() {
    return {
      p1n: false,
      p2n: false,
      p3n: false,
      p4n: false,
      p5n: false,
      p6n: false,
      p7n: false,
      p8n: false,
      p9n: false,
      p10n: false,
      p11n: false,
      p12n: false,
      open: false,

      check: [
        {
          id: 1,
          status: "book",
          p1n: true,
        },
        {
          id: 2,
          status: "park",
          p1n: true,
        },
        {
          id: 3,
          status: "blank",
          p1n: true,
        },
        {
          id: 4,
          status: "book",
          p1n: true,
        },
      ],
    };
  },

  methods: {
    closeP7() {
      this.p7n = false;
    },
    closeP8() {

      this.p8n = false;
    },

    closeP9() {
      this.p9n = false;
    },

    closeP10() {
      this.p10n = false;
    },

    closeP11() {
      this.p11n = false;
    },

    closeP12() {
      this.p12n = false;
    },
  },
};
</script>
