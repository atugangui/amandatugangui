<template>
  <div id="app">
    <!-- Top navbar -->
    <nav class="navbar navbar-expand-lg navbar-light">
      <div id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item" v-bind:class="{ active: view == 'home' }">
            <a class="nav-link" v-on:click="view = 'home'">home</a>
          </li>
          <li class="nav-item" v-bind:class="{ active: view == 'gallery' }">
            <a class="nav-link" v-on:click="view = 'gallery'">gallery</a>
          </li>
          <li class="nav-item" v-bind:class="{ active: view == 'about' }">
            <a class="nav-link" v-on:click="view = 'about'">about</a>
          </li>
          <li class="nav-item" v-bind:class="{ active: view == 'resume' }">
            <a class="nav-link" v-on:click="view = 'resume'">resume</a>
          </li>
          <li class="nav-item" v-bind:class="{ active: view == 'contact' }">
            <a class="nav-link" v-on:click="view = 'contact'">contact</a>
          </li>
        </ul>
      </div>
    </nav>
    <!-- /Top navbar-->

    <!-- Main views -->
    <Home v-if="view === 'home'" />
    <About v-if="view === 'about'" />
    <Resume v-if="view === 'resume'" />
    <Contact v-if="view === 'contact'" />
    <Gallery v-if="view === 'gallery'" />
    <!-- /Main views -->
  </div>
</template>

<script>
import Home from './components/Home.vue'
import About from './components/About.vue'
import Resume from './components/Resume.vue'
import Contact from './components/Contact.vue'
import Gallery from './components/Gallery.vue'

export default {
  name: 'App',
  components: {
    Home,
    About,
    Resume,
    Contact,
    Gallery,
  },
  data() {
    return {
      view: 'home'
    }
  }
}
</script>

<style lang="scss">
@import "~@/assets/scss/vendors/bootstrap-vue/index";
@import url('https://fonts.googleapis.com/css2?family=Jost&display=swap');

html,
body {
  min-height: 100%;
  height: 100%;
  font-family: 'Jost', sans-serif;
}

#app {
  font-family: 'Jost', Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100%;
}

/*.navbar {
  height: 10vh;
}*/

#navbarSupportedContent {
  margin-left: auto;
}

.customBtnDesign {
  border: solid rgb(250, 140, 107) 2px;
  border-radius: 0px;
  padding-left: 30px;
  padding-right: 30px;
  padding-top: 10px;
  padding-bottom: 10px;
}

a {
  color: #42b983;
}

a:hover {
  color: #42b983;
}

.nonGalleryImage {
  vertical-align: unset;
  height: 100%;
  width: 100%;
  object-fit: contain;
}


@media (min-width: 1366px) {
  body {
    font-size: 1.2rem;
  }
}

@media (min-width: 1920px) {
  .container {
    max-width: 1828px;
  }
  .navbar {
    font-size: 1.5rem;
  }
  body {
    font-size: 1.5rem;
  }
}

.v-lazy-image {
  opacity: 0;
  transform: translate3d(0, 50%, 0);
  transition: opacity 0.5s, transform 0.5s;
}
.v-lazy-image-loaded {
  opacity: 1;
  transform: translate3d(0, 0, 0);
}
</style>
