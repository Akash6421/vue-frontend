<template>
  
  <div id="app">
    <WeatherHeader greeting = "Hello" projectTitle = "This is a Weather Application" serverName = "The Server is deployed in Render"/>
    <WeatherDisplay :weatherData="weatherData" />
    <button @click="fetchWeatherData">Fetch Weather Data</button>
  </div>
</template>

<script>
import WeatherHeader from "./components/WeatherHeader.vue"
import WeatherDisplay from "./components/WeatherDisplay.vue"


export default {
  name: "App",
  components: {
    WeatherDisplay,
    WeatherHeader
  },
  data() {
    return {
      weatherData: null,
    };
  },
  methods: {
    async fetchWeatherData() {
      try {
        const response = await fetch("https://weatherinfo-akash.onrender.com/api/weather");
        if (!response.ok) {
          throw new Error(`HTTP error! Status: ${response.status}`);
        }
        this.weatherData = (await response.json()).weather;
      } catch (error) {
        console.error("Error fetching weather data:", error.message);
      }
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>