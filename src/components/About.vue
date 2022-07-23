<template>
  <div class="container">
    <div class="row">
      <div class="col">
        <img class="nonGalleryImage" src="@/assets/DSC_8770-Edit.jpg" />
      </div>
      <div class="col">
        <p id="bio">
          Having recently relocated from Los Angeles, Amanda was just 
          nominated for an acting award from Theatre Palisades for her role as 
          Gloria in <span class="italic">Wait Until Dark.</span>
          <br />
          <br />
          When she's not on stage, Amanda is intensely curious about everything. 
          <br />
          Like, what is it like to <a href="https://www.youtube.com/watch?v=jGH_rhOWm0s" target="_blank">play harp?</a> (Hard.)
          <br />
          Or to write a <a href="https://tugangui.substack.com/" target="_blank">travel blog?</a> (Cathartic.)
          <br />
          To <a href="https://imgur.com/a/esCVBuY" target="_blank">grow bok choy?</a> (Delicious.)
          <br />
          <br />
          With a background as a programmer (she coded this website herself!),
          she most recently worked at a neuroscience lab at UCLA, where she 
          co-authored several papers published in <span class="italic">Nature.</span>
          <br />
          <br />
          Still, having tried out so many things, performing remains Amanda's longest
          and brightest love.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'About'
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

.italic {
  font-style: italic;
}

#bio {
  text-align: right;
  width: 70%;
}

@media (min-width: 1366px) {
  #bio {
    width: 100%;
  }
}
</style>