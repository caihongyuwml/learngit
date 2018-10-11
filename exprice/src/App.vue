<!--页面级Vue组件-->
<template>
  <div id="app">
    <!--头部Header-->
    <Header></Header>
    <!--侧边栏列表-->
    <side-bar></side-bar>
  </div>
</template>

<script>
  import Header from './components/header.vue'
  import sidebar from './components/sidebar.vue'
export default {
  name: 'App',
  data(){
    return{

    }
  },
  methods:{

  },
  components:{
    "Header":Header,
    "side-bar":sidebar
  }
}
</script>
<style>
@import "font-icon/style.css";
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
