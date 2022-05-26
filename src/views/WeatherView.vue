<script>
import WeatherWidget from "@/components/WeatherWidget.vue";
import Giphy from "@/components/Giphy.vue";
export default {
  data() {
    return {
      today: this.getToday(),
    };
  },
  methods: {
    getToday() {
      const d = new Date();
      let day = d.getDay();
      let weekdays = [
        "Sunday",
        "Monday",
        "Tuesday",
        "Wednesday",
        "Thursday",
        "Friday",
        "Saturday",
      ];
      return weekdays[day];

    },
  },
  components: {
    WeatherWidget,
    Giphy,
  },
  
};
</script>

<template>
  <div class="container">
    <h1>This is an weather page</h1>
    <WeatherWidget />
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
