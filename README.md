1.Vue介绍
    Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式框架。与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用提供驱动。
2.安装：
    npm install -g @vue/cli        3.x
        vue create my-project
    npm install -g @vue/cli-init   2.x
        vue init webpack my-project
3.项目结构
    插件：Vetur
4.API
    1.模板语法
        插值:{{ msg }}  data中声明  可以识别单行表达式
        原始HTML:<p v-html="room"></p>
        特性:v-bind:
        v-once
        缩写：
            v-on  ->  @
            v-bind:  -> :
    2.条件渲染
        v-if v-if-else v-else
        在<template> 元素上使用 v-if 条件渲染分组
        v-show
        v-if和v-show的区别：
            v-if 是“真正”的条件渲染，因为它会确保在切换过程中条件块内的事件监听器和子组件适当地被销毁和重建。
            v-if 也是惰性的：如果在初始渲染时条件为假，则什么也不做——直到条件第一次变为真时，才会开始渲染条件块。
            相比之下，v-show 就简单得多——不管初始条件是什么，元素总是会被渲染，并且只是简单地基于 CSS 进行切换。
            一般来说，v-if 有更高的切换开销，而 v-show 有更高的初始渲染开销。因此，如果需要非常频繁地切换，则使用 v-show 较好；如果在运行时条件很少改变，则使用 v-if 较好。
    3.列表渲染
        数组 v-for="(item,index) in names"
        对象 v-for="(value,key,index) in obj"
        数组更新检测
            变异方法 (mutation method)
            替换数组
        对象更新检测
            Vue.set(object, propertyName, value)
    4.事件处理
        v-on指令
        内联处理器中的方法(事件传递参数)
            <button v-on:click="addCountHandler(5,$event)">按钮</button>
        事件修饰符
            <button v-on:click.prevent="send">发送</button>
    5.计算属性和侦听器
        computed
            computed vs methods的区别
                我们可以将同一函数定义为一个方法而不是一个计算属性。两种方式的最终结果确实是完全相同的。然而，不同的是计算属性是基于它们的响应式依赖进行缓存的。只在相关响应式依赖发生改变时它们才会重新求值。这就意味着只要 message 还没有发生改变，多次访问 reversedMessage 计算属性会立即返回之前的计算结果，而不必再次执行函数。
    6.Class 与 Style 绑定
        绑定 HTML Class
            对象语法
                <p :class="{active:isActive,'text-danger':hasError}">hello</p>
            数组语法
                <p :class="[c1,c2]">我是样式</p>
                <p :class="[isActive ? 'active' :'',c1]">我是样式2</p>
            对象数组合并语法
                <p :class="[isActive ? 'active' :'',{'text-danger':hasError},c2]">我是样式3</p>
        绑定内联样式
            对象语法
                <p :style="{color:'green',fontSize:'30px'}">style1</p>
            数组语法
                <div v-bind:style="[baseStyles, overridingStyles]"></div>
        自动添加前缀
    7.表单输入绑定
        v-model指令
        修饰符
        双向数据绑定的原理：
            参考地址：https://www.cnblogs.com/zhuzhenwei918/p/7309604.html
    8.组件
        vue单文件组件后缀名为.vue
        组件由三个部分组成：template  script  style
        template:
            只能存在一个跟组件
        script:
            data必须是一个纯函数
        scoped:
            增加scoped属性，样式只能在当前组件中生效
        组件的引入：
            1.引入
            2.依赖注入
            3.加载
        组件的复用
            因为你每用一次组件，就会有一个它的新实例被创建。
        通过 Prop 向子组件传递数据
            读取：props:[key]
            Prop 验证
