<template>
  <div class="h-full p-0 pt-0 sm:p-4">
    <div
      class="text-center sm:text-left items-center justify-center text-[#144779]"
    >
      รายการกล้องวงจรปิด(CCTV)
      <div
        class="mt-3 sm:text-left sm:justify-between sm:w-full md:w-full lg:w-3/4 sm:flex text-center items-center justify-center"
      >
        <div class="relative text-lg z-20">
          <button
            class="flex items-center justify-between px-3 py-1 bg-white w-full sm:w-[14.5vh] md:w-[16vh] lg:w-[24vh] xl:w-[36vh] border border-[#2BADCF] rounded-[30px]"
            @click="isOptionsExpanded = true"
            
          >
            <div></div>
            <span style="color: #8c8b9d; font-size: 16px">
              {{ selectedOption }}</span
            >
            <svg
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              class="h-4 w-4 transform transition-transform duration-200 ease-in-out text-[#8C8B9D]"
              :class="isOptionsExpanded ? 'rotate-180' : 'rotate-0'"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M19 9l-7 7-7-7"
              />
            </svg>
          </button>
          <div v-if="isOptionsExpanded">
    
            <transition
              enter-active-class="transform transition duration-500 ease-custom"
              enter-class="-translate-y-1/2 scale-y-0 opacity-0"
              enter-to-class="translate-y-0 scale-y-300 opacity-100"
              leave-active-class="transform transition duration-300 ease-custom"
              leave-class="translate-y-0 scale-y-300 opacity-100"
              leave-to-class="-translate-y-1/2 scale-y-0 opacity-0"
            >
              <PopoverPanel
                class="absolute left-1/2 z-10 mt-5 flex w-screen max-w-max -translate-x-1/2 px-4 overflow-hidden transition-transform transform-gpu duration-500 ease-in-out"
              >
                <div
                  class="w-screen max-w-md flex-auto overflow-hidden rounded-xl bg-white text-sm leading-6 ring-1 ring-gray-900/5"
                >
                <button
                        class="absolute right-2 top-2 text-gray-400 hover:text-gray-500 sm:right-6 sm:top-8 md:right-6 md:top-6 lg:right-8 lg:top-8"
                        @click="close"
                      >
                        Close
                </button>
                  <FullCalendar :options="calendarOptions"> </FullCalendar>
                </div>
              </PopoverPanel>
            </transition>
          </div>
        </div>

        <div class="flex lg:w-3/5 justify-between">
          <div class="relative text-lg z-10 mt-5 sm:mt-0">
            <button
              @click="selectedStatus = 'all'"
              :class="{
                'bg-cyan-500 text-[#2BADCF]': selectedStatus === 'all',
              }"
              class="text-[#2BADCF] hover:text-white hover:bg-[#2BADCF] focus:text-white focus:bg-[#2BADCF] items-center text-center px-4 py-1 bg-white w-full sm:w-[14.8vh] md:w-[16vh] lg:w-[16vh] xl:w-[18vh] border border-[#2BADCF] rounded-[30px]"
            >
              <span class="text-[16px]"> ทั้งหมด</span>
            </button>
          </div>

          <div class="relative text-lg z-10 mt-5 sm:mt-0">
            <button
              @click="selectedStatus = 'online'"
              :class="{
                'bg-[#2BADCF] text-white': selectedStatus === 'online',
              }"
              class="text-[#2BADCF] hover:text-white hover:bg-[#2BADCF] focus:text-white focus:bg-[#2BADCF] items-center text-center px-4 py-1 bg-white w-full sm:w-[14.8vh] md:w-[16vh] lg:w-[16vh] xl:w-[18vh] border border-[#2BADCF] rounded-[30px]"
            >
              <span class="text-[16px]"> ออนไลน์</span>
            </button>
          </div>

          <div class="relative text-lg z-10 mt-5 sm:mt-0">
            <button
              @click="selectedStatus = 'offline'"
              :class="{
                'bg-[#2BADCF] text-white': selectedStatus === 'offline',
              }"
              class="text-[#2BADCF] hover:text-white hover:bg-[#2BADCF] focus:text-white focus:bg-[#2BADCF] items-center text-center px-4 py-1 bg-white w-full sm:w-[14.8vh] md:w-[16vh] lg:w-[16vh] xl:w-[18vh] border border-[#2BADCF] rounded-[30px]"
            >
              <span class="text-[16px]">ออฟไลน์</span>
            </button>
          </div>
        </div>
      </div>

      <div class="relative overflow-x-auto h-[65vh] w-full mt-3">
        <div class="flex flex-wrap">
          <!-- Column -->
          <div
            class="my-1 px-1 w-full md:w-1/2 lg:px-4 lg:w-1/3"
            v-for="(video, index) in filteredVideoData"
            :key="index"
          >
            <!-- Article -->
            <article class="overflow-hidden rounded-lg shadow-lg">
              <video-player :src="video.rtsp" />
            </article>
            <!-- END Article -->
          </div>
          <!-- END Column -->

          <!-- Column -->
          <!-- <div class="my-1 px-1 w-full md:w-1/2 lg:px-4 lg:w-1/3">
            
            <article class="overflow-hidden rounded-lg shadow-lg">
              <video-player src="https://www.youtube.com/watch?v=4OrCA1OInoo" />
            </article>
            
          </div> -->
          <!-- END Column -->

          <!-- Column -->
          <!-- <div class="my-1 px-1 w-full md:w-1/2 lg:px-4 lg:w-1/3">
           
            <article class="overflow-hidden rounded-lg shadow-lg">
              <video-player
                src="https://www.youtube.com/watch?v=GZJpDjdzdv8&list=PLAxcm_L4yBeoqpP3eLMtR1HAwx1X5MD4v"
              />
            </article>
            
          </div> -->
          <!-- END Column -->

          <!-- Column -->
          <!-- <div class="my-1 px-1 w-full md:w-1/2 lg:px-4 lg:w-1/3">
            <article class="overflow-hidden rounded-lg shadow-lg">
              <a href="#">
                <img
                  alt="Placeholder"
                  class="block h-auto w-full"
                  src="https://picsum.photos/600/400/?random"
                />
              </a>

              <header
                class="flex items-center justify-between leading-tight p-2 md:p-4"
              >
                <h1 class="text-lg">
                  <a class="no-underline hover:underline text-black" href="#">
                    Article Title
                  </a>
                </h1>
                <p class="text-grey-darker text-sm">11/1/19</p>
              </header>

              <footer
                class="flex items-center justify-between leading-none p-2 md:p-4"
              >
                <a
                  class="flex items-center no-underline hover:underline text-black"
                  href="#"
                >
                  <img
                    alt="Placeholder"
                    class="block rounded-full"
                    src="https://picsum.photos/32/32/?random"
                  />
                  <p class="ml-2 text-sm">Author Name</p>
                </a>
                <a
                  class="no-underline text-grey-darker hover:text-red-dark"
                  href="#"
                >
                  <span class="hidden">Like</span>
                  <i class="fa fa-heart"></i>
                </a>
              </footer>
            </article>
          </div> -->
          <!-- END Column -->

          <!-- Column -->
          <!-- <div class="my-1 px-1 w-full md:w-1/2 lg:px-4 lg:w-1/3">
            <article class="overflow-hidden rounded-lg shadow-lg">
              <a href="#">
                <img
                  alt="Placeholder"
                  class="block h-auto w-full"
                  src="https://picsum.photos/600/400/?random"
                />
              </a>

              <header
                class="flex items-center justify-between leading-tight p-2 md:p-4"
              >
                <h1 class="text-lg">
                  <a class="no-underline hover:underline text-black" href="#">
                    Article Title
                  </a>
                </h1>
                <p class="text-grey-darker text-sm">11/1/19</p>
              </header>

              <footer
                class="flex items-center justify-between leading-none p-2 md:p-4"
              >
                <a
                  class="flex items-center no-underline hover:underline text-black"
                  href="#"
                >
                  <img
                    alt="Placeholder"
                    class="block rounded-full"
                    src="https://picsum.photos/32/32/?random"
                  />
                  <p class="ml-2 text-sm">Author Name</p>
                </a>
                <a
                  class="no-underline text-grey-darker hover:text-red-dark"
                  href="#"
                >
                  <span class="hidden">Like</span>
                  <i class="fa fa-heart"></i>
                </a>
              </footer>
            </article>
          </div> -->
          <!-- END Column -->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import VideoPlayer from "nuxt-video-player";
import FullCalendar from "@fullcalendar/vue";
import dayGridPlugin from "@fullcalendar/daygrid";
import interactionPlugin from "@fullcalendar/interaction";

require("nuxt-video-player/src/assets/css/main.css");
export default {
  data() {
    return {
      isOptionsExpanded: false,
      selectedOption: "วันนี้",
      options: [],

      calendarOptions: {
        plugins: [dayGridPlugin, interactionPlugin],
        initialView: "dayGridMonth",
        dateClick: this.handleDateClick,
        headerToolbar: {
          left: "prev,title",
          center: "",
          right: "today",
        },
        events: [
          { title: "event 1", date: "2023-10-01" },
          { title: "event 2", date: "2019-04-02" },
        ],
      },

      selectedStatus: "all",
      videoData: [
        {
          id: 1,
          rtsp: "https://www.youtube.com/watch?v=4OrCA1OInoo",
          status: false,
        },
        {
          id: 2,
          rtsp: "https://www.youtube.com/watch?v=ZiVa8CABOwU",
          status: true,
        },
        {
          id: 3,
          rtsp: "https://www.youtube.com/watch?v=1S34b4IfNSo&list=RDkjYW63CVbsE&index=11",
          status: false,
        },
        {
          id: 4,
          rtsp: "https://www.youtube.com/watch?v=MjStBdYQ7zg",
          status: false,
        },
      ],
    };
  },
  components: {
    VideoPlayer,
    FullCalendar,
  },
  computed: {
    filteredVideoData() {
      if (this.selectedStatus === "all") {
        return this.videoData;
      } else {
        const statusFilter = this.selectedStatus === "online";
        return this.videoData.filter((video) => video.status === statusFilter);
      }
    },
  },
  methods: {
    setOption(option) {
      this.selectedOption = option;
    },

    close() {
      this.isOptionsExpanded = false; 
    },

    handleDateClick: function (arg) {
      alert("date click! " + arg.dateStr);
    },
  },
};
</script>

<style>
.ease-custom {
  transition-timing-function: cubic-bezier(0.61, -0.53, 0.43, 1.43);
}
</style>
