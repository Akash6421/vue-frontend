<template>
  <div>
    <h2>{{ weatherItem.city }}</h2>
    <h4>{{ weatherItem.temperature }}</h4>
    <h4>{{ weatherItem.humidity }}</h4>
    <h4>{{ weatherItem.weather }}</h4>
  </div>
</template>

<script>
export default {
  name: 'WeatherItem',
  props: {
    weatherItem: Array
  }
};
</script>

<style scoped>
.green {
  background-color: green;
}

h4 {
  margin: 2px;
}

div {
  background-color: #ffb89e;
  color: black;
  padding: 1em;
  text-align: center;
  width: 80%;
  margin: auto;
}

.red {
  background-color: orangered !important;
}
</style>
