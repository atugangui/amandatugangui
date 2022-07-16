<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld v-if="view==='home'" msg="Welcome to Your Vue.js App"/>
    <About v-if="view === 'about'" msg="About"></About>
    <a v-on:click="view='about'">About</a>
    <a v-on:click="view='home'">Home</a>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import About from './components/About.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    About
  },
  data() {
    return {
      view: 'home'
    }
  },
}
</script>

<style lang="scss">
@import "~@/assets/scss/vendors/bootstrap-vue/index";
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
