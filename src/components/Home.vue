<template>
  <div class="container">
    <div class="row">
      <div class="col" id="left">
        <img class="nonGalleryImage" id="smearPic" src="@/assets/smear.png" />
        <h1 class="homeBio">Amanda Tugangui is a NYC-based actor, improv-er, and renaissance woman from California.</h1>
      </div>
      <div class="col" id="right">
        <div class="container innerContainer">
          <div class="row innerRow" id="topPhotoRow">
            <img class="quads nonGalleryImage leftHeadshot" src="@/assets/rrivphoto-111.jpg" />
            <img class="quads nonGalleryImage rightHeadshot" src="@/assets/rrivphoto-213.jpg" />
          </div>
          <div class="row innerRow">
            <img class="quads nonGalleryImage leftHeadshot" src="@/assets/pic3.jpg" />
            <img class="quads nonGalleryImage rightHeadshot" src="@/assets/rrivphoto-95.jpg" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home'
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
  margin-left:auto;
  margin-right: 6%;
}

.rightHeadshot {
  margin-right: auto;
  margin-left:6%;
}
</style>
