<template>
    <div>
        <p>{{count}}</p>
        <a :href="url">baidu</a><br>
        <button @click="setcounthandler">按钮</button>
        <ul>
            <li v-for="(value,index) in names" :key="index">{{value}}</li>
        </ul>
        <button @click="addname">添加</button>
        <div>
            <ul>
                <li v-for="(value,key,index) in obj"  :key="index">{{key}}:{{value}}</li>
            </ul>
        </div>

        <button @click="addobj">添加object</button>
        <div>
            {{ getmsg }}
        </div>
        <div>
          <p :class="{active:isActive,'text-danger':hasError}">hello</p>
          <button @click="changeISActive">修改</button>
        </div>
        <div>
          <p class="s1" :class="[c1,c2]">我是样式</p>
          <p class="s2" :class="[isActive ? 'active' :'',c1]">我是样式2</p>
          <p class="s3" :class="[isActive ? '' :'active',{'text-danger':hasError},c2]">我是样式3</p>
        </div>
        <div>
          <p :style="{color:'green',fontSize:'30px'}">style1</p>
        </div>
    </div>
</template>
<script>
export default {
     name: 'APIDemo1',
    data(){
        return{
            count:10,
            url:"https://www.baidu.com/",
            names:["xiaohong","xiaoming","xiaozhang"],
            obj:{
                name:"zhangfei",
                age:"20"
            },
            msg:"hello",
            isActive:true,
            hasError:true,
            c1:"s1",
            c2:'s2'
        }
    },
    methods:{
        setcounthandler(){
            this.count+=1;
        },
        addname(){
            this.names.push("lbh");
        },
        addobj(){
            this.$set(this.obj,"sex","男");
        },
        changeISActive(){
          this.isActive = !this.isActive;
        }
    },
    computed:{
        getmsg(){
            return this.msg.split("").reverse().join("");
        }
    }
}
</script>
<style scoped>

  .active{
    color: red;
  }

</style>
