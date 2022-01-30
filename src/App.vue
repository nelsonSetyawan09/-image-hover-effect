<template>
  <div id="app">
    <h2>Image Effect</h2>
    <hr>
    <ImageAnimation/>
  </div>
</template>

<script>
import ImageAnimation from './components/Index.vue'

export default {
  name: 'App',
  components: {
    ImageAnimation
  }
}
</script>

<style>
body{
  padding: 0;
  margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
