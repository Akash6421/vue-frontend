<template>
  
  <div id="app">
    <WeatherHeader greeting = "Hello" projectTitle = "This is a Weather Application" serverName = "Developed by Akash Reddy"/>
    <WeatherDisplay :weatherData="weatherData" />
    <!-- <button @click="fetchWeatherData">Fetch Weather Data</button> -->
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
      weatherData: {},
    };
  },
  methods: {
  async fetchWeatherData() {
    try {
      const response = await fetch("https://weatherinfo-akash.onrender.com/api/weather");
      const data = await response.json();
      console.log(data);

      return data.weather.map(entry => {
        return {
          _id: entry._id,
          weather: entry.weather.map(cityWeather => {
            return {
              id: cityWeather.id,
              city: cityWeather.city,
              temperature: cityWeather.temperature,
              humidity: cityWeather.humidity,
              weather: cityWeather.weather
            };
          })
        };
      });
    } catch (error) {
      console.error("Error fetching weather data:", error);
      return [];
    }
  }
},
async created(){
  this.weatherData = await this.fetchWeatherData();
}
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Montserrat', sans-serif;
}
.container {
  max-width: 400px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 0.3em solid black;
  padding: 30px;
  border-radius: 5px;
}

div{
  margin-bottom: 0.5em;

}
</style>