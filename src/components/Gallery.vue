<template>
  <div class="container">
    <stack :column-min-width="300" :gutter-width="15" :gutter-height="15" monitor-images-loaded>
      <StackItem v-for="(item, i) in items" :key="i">
          <iframe v-if="i == 1" :src="item.imgSrc">
          </iframe>
          <img class="galleryImages" v-else :src="getImgUrl(item)" v-bind:alt="item.showName"/>
          <p class="prodNameOnPic">{{item.showName}}</p>
          <!--<br/><span class="prodCoText">{{item.prodCo}}</span>-->
      </StackItem>
      <StackItem>

      </StackItem>
    </stack>
  </div>
</template>

<script>
import { Stack, StackItem } from 'vue-stack-grid';
export default {
  name: 'Gallery',
  components: { Stack, StackItem },
  methods: {
    getImgUrl(item) {
      let images = require.context('../assets/', false, /\.jpg$/)
      return images('./' + item.imgSrc + ".jpg")
    }
  },
  data() {
    return {
      currentImageHovered: null,
      items: [
          {
            showName: "SWEENEY TODD",
            imgSrc: 'SweeneyTodd',
            prodCo: 'Lewis & Clark College'
          },
          {
            showName: "DENNY'S",
            imgSrc: 'https://www.youtube.com/embed/4JU76lgOYbo',
            prodCo: 'd. Director Name'
          },
          {
            showName: "LOVE AND INFORMATION",
            imgSrc: 'LoveAndInfo',
            prodCo: 'Lewis & Clark College'
          },
          {
            showName: "AVENUE Q",
            imgSrc: 'aveQWedding',
            prodCo: 'The Hollywood Majestic'
          },
          {
            showName: 'WAIT UNTIL DARK',
            imgSrc: 'WaitUntilDark',
            prodCo: 'Theatre Palisades'
          },
          {
            showName: "ANTIGONICK",
            imgSrc: 'Antigonick',
            prodCo: 'Lewis & Clark College'
          },
          {
            showName: 'SWEENEY TODD',
            imgSrc: 'SweeneyToddClose',
            prodCo: 'Lewis & Clark College'
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
</style>