<template>
  <div id="app">
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <a class="navbar-brand" href="#">Navbar</a>

      <div id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item active">
            <a class="nav-link" v-on:click="view = 'home'">Home <span class="sr-only">(current)</span></a>
          </li>
          <li class="nav-item">
            <a class="nav-link" v-on:click="view = 'about'">About</a>
          </li>
        </ul>
      </div>
    </nav>
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld v-if="view === 'home'" msg="Welcome to Your Vue.js App" />
    <About v-if="view === 'about'" msg="About"></About>
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
