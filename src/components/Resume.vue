<template>
  <div class="container">
    <template v-if="isMobile">
      <div class="row">
        <div class="col-12">
          <button class="btn customBtnDesign" id="downloadBtn">
            <a v-bind:href="'AmandaTuganguiResume.pdf'" download>
              <BIconDownload id="downloadIcon" /> download
            </a>
          </button>
        </div>
        <div class="col-12">
          <v-lazy-image class="resume" :src=largeResume :src-placeholder=tinyResume alt="Amanda Tugangui's Resume" />
        </div>
        <div class="col-12">
          <v-lazy-image class="nonGalleryImage" :src=largeHeadshot :src-placeholder=tinyHeadshot
            alt="Amanda Tugangui's Main Headshot" />
        </div>
        </div>
    </template>
    <template v-else>
      <div class="row">

        <div class="col">
          <v-lazy-image class="resume" :src=largeResume :src-placeholder=tinyResume alt="Amanda Tugangui's Resume" />
          <button class="btn customBtnDesign" id="downloadBtn">
            <a v-bind:href="'AmandaTuganguiResume.pdf'" download>
              <BIconDownload id="downloadIcon" /> download
            </a>
          </button>
        </div>
        <div class="col">
          <v-lazy-image class="nonGalleryImage" :src=largeHeadshot :src-placeholder=tinyHeadshot
            alt="Amanda Tugangui's Main Headshot" />
        </div>
      </div>
    </template>
  </div>
</template>

<script>
import { BIconDownload } from 'bootstrap-vue'
import VLazyImage from "v-lazy-image/v2"
import largeResume from "../assets/resume/Resume.jpg"
import largeHeadshot from "../assets/resume/MainHeadshot.jpg"
import tinyResume from "../assets/tiny/resume/Resume.jpg"
import tinyHeadshot from "../assets/tiny/resume/MainHeadshot.jpg"


export default {
  name: 'Resume',
  components: {
    BIconDownload,
    VLazyImage
  },
  data() {
    return {
      isMobile: false
    }
  },
  computed: {
    largeResume() {
      return largeResume;
    },
    largeHeadshot() {
      return largeHeadshot;
    },
    tinyResume() {
      return tinyResume;
    },
    tinyHeadshot() {
      return tinyHeadshot;
    },
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

.col {
  display: flex;
  align-items: center;
  height: 100%;
}

a {
  color: #42b983;
}

.resume {
  height: 90%;
  width: 90%;
  object-fit: contain;
  position: absolute;
  top: 0px;
}

#downloadBtn {
  display: inline;
  transition: 0.3s;
  opacity: 0.5;
  bottom: 5px;
  text-align: center;
  margin-top: auto;
  color: #42b983;
}

#downloadBtn {
  margin-right: auto;
  margin-left: auto;
}

#downloadBtn:hover {
  opacity: 1;
}

@media (max-width: 900px) {
  .resume {
    position: unset;
  }
}
</style>