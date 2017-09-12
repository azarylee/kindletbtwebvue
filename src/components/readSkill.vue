<template>
  <div id="readSkill">
    <div class="title">
      <div class="img">
        <img src="../assets/img/36.jpg" class="menuPic"/>
      </div>
        <div class="subTitle">36氪</div>
        <span class="badge">{{ knumber1 }}</span>
    </div>
    <div class="title">
      <div class="img">
        <img src="../assets/img/guoke.jpg" class="menuPic"/>
      </div>
        <div class="subTitle">果壳</div>
        <span class="badge">{{ knumber2 }}</span>
    </div>
    <div class="title">
      <div class="img">
        <img src="../assets/img/js.jpeg" class="menuPic"/>
      </div>
        <div class="subTitle">简书</div>
        <span class="badge">{{ knumber2 }}</span>
    </div>
  </div>
</template>
<script>
export default {
  name: "readSkill",
  data: () => ({
    knumber1: 6,
    knumber2: 8
  })
}
</script>
<style lang="css">
</style>
