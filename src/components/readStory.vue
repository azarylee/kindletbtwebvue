<template>
  <div id="readStory">
    <div class="title">
      <div class="img">
        <img src="../assets/img/bbc.jpg" class="menuPic"/>
      </div>
        <div class="subTitle">BBC</div>
        <span class="badge">{{ snumber1 }}</span>
    </div>
    <div class="title">
      <div class="img">
        <img src="../assets/img/ng.png" class="menuPic"/>
      </div>
        <div class="subTitle">National Geographic</div>
        <span class="badge">{{ snumber2 }}</span>
    </div>
    <div class="title">
      <div class="img">
        <img src="../assets/img/cg.jpg" class="menuPic"/>
      </div>
        <div class="subTitle">中国国家地理</div>
        <span class="badge">{{ snumber3 }}</span>
    </div>
    <div class="title">
      <div class="img">
        <img src="../assets/img/nfzm.jpeg" class="menuPic"/>
      </div>
        <div class="subTitle">南方周末</div>
        <span class="badge">{{ snumber4 }}</span>
    </div>
    <div class="title">
      <div class="img">
        <img src="../assets/img/bzmh.jpg" class="menuPic"/>
      </div>
        <div class="subTitle">暴走漫画</div>
        <span class="badge">{{ snumber5 }}</span>
    </div>
    <div class="title">
      <div class="img">
        <img src="../assets/img/yl.jpeg" class="menuPic"/>
      </div>
        <div class="subTitle">意林</div>
        <span class="badge">{{ snumber2 }}</span>
    </div>
  </div>
</template>
<script>
export default {
  name: "readStory",
  data(){
    return{
      snumber1: 3,
      snumber2: 7,
      snumber3: 0,
      snumber4: 1,
      snumber5: 4
    }
  }
}
</script>
<style lang="css">
</style>
