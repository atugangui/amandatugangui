<template>
  <div class="container">
    <div class="row">
    <div class="col" id="left"></div>
    <div class="col" id="right">
      <div class="quads" id="one"></div>
      <div class="quads" id="two"></div>
      <div class="quads" id="three"></div>
      <div class="quads" id="four"></div>
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

.row {
  height: 100%;
}

.hello {
  height: 89vh;
  margin-right: 8%;
  margin-left: 8%;
}

.halves {
  display: inline-block;
  height: 100%;
  width: 50%;
}

.quads {
  display: inline-block;
  height: 10%;
  width: 50%;
}

#left {
  background-color: red;
}

#right {
  background-color: blue;
}
</style>
