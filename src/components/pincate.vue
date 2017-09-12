<template>
  <div id="pin">
      <div class="title" @click="show">
        <div class="img">
          <img src="../assets/img/feed.png" class="menuPic"/>
        </div>
        <div class="subTitle">
          <div>我的订阅</div>
        </div>
      </div>
      <!--阅读-->
      <div class="title" v-show="show01"  @click="showRead">
        <div class="img">
          <span :class="[aClass]"></span>
        </div>
          <div class="subTitle" id="science" v-if="read">阅读</div>
          <span class="badge">{{ number1 }}</span>
      </div>
      <readBooks v-show="showRead01" ref="readBooks"></readBooks>
      <!--//阅读-->
      <!--小说-->
      <div class="title" v-show="show01" @click="showStory">
        <div class="img">
          <span :class="[bClass]"></span>
        </div>
          <div class="subTitle" id="science" v-if="story">小说</div>
          <span class="badge">{{ number2 }}</span>
      </div>
      <readStory v-show="showStory01" ref="readStory"></readStory>
      <!--//小说-->
      <div class="title" v-show="show01" @click="showSkill">
        <div class="img">
          <span :class="[cClass]"></span>
        </div>
          <div class="subTitle" id="science" v-if="skill">科技</div>
          <span class="badge" >{{ number3 }}</span>
      </div>
      <readSkill v-show="showSkill01" ref="readSkill"></readSkill>
  </div>
</template>
<script>
import readBooks from '../components/readBooks'
import readStory from '../components/readStory'
import readSkill from '../components/readSkill'

export default {
  data(){
    return{
      number1: 0,
      number2: 0,
      number3: 0,
      read: true,
      story: true,
      skill: true,
      show01: false,
      aClass: 'glyphicon glyphicon-chevron-right',
      bClass: 'glyphicon glyphicon-chevron-right',
      cClass: 'glyphicon glyphicon-chevron-right',
      showRead01: false,
      showStory01: false,
      showSkill01: false,
    }
  },
  methods:{
    showRead: function(){
      this.$root.eventBus.$emit('mshow',false);
      this.$root.eventBus.$emit('mrshow',false);
      var add= $("#readBook").height();
      var mwheight= $('.menc').height();
      var mheight= $('.mencx').height()-25.74;
      console.log("内容高度："+mheight);
      var bmh= $('#bottomMenu').height();

      // get the down button has been clicked or not
      console.log($('.mencx').css('top'));
      var htop= $('.mencx').css('top');
      var str= htop.split('p');
      var compare= str[0];
      console.log(compare);
      // get the down button has been clicked or not

      if(this.aClass=='glyphicon glyphicon-chevron-right'){
        this.aClass= 'glyphicon glyphicon-chevron-down';
        this.showRead01= true;
        if(compare<0){
          mheight= mheight+ add;
        } else{
          mheight= mheight+ add;
        }
      } else{
        this.aClass= 'glyphicon glyphicon-chevron-right';
        this.showRead01= false;
        if(compare<0){
          var mheight= $('.mencx').height()-(700-bmh+14)- add;
        } else{
          var mheight= $('.mencx').height()- add;
        }
      }
      console.log("内容高度："+mheight);
      if(mheight>mwheight){
        $('.rightMenu').css('background','white');
      } else{
        $('.rightMenu').css('background','grey');
      }
    },
    showStory: function(){
      this.$root.eventBus.$emit('mshow',false);
      this.$root.eventBus.$emit('mrshow',false);
      var add= $('#readStory').height();
      var mwheight= $('.menc').height();
      var mheight= $('.mencx').height()-25.74;
      console.log("内容高度："+mheight);
      var bmh= $('#bottomMenu').height();
      // get the down button has been clicked or not
      var htop= $('.mencx').css('top');
      var str= htop.split('p');
      var compare= str[0];
      // get the down button has been clicked or not

      if(this.bClass=='glyphicon glyphicon-chevron-right'){
        this.bClass= 'glyphicon glyphicon-chevron-down';
        this.showStory01= true;
        if(compare<0){
          mheight= mheight-(700-bmh+14)+ add;
        } else{
          mheight= mheight+ add;
        }
      } else{
        this.bClass= 'glyphicon glyphicon-chevron-right';
        this.showStory01= false;
        if(compare<0){
          mheight= mheight-(700-bmh+14)- add;
        } else{
          mheight= mheight- add;
        }
      }
      console.log("内容高度："+mheight);
      if(mheight>mwheight){
        $('.rightMenu').css('background','white');
      } else{
        $('.rightMenu').css('background','grey');
      }
    },
    showSkill: function(){
      this.$root.eventBus.$emit('mshow',false);
      this.$root.eventBus.$emit('mrshow',false);
      var add= $('#readSkill').height();
      var mwheight= $('.menc').height();
      var mheight= $('.mencx').height()-25.74;
      var bmh= $('#bottomMenu').height();
      // get the down button has been clicked or not
      var htop= $('.mencx').css('top');
      var str= htop.split('p');
      var compare= str[0];
      // get the down button has been clicked or not
      if(this.cClass=='glyphicon glyphicon-chevron-right'){
        this.cClass= 'glyphicon glyphicon-chevron-down';
        this.showSkill01= true;

        if(compare<0){
          mheight= mheight-(700-bmh+14)+ add;
        } else{
          mheight= mheight+ add;
        }
      } else{
        this.cClass= 'glyphicon glyphicon-chevron-right';
        this.showSkill01= false;
        if(compare<0){
          mheight= mheight-(700-bmh+14)- add;
        } else{
          mheight= mheight- add;
        }
      }
      if(mheight>mwheight){
        $('.rightMenu').css('background','white');
      } else{
        $('.rightMenu').css('background','grey');
      }
    },
    show: function () {
      this.$root.eventBus.$emit('mshow',false);
      this.$root.eventBus.$emit('mrshow',false);
      return this.show01 = this.show01===true? false:true;
    },
    change: function(number1){
      this.$root.eventBus.$emit('mshow',false);
      this.$root.eventBus.$emit('mrshow',false);
      this.number1= number1;
    }
  },
  components:{
    readBooks,
    readStory,
    readSkill
  },
  mounted: function() {
    this.number1= $('#readBook').children('.title').length;
    this.number2= $('#readStory').children('.title').length;
    this.number3= $('#readSkill').children('.title').length;
  }
}
</script>
<style lang="css">
.img>span{ font-size: 2rem;}
.badge{ text-align: right;}
</style>
