<template v-if="isMobile">
  <div class="container">
    <div class="row">
      <template v-if="isMobile">
      <div class="col-12">
          <p id="contactInfo">
            Gill Talent Group
            <br/>
            <br/>
            NYC Agent: Gabrielle Holder
            <br/>Gabrielle@gilltalent.com
            <br/>
            <br/>
            42 Broadway, 12 FL Suite 106
            <br/>New York City, New York 10004
            <br/>Tel 646.889.1234, Fax 888.451.3748
          </p>
        </div>
        <div class="col-12">
          <v-lazy-image class="nonGalleryImage" :src=gtg :src-placeholder=tinyGtg
            alt="Gill Talent Group" />
        </div>
      </template>
      <template v-else>
        <div class="col">
          <v-lazy-image class="nonGalleryImage" :src=gtg :src-placeholder=tinyGtg
            alt="Gill Talent Group" />
        </div>
        <div class="col">
          <p id="contactInfo">
            Gill Talent Group
            <br/>
            <br/>
            NYC Agent: Gabrielle Holder
            <br/>Gabrielle@gilltalent.com
            <br/>
            <br/>
            42 Broadway, 12 FL Suite 106
            <br/>New York City, New York 10004
            <br/>Tel 646.889.1234, Fax 888.451.3748
          </p>
        </div>
      </template>
    </div>
  </div>
</template>

<script>
import VLazyImage from "v-lazy-image/v2";

import gtg from "../assets/contact/GillTalentGroup.jpg";
import tinyGtg from "../assets/tiny/contact/GillTalentGroup.jpg";

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
    gtg() {
      return gtg;
    },
    tinyGtg() {
      return tinyGtg;
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

#contactInfo {
  text-align: right;
  width: 70%;
}

@media (min-width: 1366px) {
  #contactInfo {
    width: 100%;
  }
}

@media (max-width: 900px) {
  #contactInfo {
    width: 100%;
    text-align: center;
  }
}
</style>