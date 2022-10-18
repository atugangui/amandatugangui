<template v-if="isMobile">
  <div class="container">
    <div class="row">
      <template v-if="isMobile">
      <div class="col-12">
          <p id="bio">
            Onstage, Amanda brings an intensity and freshness to everything she performs in, whether it be a Greek classic or 
            an underground comedy show.
            <br/>
            <br/>
            Offstage, Amanda is madly curious about everything.
            <br />
            Like, what is it like to <a href="https://www.youtube.com/watch?v=jGH_rhOWm0s" target="_blank">play
              harp?</a>
            (Hard.)
            <br />
            Or to write a <a href="https://tugangui.substack.com/" target="_blank">travel blog?</a> (Cathartic.)
            <br />
            To <a href="https://imgur.com/a/esCVBuY" target="_blank">grow bok choy?</a> (Delicious.)
            <br />
            <br />
            Still, having tried out so many things, performing remains Amanda's longest
            and brightest love.
          </p>
        </div>
        <div class="col-12">
          <v-lazy-image class="nonGalleryImage" :src=polaroid :src-placeholder=tinyPolaroid
            alt="Amanda Tugangui Polaroid picture" />
        </div>
      </template>
      <template v-else>
        <div class="col">
          <v-lazy-image class="nonGalleryImage" :src=polaroid :src-placeholder=tinyPolaroid
            alt="Amanda Tugangui Polaroid picture" />
        </div>
        <div class="col">
          <p id="bio">
            Onstage, Amanda brings an intensity and freshness to everything she performs in, whether it be a Greek classic or 
            an underground comedy show.
            <br/>
            <br/>
            Offstage, Amanda is madly curious about everything.
            <br />
            Like, what is it like to <a href="https://www.youtube.com/watch?v=jGH_rhOWm0s" target="_blank">play
              harp?</a>
            (Hard.)
            <br />
            Or to write a <a href="https://tugangui.substack.com/" target="_blank">travel blog?</a> (Cathartic.)
            <br />
            To <a href="https://imgur.com/a/esCVBuY" target="_blank">grow bok choy?</a> (Delicious.)
            <br />
            <br />
            Still, having tried out so many things, performing remains Amanda's longest
            and brightest love.
          </p>
        </div>
      </template>
    </div>
  </div>
</template>

<script>
import VLazyImage from "v-lazy-image/v2";

import polaroid from "../assets/about/Polaroid.png";
import tinyPolaroid from "../assets/tiny/about/Polaroid.png";

export default {
  name: 'About',
  components: {
    VLazyImage
  },
  data() {
    return {
      isMobile: false
    }
  },
  computed: {
    polaroid() {
      return polaroid;
    },
    tinyPolaroid() {
      return tinyPolaroid;
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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  height: 90%;
}

.row {
  height: 100%;
}

.italic {
  font-style: italic;
}

#bio {
  text-align: right;
  width: 70%;
}

@media (min-width: 1366px) {
  #bio {
    width: 100%;
  }
}

@media (max-width: 900px) {
  #bio {
    width: 100%;
    text-align: center;
  }
}
</style>