<template>
    <div class="hello">
      <button @click="sendDataHandler">send</button>
      <input type="text" v-model="message" @change="msgChange">
      <p>{{ message }}</p>
    </div>
</template>

<script>
    export default {
        name: "HelloWorld2",
      data(){
          return{
            msg: "hehehe",
            message: ""
          }
      },
      methods:{
        sendDataHandler() {
          this.$emit("myEvent", this.msg);
        },
        msgChange(){
          this.$emit("myChange",this.message)
        }
      },
      props: {
        title: {
          type: String,
          default: "hello"
        }
      },
      watch: {
        message(value) {
          this.$emit("myChange", value);
        }
      }
    }
</script>

<style scoped>

</style>
