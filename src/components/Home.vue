<template>
  <div class="container">
    <div class="row">
    <div class="col" id="left">
      <h1 class="homeBio specialFont">Amanda Tugangui is a NYC-based actor, improv-er, and aspiring renaissance woman from California.</h1>
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
        <img class="homeHeadshot" src="@/assets/rrivphoto-182.jpg"/>
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
  name: 'Home',
  props: {
    msg: String
  }
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
  background-color: red;
  display: flex;
  align-items: center;
}

#right {
  background-color: blue;
}

.homeBio {
  text-align: left;
}

.homeHeadshot {
  vertical-align: unset;
  height: 100%;
  width: 100%;
  object-fit:cover;
}

.innerRow {
  height: 50%;
}
</style>
