<template>
  <div id="app">
    <img src="./assets/logo.png">
    <!--绑定数据两种方法 1.{{}}} 2.v-text-->
    <h1>{{ msg }}</h1>
    <p v-text="test_p"></p>
    <h3>{{obj.name}}</h3>
    <!--循环：v-for-->
    <ul>
      <li v-for="item in list">
        {{item}}
      </li>
    </ul>

    <!--v-bind 绑定属性，例如img的src、div的title等，v-bind:可以简写成:-->
    <!-- v-bind绑定数据的时候是从data中获得数据时，才使用冒号，不绑定data数据时不用加冒号-->
    <div v-bind:title="title">鼠标放这里</div>
    <img v-bind:src="imgUrl"/>

    <div class="red"></div>
    <!--v-html 绑定html，将data中的html标签语言解析-->
    <div v-html="h2"></div>

  </div>
</template>

<script>//js业务逻辑
export default {//默认写法将该组件暴漏出去
  name: 'app',//给组件起名字
  data () {//业务逻辑里面定义的数据
    return {
      msg: 'Welcome to Your Vue.js App',//绑定数据，在DOM中{{msg}}调用
      test_p: "这是一段测试段落，啦啦啦啦～～～～～～",
      obj:{//对象，可以定义一组数据
        name:"我叫VUE",
      },
      list:["111", "222", "333"],
      imgUrl:"http://localhost:8080/dist/logo.png?82b9c7a5a3f405032b1db71a25f67021",
      title:"这是一个提示",
      h2: "<h2>这是H2标题</h2>>"
    }
  }
}
</script>

<style>
  .red{
    color:red;
  }
/*#app {*/
  /*font-family: 'Avenir', Helvetica, Arial, sans-serif;*/
  /*-webkit-font-smoothing: antialiased;*/
  /*-moz-osx-font-smoothing: grayscale;*/
  /*text-align: center;*/
  /*color: #2c3e50;*/
  /*margin-top: 60px;*/
/*}*/

/*h1, h2 {*/
  /*font-weight: normal;*/
/*}*/

/*ul {*/
  /*list-style-type: none;*/
  /*padding: 0;*/
/*}*/

/*li {*/
  /*display: inline-block;*/
  /*margin: 0 10px;*/
/*}*/

/*a {*/
  /*color: #42b983;*/
/*}*/
</style>
