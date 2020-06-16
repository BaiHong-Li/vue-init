<template>

  <div>
    {{title}}-{{age}}
    {{friends}}
  </div>
</template>

<script>
    export default {
        name: "MyComponent2.vue",
      data(){
          return{

          }
      },
      props:{
        title:{
          type:[String,Number],
          required:true
        },
        age:{
          type:Number,
          default:1
        },
        friends:{
          type:Array,
          default:function(){
            return ["0"]
          }
        }
      }
    }
</script>

<style scoped>

</style>
