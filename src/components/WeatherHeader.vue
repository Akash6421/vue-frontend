<template>
  <div>
    <h1>{{ greeting }}</h1>
    <h2>{{ projectTitle }}</h2>
    <h4>{{ serverName }}</h4>
  </div>
</template>

<script>
export default {
  name: 'WeatherHeader',
  props: { 

        projectTitle:String,
        serverName:String,
        greeting: String
    }
};
</script>

<style scoped>
div {
  text-align: center;
}
</style>
