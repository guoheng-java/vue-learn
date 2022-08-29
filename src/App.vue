<script>
// <script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
export default{
  data() {
    return {
      num: 2,
      uname:"郭恒",
      msg:"<h2>达丰V大夫是的</h2>",
      id:"d1",
      url:"https://pdai.tech/_images/index-read.gif",
      attributegh:'id'
    };
  },
  methods: {
    changename: function(){
      this.uname='东方闪电'
    },
    changecolor: function(){
      this.id="d2"
    }
  },

};
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <!-- <HelloWorld msg="You did it!" /> -->
      <p>{{num}}</p>
      <p>{{uname}}</p>
      <p v-once>{{uname}}</p>
      <p>{{msg}}</p>
      <p v-html="msg"></p>
      <button @click="changename">更改名字</button>

      <p v-bind:id="id">是你的讲课呢</p>
      <img v-bind:src="url">
      <button @click="changecolor">改变颜色</button>
      <button @click="id ='d2'">改变颜色</button>
      <p>{{num+1}}</p>
      <p>{{uname.split('').reverse().join('')}}</p>
      <!-- v-bond 语法糖 :-->
      <p :id="id">是你的讲课呢</p>
      <!-- v-on 用于监听DOM事件 -->
      <button v-on:click="changecolor">改变颜色</button>
      <!-- v-on 语法糖 @-->
      <button @click="changecolor">改变颜色</button>
      <!-- 动态参数 -->
      <!-- 动态属性 -->
      <p v-bind:[attributegh]=id>v-bind 绑定</p>
      <button @click="attributegh = 'class'">改变</button>

    </div>
  </header>

  <!-- <main>
    <TheWelcome />
  </main> -->
</template>

<style scoped>
header {
  line-height: 1.5;
}
#d1{
  color: blue;
}
#d2{
  color: red;
}
.d1{
  font-size: 50px;
}
.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
