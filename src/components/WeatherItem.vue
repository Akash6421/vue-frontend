<template>
  <div class="weather-item">
    <div>
      <strong>City:</strong> {{ weatherItem.city }}
    </div>
    <div>
      <strong>Temperature:</strong> {{ weatherItem.temperature }}
    </div>
    <div>
      <strong>Humidity:</strong> {{ weatherItem.humidity }}
    </div>
    <div>
      <strong>Weather:</strong> {{ weatherItem.weather }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'WeatherItem',
  props: {
    weatherItem: Object
  }
};
</script>

<style scoped>
.weather-item {
  background-color: coral;
  color: black;
  padding: 1em;
  text-align: center;
  width: 50%;
  margin: auto;
}
</style>
