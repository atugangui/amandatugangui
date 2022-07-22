<template>
  <div class="container">
    <div class="row">
      <div class="col">
        <img class="resume" src="@/assets/AmandaTuganguiResume.jpg" />
        <button class="btn customBtnDesign" id="downloadBtn">
          <a  v-bind:href="'/AmandaTuganguiResume.pdf'" download>
          <BIconDownload id="downloadIcon"/> download
          </a>
        </button>
      </div>
      <div class="col">
        <img class="mainHeadshot" src="@/assets/rrivphoto-82.jpg"/>
      </div>
    </div>
  </div>
</template>

<script>
import { BIconDownload} from 'bootstrap-vue'

export default {
  name: 'About',
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

h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
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

.mainHeadshot {
  height: 100%;
  width: 100%;
  object-fit: contain;
}

.italic {
  font-style: italic;
}

#bio {
  text-align: right;
  width: 70%;
}

#downloadBtn, #zoomBtn {
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

#zoomBtn:hover {opacity: 1}

#downloadIcon {
  width: 15px;
  margin: 2px;
}

</style>