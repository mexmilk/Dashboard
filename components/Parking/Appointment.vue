<template>
  <div>
    <p class="">รายการจองคิวล่วงหน้า (10 รายการ)</p>
    <div
      class="mt-4 justify-between flex text-[#8C8B9D] p-2 md:px-7 text-center"
    >
      <div class="flex item-center justify-center min-h-[80vh] w-full bg-white">
        <div class="w-full h-[5/6] overflow-hidden bg-teal-50 shadow-xl">
          <Calendar @eventClick="eventClick" />
        </div>
      </div>
    </div>
    <ModalCalendar  v-if="showModal" @closeModal="closeModal"/>
  </div>
</template>

<script>
import Calendar from "./Calendar.vue";
import ModalCalendar from "./ModalCalendar.vue";

export default {
  components: {
    Calendar,
    ModalCalendar,
  },
  data() {
    return {
      showModal: false,
    };
  },

  methods: {
    eventClick(arg) {
      this.$data.showModal = true
      console.log("Hello: ", arg);
    },

    closeModal() {
      this.$data.showModal = false
    },
  },
};
</script>
