<template>
  <div class="container">
    <div class="row">
      <div class="col">
        <img class="resume" src="@/assets/AmandaTuganguiResume.jpg" />
        <button class="btn customBtnDesign" id="downloadBtn">
          <a v-bind:href="'AmandaTuganguiResume.pdf'" download>
          <BIconDownload id="downloadIcon"/> download
          </a>
        </button>
      </div>
      <div class="col">
        <img class="nonGalleryImage" src="@/assets/rrivphoto-82.jpg"/>
      </div>
    </div>
  </div>
</template>

<script>
import { BIconDownload } from 'bootstrap-vue'

export default {
  name: 'Resume',
  components: {
    BIconDownload,
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
  position:absolute;
  top:0px;
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

</style>