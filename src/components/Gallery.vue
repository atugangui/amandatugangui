<template>
  <div class="container">
    <stack :column-min-width="300" :gutter-width="15" :gutter-height="15" monitor-images-loaded>
      <StackItem v-for="(item, i) in items" :key="i">
        <template v-if="item.mediaType == 2">
          <iframe width="560" height="315" :src="item.imgSrc" title="YouTube video player" frameborder="0" >
          </iframe>
          </template>
          <template v-else>
          <v-lazy-image
            class="galleryImages"
            :src=getLargeImgUrl(item)
            :src-placeholder=getTinyImgUrl(item)
            v-bind:alt="item.showName"
          />
          <p class="prodNameOnPic">{{item.showName}}</p>
          </template>
          <!--<br/><span class="prodCoText">{{item.prodCo}}</span>-->
      </StackItem>
      <StackItem>

      </StackItem>
    </stack>
  </div>
</template>

<script>
import { Stack, StackItem } from 'vue-stack-grid';
import VLazyImage from "v-lazy-image/v2";

import largeSweeney from "../assets/gallery/SweeneyTodd.jpg";
import largeLove from "../assets/gallery/LoveAndInformation.jpg";
import largeWedding from "../assets/gallery/AvenueQ.jpg";
import largeWait from "../assets/gallery/WaitUntilDark.jpg";
import largeAntigonick from "../assets/gallery/Antigonick.jpg";
import largeSweeney2 from "../assets/gallery/SweeneyToddClose.jpg";

import tinySweeney from "../assets/tiny/gallery/SweeneyTodd.jpg";
import tinyLove from "../assets/tiny/gallery/LoveAndInformation.jpg";
import tinyWedding from "../assets/tiny/gallery/AvenueQ.jpg";
import tinyWait from "../assets/tiny/gallery/WaitUntilDark.jpg";
import tinyAntigonick from "../assets/tiny/gallery/Antigonick.jpg";
import tinySweeney2 from "../assets/tiny/gallery/SweeneyToddClose.jpg";

export default {
  name: 'Gallery',
  components: { Stack, StackItem, VLazyImage },
  methods: {
    getLargeImgUrl(item) {
      return item.largeImg;
    },
    getTinyImgUrl(item){
      return item.tinyImg;
    }
  },
  data() {
    return {
      currentImageHovered: null,
      items: [
          {
            showName: "SWEENEY TODD",
            imgSrc: 'SweeneyTodd',
            prodCo: 'Lewis & Clark College',
            largeImg: largeSweeney,
            tinyImg: tinySweeney,
            mediaType: 1
          },
          {
            showName: 'HEART OF GOD',
            imgSrc: 'https://www.youtube.com/embed/qbPxZPsjhbg',
            prodCo: 'd. Director Name',
            largeImg: null,
            tinyImg: null,
            mediaType: 2
          },
          {
            showName: "DENNY'S",
            imgSrc: 'https://www.youtube.com/embed/4JU76lgOYbo',
            prodCo: 'd. Director Name',
            largeImg: null,
            tinyImg: null,
            mediaType: 2
          },
          {
            showName: "AVENUE Q",
            imgSrc: 'aveQWedding',
            prodCo: 'The Hollywood Majestic',
            largeImg: largeWedding,
            tinyImg: tinyWedding,
            mediaType: 1
          },
          {
            showName: "LOVE AND INFORMATION",
            imgSrc: 'LoveAndInfo',
            prodCo: 'Lewis & Clark College',
            largeImg: largeLove,
            tinyImg: tinyLove,
            mediaType: 1
          },
          {
            showName: 'WAIT UNTIL DARK',
            imgSrc: 'WaitUntilDark',
            prodCo: 'Theatre Palisades',
            largeImg: largeWait,
            tinyImg: tinyWait,
            mediaType: 1
          },
          {
            showName: "ANTIGONICK",
            imgSrc: 'Antigonick',
            prodCo: 'Lewis & Clark College',
            largeImg: largeAntigonick,
            tinyImg: tinyAntigonick,
            mediaType: 1
          },
          {
            showName: 'SWEENEY TODD',
            imgSrc: 'SweeneyToddClose',
            prodCo: 'Lewis & Clark College',
            largeImg: largeSweeney2,
            tinyImg: tinySweeney2,
            mediaType: 1
          }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  height: 100%;
}

.vsg-container {
  max-height: 100%;
  height: 100%;
}

.galleryImages,
iframe {
  width: 100%;
  border-radius: 8px;
}

.prodNameOnPic {
  font-size: 8pt;
  position: absolute;
  bottom: -13px;
  right: 5px;
  text-align: right;
  color: white;
}

.prodCoText{
  font-style: italic;
}

@media (min-width: 1920px) {
  .container {
    max-width: 1200px;
  }
}
</style>