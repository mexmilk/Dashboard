<template>
  <div
    class="system-content justify-center min-h-screen bg-white sm:bg-gray-200 sm:items-center sm:py-10 sm:px-16"
  >
    <div
      class="bg-white h-full sm:rounded-[30px] rounded-none sm:overflow-hidden"
    >
      <nav
        class="fixed top-0 left-0 right-0 z-50 sm:z-50 sm:static text-center text-2xl sm:text-3xl p-3 bg-white shadow sm:shadow-none text-[#26AFC8] "
      >
        <div class="relative block sm:hidden">
          <div class="absolute">
            <button
              @click="toggleSidebar"
              class="cursor-pointer inline-flex items-center text-sm text-gray-500 rounded-lg md:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400"
            >
              <fa
                :icon="['fas', 'bars']"
                class="text-3xl"
                style="color: #26afc8"
              />
            </button>
          </div>
        </div>
        Parking System
      </nav>

      <div class="flex " >
        <!-- Web App Mobile -->
        <div
          class="navbar mt-14 w-3/5 absolute inset-y-0 left-0 transition duration-200 overflow-hidden ease-in-out h-full sm:hidden z-10 "
          style="background: linear-gradient(180deg, #27aec9 0%, #09ae9f 100%)"
          :class="{
            '-translate-x-full': !showSidebar,
            ' -translate-x-0': showSidebar,
          }"
        >
          <img
            class="h-18 w-full pt-5 px-4 object-cover md:h-full md:w-96"
            src="../assets/images/All-logo-04 1.svg"
          />
          <ul class="px-4 pb-4 text-white">
            <li
              @click="
                activeDiv = 'Home';
                closeSidebar();
              "
              class="block py-2 px-4 text-sm cursor-pointer shadow-[0_1px_0px_0px_rgba(85,206,214,.6)] hover:shadow-none"
            >
              <span>หน้าหลัก</span>
            </li>
            <li
              @click="
                activeDiv = 'Appoint';
                closeSidebar();
              "
              class="block py-2 px-4 text-sm cursor-pointer shadow-[0_1px_0px_0px_rgba(85,206,214,.6)] hover:shadow-none"
            >
              ข้อมูลจองคิวล่วงหน้า
            </li>
            <li
              @click="
                activeDiv = 'Daily';
                closeSidebar();
              "
              class="block py-2 px-4 text-sm cursor-pointer shadow-[0_1px_0px_0px_rgba(85,206,214,.6)] hover:shadow-none"
            >
              ข้อมูลเข้าใช้ช่องจอดประจำวัน
            </li>
            <li
              @click="
                activeDiv = 'CCTV';
                closeSidebar();
              "
              class="block py-2 px-4 text-sm cursor-pointer shadow-[0_1px_0px_0px_rgba(85,206,214,.6)] hover:shadow-none"
            >
              กล้องวงจรปิด (CCTV)
            </li>
            <li
              @click="
                activeDiv = 'Setting';
                closeSidebar();
              "
              class="block py-2 px-4 text-sm cursor-pointer shadow-[0_1px_0px_0px_rgba(85,206,214,.6)] hover:shadow-none"
            >
              ตั้งค่าการแจ้งเตือน
            </li>
            <li
              @click="
                activeDiv = 'QR';
                closeSidebar();
              "
              class="block py-2 px-4 text-sm cursor-pointer shadow-[0_1px_0px_0px_rgba(85,206,214,.6)] hover:shadow-none"
            >
              QR Code
            </li>
            <li
              @click="
                logout();
                closeSidebar();
              "
              class="block py-2 px-4 text-sm cursor-pointer shadow-[0_1px_0px_0px_rgba(85,206,214,.6)] hover:shadow-none"
            >
            ออกจากระบบ
            </li>
          </ul>
        </div>

        <!-- Web -->
        <div class="w-2/5 pl-3 pb-3 hidden sm:block md:w-2/5 lg:w-2/5 xl:w-1/5">
          <div
            class="w-full pl-3 pb-44 pt-3"
            style="
              background: linear-gradient(180deg, #27aec9 0%, #09ae9f 100%);
              border-radius: 30px;
            "
          >
            <img
              class="h-18 w-full object-cover md:h-full md:w-96"
              src="../assets/images/All-logo-04 1.svg"
            />
            <ul class="text-white pl-6 pt-3">
              <li
                @click="
                  activeDiv = 'Home';
                  closeSidebar();
                "
                :class="{'bg-white text-cyan-500 rounded-l-full': activeDiv === 'Home'}"
                class="pb-6 pt-6 pl-5 hover:text-cyan-500 hover:bg-white hover:rounded-l-full cursor-pointer"
              >
                <span>หน้าหลัก</span>
              </li>
              <li
                @click="
                  activeDiv = 'Appoint';
                  closeSidebar();
                "
                :class="{'bg-white text-cyan-500 rounded-l-full': activeDiv === 'Appoint'}"
                class="pb-6 pt-6 pl-5 hover:text-cyan-500 hover:bg-white hover:rounded-l-full cursor-pointer"
              >
                <span>ข้อมูลจองคิวล่วงหน้า</span>
              </li>
              <li
                @click="
                  activeDiv = 'Daily';
                  closeSidebar();
                "
                :class="{'bg-white text-cyan-500 rounded-l-full': activeDiv === 'Daily'}"
                class="pb-6 pt-6 pl-5 hover:text-cyan-500 hover:bg-white hover:rounded-l-full cursor-pointer"
              >
                <span> ข้อมูลเข้าใช้ช่องจอดประจำวัน </span>
              </li>
              <li
                @click="
                  activeDiv = 'CCTV';
                  closeSidebar();
                "
                :class="{'bg-white text-cyan-500 rounded-l-full': activeDiv === 'CCTV'}"
                class="pb-6 pt-6 pl-5 hover:text-cyan-500 hover:bg-white hover:rounded-l-full cursor-pointer"
              >
                <span class="text-base">กล้องวงจรปิด (CCTV)</span>
              </li>
              <li
                @click="
                  activeDiv = 'Setting';
                  closeSidebar();
                "
                :class="{'bg-white text-cyan-500 rounded-l-full': activeDiv === 'Setting'}"
                class="pb-6 pt-6 pl-5 hover:text-cyan-500 hover:bg-white hover:rounded-l-full cursor-pointer"
              >
                <span>ตั้งค่าการแจ้งเตือน</span>
              </li>
              <li
                @click="
                  logout();
                  closeSidebar();
                "
                class="pb-6 pt-6 pl-5 hover:text-cyan-500 hover:bg-white hover:rounded-l-full cursor-pointer"
              >
                <span>ออกจากระบบ</span>
              </li>
            </ul>
          </div>
        </div>

        <div class="mt-10 sm:mt-0 px-5 py-7 w-full h-full sm:px-4 sm:pb-3 sm:pt-0 z-0" >
          <div v-if="activeDiv === 'Home'">
            <ParkingHome />
          </div>
          <div v-if="activeDiv === 'Appoint'">
            <ParkingAppointment />
          </div>
          <div v-if="activeDiv === 'Daily'">
            <ParkingDaily/>
          </div>
          <div v-if="activeDiv === 'CCTV'">
            <ParkingCCTV />
          </div>
          <div v-if="activeDiv === 'Setting'">
            <ParkingSetting />
            </div>
          <div v-if="activeDiv === 'Logout'">
            ออกจากระบบ
          </div>
        </div>

      </div>
    </div>
  </div>
</template>



<script>
export default {
  data() {
    return {
      showSidebar: false,
      activeDiv: "Home",
    };
  },
  mounted() {},
  methods: {
    logout() {
      // perform the logout action, such as clearing local storage or sending a logout request to the server
      // then redirect the user to the login page
      this.$router.push('/login');
    },
    loadCCTVComponent() {
      console.log("1234");
      alert("หน้าหลัก"); // Load the CCTV component here
    },
    toggleSidebar() {
      this.showSidebar = !this.showSidebar;
    },
    closeSidebar() {
      this.showSidebar = false;
    },
  },
};
</script>

<style>
.navbar {
  position: fixed;
  top: 0;
  left: 0; 
  right: 0;
  z-index: 999;
  background-color: white;
  box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.2);

}

.system-content {
  font-family: 'Kanit', sans-serif;
}
</style>

