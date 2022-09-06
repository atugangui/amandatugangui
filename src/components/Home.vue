<template>
  <div class="container">
    <template v-if="isMobile">
      <div class="row">
        <div class="col-12" style="height:50%">
          <v-lazy-image class="nonGalleryImage" :src=portrait :src-placeholder=tinyPortrait
            alt="Amanda Tugangui's Portrait" />
        </div>
        <div class="col-12" id="left" style="height:50%">
          <img class="nonGalleryImage" id="greenGoldCircles" src="@/assets/home/Circles.png" alt=null />
          <h1 class="homeBio">Amanda Tugangui is an NYC-based actor, improv-er, and renaissance woman from California.
          </h1>
        </div>
      </div>
    </template>
    <template v-else>
      <div class="row">
        <div class="col" id="left">
          <img class="nonGalleryImage" id="greenGoldCircles" src="@/assets/home/Circles.png" alt=null />
          <h1 class="homeBio">Amanda Tugangui is an NYC-based actor, improv-er, and renaissance woman from California.
          </h1>
        </div>
        <div class="col">
          <v-lazy-image class="nonGalleryImage" :src=portrait :src-placeholder=tinyPortrait
            alt="Amanda Tugangui's Portrait" />
        </div>
      </div>
    </template>
  </div>
</template>

<script>
import VLazyImage from "v-lazy-image/v2";

import portrait from "../assets/home/Portrait.jpg";
import tinyPortrait from "../assets/tiny/home/Portrait.jpg";

export default {
  name: 'Home',
  components: {
    VLazyImage
  },
  data() {
    return {
      isMobile: false
    }
  },
  computed: {
    portrait() {
      return portrait;
    },
    tinyPortrait() {
      return tinyPortrait;
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

.innerContainer {
  height: 100%;
}

.row {
  height: 100%;
}

.quads {
  display: inline-block;
  width: 33%;
  margin: auto;
}

#left {
  display: flex;
  align-items: center;
}

.homeBio {
  text-align: center;
  z-index: 1;
  position: absolute;
}

#greenGoldCircles {
  z-index: 0;
}

.innerRow {
  height: 50%;
}

#topPhotoRow {
  margin-bottom: 2%;
}

.leftHeadshot {
  margin-left: auto;
  margin-right: 6%;
}

.rightHeadshot {
  margin-right: auto;
  margin-left: 6%;
}

@media (min-height: 721px) {
  .quads {
    width: 44%;
  }
}

@media (min-height: 1080px) {
  .quads {
    width: 33%;
  }
}
</style>
