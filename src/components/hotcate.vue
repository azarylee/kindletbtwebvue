<template>
  <div id="hot">
    <div class="title">
      <div class="img">
        <img src="../assets/img/hot.png" class="menuPic"/>
      </div>
      <div class="subTitle" @click="show">
        <div >热门分类</div>
      </div>
    </div>
    <div class="title" v-show="show01" @click="contentShow1">
      <div class="img">
        <img />
      </div>
      <div class="subTitle">
        <div id="science">科技·互联网</div>
      </div>
    </div>
    <div class="title" v-show="show01" @click="contentShow2">
      <div class="img">
        <img />
      </div>
      <div class="subTitle">
        <div id="business">商业·财经</div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
    data(){
      return{
        show01: false,
        msg_show: false,
        active: 0,
        science: false,
        business: false,
      }
    },
    methods: {
        show: function () {
          var add= $('#hot').height();
          var mwheight= $('.menc').height();
          var mheight= $('.mencx').height()-25.74;
          var htop= $('.mencx').css('top');
          var str= htop.split('p');
          var compare= str[0];
          this.$root.eventBus.$emit('mshow',false);
          this.$root.eventBus.$emit('mrshow',false);
          console.log(this.show01);
          if(this.show01===false){
            compare>0? (mheight+ add):(mheight-(1588) + add);
            return this.show01 = this.show01===true? false:true;
          } else{
            compare>0? (mheight- add):(mheight-(1588) - add);
            return this.show01 = this.show01===true? false:true;
          };
          if(mheight>mwheight){
            $('.rightMenu').css('background','white');
          } else{
            $('.rightMenu').css('background','grey');
          }
        },
        contentShow1: function(){
          this.$root.eventBus.$emit('mshow',false);
          this.$root.eventBus.$emit('mrshow',false);
          this.$root.eventBus.$emit('msg_show', true);
          console.log(science);
          this.$root.eventBus.$emit('science', true);
          console.log(science);
        },
        contentShow2: function(){
          this.$root.eventBus.$emit('mshow',false);
          this.$root.eventBus.$emit('mrshow',false);
          this.$root.eventBus.$emit('msg_show', true);
          this.$root.eventBus.$emit('business', true);
        }
    },
}
</script>
<style lang="css">
.menuPic{ width: 2rem;}
</style>
