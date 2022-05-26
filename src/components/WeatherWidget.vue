<script>
export default {
  data() {
    return {
      weather: this.getWeather(),
    };
  },
  methods: {
    async getWeather() {
      let url = "https://api.weatherbit.io/v2.0/current?city=Seattle,Washington&key=867ecdcbd85c48dcb8d16ccb01d92f45";
      await fetch(url)
        .then((response) => response.json())
        .then((data) => {
          console.log(data.data[0]);
          this.weather = data.data[0];
        })
        .catch((error) => console.log(error));
    }
  },
}
</script>
<template>
  <div class="container">
    <h1>{{ weather.city_name }}</h1>
    <h3>Temperature: {{ weather.temp }}°C</h3>
    <h3>Feels like: {{ weather.app_temp }}°C</h3>
    <h3>Wind direction: {{weather.wind_dir}}</h3>
    <h4>Coordinates: {{weather.lat}}, {{weather.lon}} (lat,lon)</h4>
  </div>
</template>

<style scoped>

</style>