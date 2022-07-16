<template>
  <div id="app">
    <nav class="navbar navbar-expand-lg navbar-light">
      <div id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item" v-bind:class="{ active: view == 'home' }">
            <a class="nav-link" v-on:click="view = 'home'">Home</a>
          </li>
          <li class="nav-item" v-bind:class="{ active: view == 'about' }">
            <a class="nav-link" v-on:click="view = 'about'">About</a>
          </li>
          <li class="nav-item" v-bind:class="{ active: view == 'resume' }">
            <a class="nav-link" v-on:click="view = 'resume'">Resume</a>
          </li>
          <li class="nav-item" v-bind:class="{ active: view == 'contact' }">
            <a class="nav-link" v-on:click="view = 'contact'">Contact</a>
          </li>
        </ul>
      </div>
    </nav>
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld v-if="view === 'home'" msg="Welcome to Your Vue.js App" />
    <About v-if="view === 'about'" msg="About"></About>
    <Resume v-if="view === 'resume'" msg="Resume"></Resume>
    <Contact v-if="view === 'contact'" msg="Contact"></Contact>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import About from './components/About.vue'
import Resume from './components/Resume.vue'
import Contact from './components/Contact.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    About,
    Resume,
    Contact
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
}

#navbarSupportedContent {
  margin-left: auto;
}
</style>
