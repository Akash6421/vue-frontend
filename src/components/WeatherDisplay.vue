<template>
  <div>
    <div v-for="weatherEntry in weatherData" :key="weatherEntry._id">
      <div v-for="cityWeather in weatherEntry.weather" :key="cityWeather.id">
        <WeatherItem :weatherItem="cityWeather" />
      </div>
    </div>
  </div>
</template>

<script>
import WeatherItem from './WeatherItem.vue';

export default {
  name: 'WeatherDisplay',
  props: {
    weatherData: Array
  },
  components: {
    WeatherItem
  }
};
</script>

<style scoped>
</style>
