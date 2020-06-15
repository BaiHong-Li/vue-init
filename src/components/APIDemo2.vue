<template>
  <div>
    <textarea v-model="msg"></textarea>
    <p>{{msg}}</p>
    <input type="checkbox" id="jack" value="Jack" v-model="checkeds">
    <input type="checkbox" id="john" value="John" v-model="checkeds">
    <input type="checkbox" id="mike" value="Mike" v-model="checkeds">
    <p>{{checkeds}}</p>
    <ul>
      <li v-for="(item,index) in checkeds" :key="index">{{item}}</li>
    </ul>
  </div>
</template>

<script>
    export default {
      name: "APIDemo2.vue",
      data(){
        return{
          msg:"",
          checkeds:[]
        }
      }
    }
</script>

<style scoped>

</style>
