<template>
  <div class="container">
    <div class="row">
      <div class="col" id="left">
        <img class="nonGalleryImage" id="smearPic" src="@/assets/home/PaintSmear.png" alt=null/>
        <h1 class="homeBio">Amanda Tugangui is an NYC-based actor, improv-er, and renaissance woman from California.
        </h1>
      </div>
      <div class="col" id="right">
        <div class="container innerContainer">
          <div class="row innerRow" id="topPhotoRow">
            <v-lazy-image class="quads nonGalleryImage leftHeadshot" :src=largeBlue :src-placeholder=tinyBlue alt="Smiling Amanda Tugangui" />
            <v-lazy-image class="quads nonGalleryImage rightHeadshot" :src=largeGreen :src-placeholder=tinyGreen alt="Smirking Amanda Tugangui" />
          </div>
          <div class="row innerRow">
            <v-lazy-image class="quads nonGalleryImage leftHeadshot" :src=largeTan :src-placeholder=tinyTan alt="Dramatic Amanda Tugangui"/>
            <v-lazy-image class="quads nonGalleryImage rightHeadshot" :src=largePurple :src-placeholder=tinyPurple alt="Laughing Amanda Tugangui" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import VLazyImage from "v-lazy-image/v2";

import largeBlue from "../assets/home/BlueHeadshot.jpg";
import largeGreen from "../assets/home/GreenHeadshot.jpg";
import largeTan from "../assets/home/TanHeadshot.jpg";
import largePurple from "../assets/home/PurpleHeadshot.jpg";

import tinyBlue from "../assets/tiny/home/BlueHeadshot.jpg";
import tinyGreen from "../assets/tiny/home/GreenHeadshot.jpg";
import tinyTan from "../assets/tiny/home/TanHeadshot.jpg";
import tinyPurple from "../assets/tiny/home/PurpleHeadshot.jpg";

export default {
  name: 'Home',
  components: {
    VLazyImage
  },
  computed: {
    largeBlue() {
      return largeBlue;
    },
    largeGreen() {
      return largeGreen;
    },
    largeTan() {
      return largeTan;
    },
    largePurple() {
      return largePurple;
    },
    tinyBlue() {
      return tinyBlue;
    },
    tinyGreen() {
      return tinyGreen;
    },
    tinyTan() {
      return tinyTan;
    },
    tinyPurple() {
      return tinyPurple;
    }
  },
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

#smearPic {
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
