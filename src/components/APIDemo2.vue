<template>
  <div>
    <input class="text" v-model="msg">
    <p>{{msg}}</p>
    <input type="checkbox" v-model="checked">
    <p>{{checked}}</p>
  </div>
</template>

<script>
    export default {
      name: "APIDemo2.vue",
      data(){
        return{
          msg:"",
          checked:true
        }
      }
    }
</script>

<style scoped>

</style>
