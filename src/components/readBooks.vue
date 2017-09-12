<template>
  <div id="readBook" >
    <div class="title" @click="doubanshow">
      <div class="img">
        <img src="../assets/img/doubanLogo.jpg" class="menuPic"/>
      </div>
        <div class="subTitle">豆瓣</div>
        <span class="badge">{{ readnumber1 }}</span>
    </div>
    <div class="title" @click="toutiaoshow">
      <div class="img">
        <img src="../assets/img/tt.png" class="menuPic"/>
      </div>
      <div class="subTitle">今日头条</div>
      <span class="badge">{{ readnumber2 }}</span>
    </div>
    <div class="title" @click="zhihushow">
      <div class="img">
        <img src="../assets/img/zhihu.jpg" class="menuPic"/>
      </div>
      <div class="subTitle">知乎</div>
      <span class="badge">{{ readnumber3 }}</span>
    </div>
    <div class="title">
      <div class="img">
        <img src="../assets/img/ifeng.jpg" class="menuPic"/>
      </div>
      <div class="subTitle">凤凰新闻</div>
      <span class="badge">{{ readnumber4 }}</span>
    </div>
    <div class="title">
      <div class="img">
        <img src="../assets/img/sl.jpg" class="menuPic"/>
      </div>
        <div class="subTitle">三联生活</div>
        <span class="badge">{{ readnumber5 }}</span>
    </div>
  </div>
</template>
<script>

export default {
  name: "readBook",
  data(){
    return{
      readnumber1: 1,
      readnumber2: 3,
      readnumber3: 0,
      readnumber4: 6,
      readnumber5: 5,
      douban: false,
    }
  },
  methods: {
    doubanshow: function(){
      this.$root.eventBus.$emit('mshow',false);
      this.$root.eventBus.$emit('mrshow',false);
      this.$root.eventBus.$emit('msg_show', true);
      this.$root.eventBus.$emit('douban', true);
    },
    toutiaoshow: function(){
      this.$root.eventBus.$emit('mshow',false);
      this.$root.eventBus.$emit('mrshow',false);
      this.$root.eventBus.$emit('msg_show', true);
      this.$root.eventBus.$emit('toutiao', true);
    },
    zhihushow: function(){
      this.$root.eventBus.$emit('mshow',false);
      this.$root.eventBus.$emit('mrshow',false);
      this.$root.eventBus.$emit('msg_show', true);
      this.$root.eventBus.$emit('zhihu', true);
    },
  }
}

</script>
<style lang="css">
</style>
