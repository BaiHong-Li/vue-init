<template>
  <div id="app">
    <ul>
      <li v-for="(item,index) in names" :key="index">
        <MyComponent :name="item"/>
      </li>
    </ul>
    <MyComponent2 title="name":age="20":friends="fs"></MyComponent2>

    <HelloWorld2></HelloWorld2>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import APIDemo1 from './components/APIDemo1'
import APIDemo2 from './components/APIDemo2'
import MyComponent from './components/MyComponent'
import MyComponent2 from './components/MyComponent2'
import HelloWorld2 from "./components/HelloWorld2";

export default {
  name: 'App',
  components: {
    HelloWorld,
    APIDemo1,
    APIDemo2,
    MyComponent,
    MyComponent2,
    HelloWorld2
  },
  data(){
    return{
      names:["iwen","ime","frank"],
      fs:["18","19","20"]
    }
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
