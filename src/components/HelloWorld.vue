<template>
  <div>
      {{msg}}
      <p v-html="room"></p>
      <a v-bind:href="links.url">{{links.title}}</a>
      <a v-bind:data_id="id"></a>
      <a v-bind:class="myactive">哈哈哈哈</a>
      <a>{{10>20 ? "错误":"正确"}}</a>
      <p>{{ msg.split('').reverse().join('')}}</p>
      <div>
        <p v-if="flag">孙悟空</p>
        <p v-else>六耳猕猴</p>
      </div>
      <p v-show="flag">九尾妖狐</p>
      <ul>
        <li v-for="(skill,index) in names" v-bind:key="index">{{skill}}</li>
      </ul>
      <ul>
        <li v-for="(vlaue,name,index) in obj" v-bind:key="index">{{name}}:{{vlaue}}-{{index}}</li>
      </ul>
      <div>
        <p>{{count}}</p>
        <button v-on:mouseover="addcounthandler()">按钮 </button>
      </div>
  </div>
 
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg:"hello world",
      room:"<h3>房间号</h3>",
      flag:false,
      myactive:"active",
      id:"618",
      links:{
        title:"baidu",
        url:"https://www.baidu.com/"
      },
      names:["Q","W","E","R"],
      obj:{
        name:"lbh",
        sex:"man",
        age:"24"
      },
      count:0
    }
  },
  methods:{
    addcounthandler(){
      this.count+=1;
    }
  }
}
</script>
