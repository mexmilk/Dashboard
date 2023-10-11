<!-- Please remove this file from your project -->
<template>
  <div
    class="max-w-md mx-auto bg-white rounded-xl shadow-md overflow-hidden md:max-w-3xl"
  >
    <div class="md:flex">
      <div class="md:shrink-0 relative">
        <img
          class="h-80 w-full object-cover md:h-full md:w-96"
          src="../../assets/images/imglogin.svg"
        />
        <div
          class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 text-center"
        >
          <div class="text-left">
            <span class="text-white text-5xl sm:text-6xl">Welcome</span><br />
            <span class="text-white text-xl font-extralight"
              >To Parking Dashboard</span
            ><br />
            <div class="bg-white col-span-1 border-t my-2"></div>
            <span class="text-white font-extralight text-xs sm:text-base"
              >ระบบบริหารจัดการที่จอดรถอัจฉริยะ</span
            >
          </div>
        </div>
      </div>
      <div class="rounded-md">
        <div class="p-8">
          <div class="justify-center items-center text-center flex mx-auto">
            <img class="h-16 sm:h-20" src="../../assets/images/logo.svg" />
            <div class="text-3xl sm:text-5xl">
              <span class="font-light"
                >Planet<span class="font-normal text-lime-500">EV</span></span
              >
            </div>
          </div>
          <form>
            <div class="relative mb-4 mt-20" data-te-input-wrapper-init>
              <input
                style="border: 1px solid #1ab6c1"
                class="w-full sm:w-64 md:w-80 lg:w-90 py-2 px-4 rounded-md bg-gray-50 focus:bg-white focus:outline-none focus:ring-2 focus:ring-cyan-300 text-cyan-600"
                placeholder="Username"
                v-model="username"
              />
            </div>
            <div class="relative mb-1" data-te-input-wrapper-init>
              <input
                style="border: 1px solid #1ab6c1"
                class="w-full sm:w-64 md:w-80 lg:w-90 py-2 px-4 rounded-md bg-gray-50 focus:outline-none focus:ring-2 focus:ring-cyan-300 text-cyan-600"
                placeholder="Password"
                :type="showPassword ? 'text' : 'password'"
                v-model="password"
              />
              <label
                class="absolute inset-y-0 right-0 flex items-center pr-3 cursor-pointer"
                @click="showPassword = !showPassword"
              >
                <svg
                  :class="{
                    'text-cyan-600': !showPassword,
                    'text-[#1ab6c1]': showPassword,
                  }"
                  xmlns="http://www.w3.org/2000/svg"
                  width="16"
                  height="16"
                  fill="currentColor"
                  class="bi bi-eye-slash w-5 h-5"
                  viewBox="0 0 16 16"
                >
                  <path
                    :class="{ hidden: showPassword }"
                    d="M13.359 11.238C15.06 9.72 16 8 16 8s-3-5.5-8-5.5a7.028 7.028 0 0 0-2.79.588l.77.771A5.944 5.944 0 0 1 8 3.5c2.12 0 3.879 1.168 5.168 2.457A13.134 13.134 0 0 1 14.828 8c-.058.087-.122.183-.195.288-.335.48-.83 1.12-1.465 1.755-.165.165-.337.328-.517.486l.708.709z"
                  />
                  <path
                    :class="{ hidden: showPassword }"
                    d="M11.297 9.176a3.5 3.5 0 0 0-4.474-4.474l.823.823a2.5 2.5 0 0 1 2.829 2.829l.822.822zm-2.943 1.299.822.822a3.5 3.5 0 0 1-4.474-4.474l.823.823a2.5 2.5 0 0 0 2.829 2.829z"
                  />
                  <path
                    :class="{ hidden: showPassword }"
                    d="M3.35 5.47c-.18.16-.353.322-.518.487A13.134 13.134 0 0 0 1.172 8l.195.288c.335.48.83 1.12 1.465 1.755C4.121 11.332 5.881 12.5 8 12.5c.716 0 1.39-.133 2.02-.36l.77.772A7.029 7.029 0 0 1 8 13.5C3 13.5 0 8 0 8s.939-1.721 2.641-3.238l.708.709zm10.296 8.884-12-12 .708-.708 12 12-.708.708z"
                  />

                  <path
                    :class="{ hidden: !showPassword }"
                    d="M16 8s-3-5.5-8-5.5S0 8 0 8s3 5.5 8 5.5S16 8 16 8zM1.173 8a13.133 13.133 0 0 1 1.66-2.043C4.12 4.668 5.88 3.5 8 3.5c2.12 0 3.879 1.168 5.168 2.457A13.133 13.133 0 0 1 14.828 8c-.058.087-.122.183-.195.288-.335.48-.83 1.12-1.465 1.755C11.879 11.332 10.119 12.5 8 12.5c-2.12 0-3.879-1.168-5.168-2.457A13.134 13.134 0 0 1 1.172 8z"
                  />

                  <path
                    :class="{ hidden: !showPassword }"
                    d="M8 5.5a2.5 2.5 0 1 0 0 5 2.5 2.5 0 0 0 0-5zM4.5 8a3.5 3.5 0 1 1 7 0 3.5 3.5 0 0 1-7 0z"
                  />
                </svg>
              </label>
            </div>
            <div v-if="error" class="text-red-500 mb-4">{{ error }}</div>
            <div class="relative mb-4" data-te-input-wrapper-init>
              <label class="md:w-2/3 block text-gray-500">
                <input
                  class="mr-2 leading-tight text-cyan-600 focus:ring-cyan-300"
                  type="checkbox"
                  v-model="rememberMe"
                />
                <span class="text-sm"> Remember me </span>
              </label>
            </div>
            
            <div class="mb-12 pt-4 pb-1 text-center">
              <button
                @click.prevent="handleLogin()"
                class="bg-gradient-to-b from-cyan-500 to-teal-400 mb-3 inline-block w-full rounded px-6 pt-2.5 pb-2 text-xs font-medium uppercase leading-normal text-white shadow-[0_4px_9px_-4px_rgba(0,0,0,0.2)] transition duration-150 ease-in-out hover:shadow-[0_8px_9px_-4px_rgba(0,0,0,0.1),0_4px_18px_0_rgba(0,0,0,0.2)] focus:shadow-[0_8px_9px_-4px_rgba(0,0,0,0.1),0_4px_18px_0_rgba(0,0,0,0.2)] focus:outline-none focus:ring-0 active:shadow-[0_8px_9px_-4px_rgba(0,0,0,0.1),0_4px_18px_0_rgba(0,0,0,0.2)]"
                type="submit"
              >
                เข้าสู่ระบบ
              </button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "NuxtTutorial",
  data() {
    return {
      account: {
        user: "planetev",
        pass: "1234",
      },
      username: "",
      password: "",
      showPassword: false,
      rememberMe: false,
      error: "",
    };
  },
  mounted() {
    // Load saved username and password from localStorage
    const savedUsername = localStorage.getItem("username");
    const savedPassword = localStorage.getItem("password");
    if (savedUsername && savedPassword) {
      this.username = savedUsername;
      this.password = savedPassword;
      this.rememberMe = true;
    }
  },
  methods: {
    handleLogin() {
      if (
        this.username === this.account.user &&
        this.password === this.account.pass
      ) {
        // If "Remember me" checkbox is checked, save the username and password to localStorage
        if (this.rememberMe) {
          localStorage.setItem("username", this.username);
          localStorage.setItem("password", this.password);
        } else {
          // If "Remember me" checkbox is not checked, remove the saved username and password from localStorage
          localStorage.removeItem("username");
          localStorage.removeItem("password");
        }
        this.login();
      } else {
        this.error = "Invalid username or password";
      }
    },
    login() {
      this.$router.push("/system");
    },
  },
};
</script>
