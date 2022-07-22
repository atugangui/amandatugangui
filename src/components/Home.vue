<template>
  <div class="container">
    <div class="row">
    <div class="col" id="left">
      <img class="homeSmear" src="@/assets/smear.png"/>
      <h1 class="homeBio specialFont">Amanda Tugangui is a NYC-based actor, improv-er, and renaissance woman from California.</h1>
    </div>
    <div class="col" id="right">
      <div class="container innerContainer">
        <div class="row innerRow">
      <div class="quads" id="one">
        <img class="homeHeadshot" src="@/assets/rrivphoto-111.jpg"/>
      </div>
      <div class="quads" id="two">
        <img class="homeHeadshot" src="@/assets/rrivphoto-213.jpg"/>
      </div>
      </div>
      <div class="row innerRow">
      <div class="quads" id="three">
        <img class="homeHeadshot" src="@/assets/pic3.jpg"/>
      </div>
      <div class="quads" id="four">
        <img class="homeHeadshot" src="@/assets/rrivphoto-95.jpg"/>
      </div>
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

.homeHeadshot, .homeSmear {
  vertical-align: unset;
  height: 100%;
  width: 100%;
  object-fit: contain;
}

.homeSmear {
  z-index: 0;
}

.innerRow {
  height: 50%;
}
</style>
