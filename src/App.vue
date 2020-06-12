<template>
  <div id="app">
    <APIDemo1/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import APIDemo1 from './components/APIDemo1'

export default {
  name: 'App',
  components: {
    HelloWorld,
    APIDemo1
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
