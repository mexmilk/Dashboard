<template>
    <FullCalendar :options="calendarOptions"/>
</template>

<script>
import FullCalendar from "@fullcalendar/vue";
import dayGridPlugin from "@fullcalendar/daygrid";
import interactionPlugin from "@fullcalendar/interaction";

export default {
  components: {
    FullCalendar,
  },
  data() {
    return {
      calendarOptions: {
        plugins: [dayGridPlugin, interactionPlugin],
        initialView: "dayGridMonth",
        headerToolbar: {
          left: "prev",
          center: "title",
          right: "next",
        },
        dateClick: this.handleDateClick,
        eventClick: this.handleEventClick,
        events: [
          { title: '2 รายการ', date: '2023-09-30' },
          { title: '1 รายการ', date: '2023-10-01' }
        ]
      },
    };
  },

  methods: {
    handleDateClick: function(arg) {
      
    },

    handleEventClick(clickInfo) {
        this.$emit('eventClick', clickInfo)
    },
  },
};
</script>

<style>
.fc {
  max-width: 1100px;
  max-height: 700px;
}


#fc-dom-1 {
  color: #26afc8;
}

</style>
