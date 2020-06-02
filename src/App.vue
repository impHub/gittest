<template>
  <div id="app">
    <!--  -->
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <p>姓名{{apis.name}}</p>
    <p>qq:{{apis.qq}}</p>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data(){
    return {
      apis:{}
    }
  },
  created(){
    axios.get(`/api/datas`)
      .then(res=>{
        console.log(res)
        this.apis = res.data
      })
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
