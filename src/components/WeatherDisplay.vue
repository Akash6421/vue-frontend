<template>
  <div>
    <WeatherItem v-for="weatherItem of weatherData" :key="weatherItem.id" :weatherItem="weatherItem" />
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
