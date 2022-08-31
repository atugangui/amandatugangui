<template>
  <div id="app">
    <!-- Top navbar -->
    <template v-if="isMobile">
      <!-- Top Navigation Menu -->
      <div class="topnav">
        <div id="buttonDiv">
        <button v-on:click=" listIsHidden= !listIsHidden " class="btn customHamburger customBtnDesign">
          <BIconList id="hamburgerIcon"/>
          </button>
          </div>
        <!-- Navigation links (hidden by default) -->
        <div id="myLinks" v-bind:class="{ showList: !listIsHidden}">
          <a class="hamburgerLink" v-on:click="view = 'home'" v-bind:class="{ active: view=='home' }">home</a>
          <a class="hamburgerLink" v-on:click="view = 'gallery'" v-bind:class="{ active: view=='gallery'}">gallery</a>
          <a class="hamburgerLink" v-on:click="view = 'resume'" v-bind:class="{ active: view=='resume' }">resume</a>
          <a class="hamburgerLink" v-on:click="view = 'about'" v-bind:class="{ hactive: view=='about' }">about</a>
          <a class="hamburgerLink" v-on:click="view = 'contact'" v-bind:class="{ active: view=='contact' }">contact</a>
        </div>
        <!-- "Hamburger menu" / "Bar icon" to toggle the navigation links -->
        
      </div>
    </template>
    <template v-else>
      <nav class="navbar navbar-expand-lg navbar-light">
        <div id="navbarSupportedContent">
          <ul class="navbar-nav mr-auto">
            <li class="nav-item" v-bind:class="{ active: view == 'home' }">
              <a class="nav-link" v-on:click="view = 'home'">home</a>
            </li>
            <li class="nav-item" v-bind:class="{ active: view == 'gallery' }">
              <a class="nav-link" v-on:click="view = 'gallery'">gallery</a>
            </li>
            <li class="nav-item" v-bind:class="{ active: view == 'resume' }">
              <a class="nav-link" v-on:click="view = 'resume'">resume</a>
            </li>
            <li class="nav-item" v-bind:class="{ active: view == 'about' }">
              <a class="nav-link" v-on:click="view = 'about'">about</a>
            </li>
            <li class="nav-item" v-bind:class="{ active: view == 'contact' }">
              <a class="nav-link" v-on:click="view = 'contact'">contact</a>
            </li>
          </ul>
        </div>
      </nav>
    </template>
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
import { BIconList } from 'bootstrap-vue'

export default {
  name: 'App',
  components: {
    Home,
    About,
    Resume,
    Contact,
    Gallery,
    BIconList
  },
  data() {
    return {
      isMobile: false,
      view: 'home',
      listIsHidden: true
    }
  },
  mounted() {
    this.onResize()
    window.addEventListener('resize', this.onResize, { passive: true })
  },
  methods: {
    onResize() {
      this.isMobile = window.innerWidth < 900
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
  background-color: #fff9e6;
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

.col {
  display: flex;
  align-items: center;
  height: 100%;
}

.customBtnDesign {
  border: solid rgb(190, 153, 58) 2px;
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

@media (max-width: 900px) {
   /* Style the navigation menu */
.topnav {
  overflow: hidden;
  position: relative;
}

#myLinks > a{
  color: rgba(0, 0, 0, 0.5);
}

/* Hide the links inside the navigation menu (except for logo/home) */
.topnav #myLinks {
  display: none;
}

/* Style navigation menu links */
.topnav a {
  padding: 14px 16px;
  text-decoration: none;
  font-size: 17px;
  display: block;
}

/* Style the hamburger menu */
.topnav a.icon {
  display: block;
  position: absolute;
  right: 0;
  top: 0;
}

/* Add a grey background color on mouse-over */
.topnav a:hover {
  background-color: #ddd;
  color: black;
}

.active {
  color: black !important;
}

.customHamburger {
  float:right;
  padding: 5px;
}

#hamburgerIcon {
  color: #42b983;
}

.showList {
  display: block !important;
}

#buttonDiv {
  width: 100%;
}

.hamburgerLink {
  text-align: right;
}
}
</style>
