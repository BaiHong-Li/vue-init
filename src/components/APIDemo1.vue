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
            hasError:true
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
            this.$set(this.obj,"zhaoyun","男");
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
