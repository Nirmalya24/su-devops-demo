<script>
import Giphy from "@/components/Giphy.vue";

export default {
  data() {
    return {
      today: this.getToday(),
    };
  },
  methods: {
    getToday() {
      let days = [
        "Sunday",
        "Monday",
        "Tuesday",
        "Wednesday",
        "Thursday",
        "Friday",
        "Saturday",
      ];
      let d = new Date().getDay();
      return days[d];
    },
  },
  components: { Giphy },
};
</script>

<template>
  <div class="container">
    <h1>Today is {{ today }}!</h1>
    <Giphy :query-string="today" />
  </div>
</template>

<style>
.container {
  display: flex;
  align-items: center;
  flex-direction: column;
  align-self: center;
  place-items: center;
  place-content: center;
}
</style>
