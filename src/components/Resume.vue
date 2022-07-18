<template>
  <div class="container">
    <div class="row">
      <div class="col">
        <img class="resume" src="@/assets/AmandaTuganguiResume.jpg" />
        <BIconZoomIn id="zoomBtn" />
        <button class="btn btn-light" id="downloadBtn">
          <BIconFilePdf/> DOWNLOAD PDF
        </button>
      </div>
      <div class="col">
        <img class="mainHeadshot" src="@/assets/rrivphoto-82.jpg"/>
      </div>
    </div>
  </div>
</template>

<script>
import { BIconFilePdf, BIconZoomIn} from 'bootstrap-vue'

export default {
  name: 'About',
  components: {
    BIconFilePdf,
    BIconZoomIn
  },
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
  height: 100%;
  width: 100%;
  object-fit: contain;
  position:absolute;
}

.mainHeadshot {
  height: 80%;
  width: 80%;
  object-fit: contain;
}

.italic {
  font-style: italic;
}

#bio {
  text-align: right;
  width: 70%;
}

#downloadBtn {
  border: solid red 2px;
  border-radius: 0px;
  padding-left: 30px;
  padding-right: 30px;
  padding-top: 10px;
  padding-bottom: 10px;
  position: absolute;
  transition: 0.3s;
  opacity: 0.5;
  bottom: 5px;
  right: 25%;
}

#downloadBtn:hover {opacity: 1}

#zoomBtn {
  position:absolute;
  width: 20px;
  margin-left: auto;
margin-right: auto;
left: 0;
right: 0;
text-align: center;
}

</style>