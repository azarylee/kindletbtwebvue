<template>
  <div id="bottomMenur">
      <div id="rmenudiv" v-show="mrshow">
        <div class="menudiv_cont">
          <div class="title" @click="show_menu">
            <div class="img">
              <img src="../assets/img/visible.png" class="one" />
            </div>
            <div class="subTitle">
              <div>显示左侧栏</div>
            </div>
          </div>

          <div class="title" @click="show_font">
            <div class="img">
              <img src="../assets/img/font.png" class="two"/>
            </div>
            <div class="subTitle">
              <div>字体</div>
            </div>
          </div>

        </div>
      </div>
      <div class="leftMenur glyphicon glyphicon-menu-hamburger" @click="showNavbar">

      </div>
      <div class="middleMenur glyphicon glyphicon-menu-up" @click="up">

      </div>
      <div class="rightMenur glyphicon glyphicon-menu-down" @click="down">

      </div>
  </div>
</template>
<script>

export default {
  data(){
    return{
      height: $('.contentcx').height(),
      total_h: $('.contentcx').height(),
      wheight: $('.contentc').height(),
      mrshow: false
    }
  },
  methods: {
    showNavbar: function(){
      this.$root.eventBus.$emit('mshow',false);
      return this.mrshow= this.mrshow===true? false:true;
    },
    down: function() {
      this.$root.eventBus.$emit('mshow',false);
      this.mrshow=false;
      var htop= $('.contentcx').css('top');
      var str= htop.split('p');
      var compare= str[0];
      console.log("down");
      console.log("top:"+compare);
      if(this.height>this.wheight && compare<=0){
        console.log('开始');
        console.log('height:'+this.height);
        console.log('wheight:'+this.wheight);
        $('.contentcx').animate({top: '-=98rem'}, 'fast');
        this.height -=1575;
        compare -=1575;
        this.height<this.wheight?$('.rightMenur').css('background','grey'):$('.rightMenur').css('background','white');
        console.log("nowTop:"+compare);
        this.height>this.wheight && compare>0?$('.middleMenur').css('background','grey'):$('.middleMenur').css('background','white');
        console.log('结束');
        console.log('height:'+this.height);
        console.log('wheight:'+this.wheight);
      }
      else{
        $('.rightMenur').css('background','grey');
      }
    },
    up: function(){
      this.$root.eventBus.$emit('mshow',false);
      this.mrshow=false;
      var htop= $('.contentcx').css('top');
      var str= htop.split('p');
      var compare= parseInt(str[0]);
      console.log("up");
      console.log("top:"+compare);
      if(this.height<this.total_h && compare<0){
        console.log('up开始');
        console.log('height:'+this.height);
        console.log('wheight:'+this.wheight);
        $('.contentcx').animate({top: '+=98rem'}, 'fast');
        this.height +=1575;
        compare +=1575;
        this.height<=this.wheight?$('.rightMenur').css('background','grey'):$('.rightMenur').css('background','white');
        console.log("nowTop:"+compare);
        this.height>=this.wheight && compare>=0?$('.middleMenur').css('background','grey'):$('.middleMenur').css('background','white');
        console.log('up结束');
        console.log('height:'+this.height);
        console.log('wheight:'+this.wheight);
      } else{
        $('.middleMenur').css('background','grey');
      }
    },
    show_menu: function(){
      if($('#men').hasClass('active')){
        $('#men').removeClass('active');
        $('#menudiv').css('display','none');
        this.$root.eventBus.$emit('mshow',false);
      }
      this.mrshow=false;
    },
    show_font: function(){
      this.$root.eventBus.$emit('fontchoice',true);
      this.$root.eventBus.$emit('mshow',false);
      this.mrshow=false;
    }
  },
  mounted() {
    console.log(this.height);
    console.log(this.wheight);
    if(this.height>this.wheight){
      $('.rightMenur').css('background','white');
      $('.middleMenur').css('background','grey');
    } else{
      $('.rightMenur').css('background','grey');
      $('.middleMenur').css('background','grey');
    }
  },
  created(){
    this.$root.eventBus.$on('mshow', () => {
      this.mshow= false;
    });
    this.$root.eventBus.$on('mrshow', () => {
      this.mrshow= false;
    });
  }
}
</script>
<style lang="css">
#bottomMenur{ flex: none; -webkit-flex: none; display: flex; flex-direction: row; height: 8rem; width: 100%; border-top: 2px solid #999;}
.leftMenur,.middleMenur{ width: 8rem; border-right: 1px solid #999; display: flex!important; justify-content: center; align-items: center; font-size: 3rem;}
.rightMenur{ flex: 1; -webkit-flex: 1; border-right: 1px solid #999; display: flex!important; justify-content: center; align-items: center; font-size: 3rem;}
</style>
