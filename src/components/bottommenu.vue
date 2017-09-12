<template>

  <div id="bottomMenu">
    <div id="menudiv" v-show="mshow">
      <div class="menudiv_cont">
        <div class="title" @click="hidden_menu">
          <div class="img">
            <img src="../assets/img/visible.png" class="one"/>
          </div>
          <div class="subTitle">
            <div>隐藏左侧栏</div>
          </div>
        </div>

        <div class="title" @click="show_account_info">
          <div class="img">
            <img src="../assets/img/account.png" class="two"/>
          </div>
          <div class="subTitle">
            <div>账户信息/升级</div>
          </div>
        </div>

        <div class="title">
          <div class="img">
            <img src="../assets/img/logoff.png" class="three"/>
          </div>
          <div class="subTitle">
            <div>登出</div>
          </div>
        </div>
      </div>
    </div>
    <div class="leftMenu glyphicon glyphicon-menu-hamburger" @click="showNavbar">

    </div>
    <div class="middleMenu glyphicon glyphicon-menu-up" @click="up">

    </div>
    <div class="rightMenu glyphicon glyphicon-menu-down" @click="down">

    </div>
  </div>
</template>
<script>

export default {
  data(){
    return{
      mshow: false
    }
  },
  methods: {
    showNavbar: function(){
      this.$root.eventBus.$emit('mrshow',false);
      return this.mshow= this.mshow===true? false:true;
    },
    down: function() {
      this.$root.eventBus.$emit('mshow',false);
      this.$root.eventBus.$emit('mrshow',false);
      var mwheight= $('.menc').height();
      var mheight= $('.mencx').height()-25.74;
      var htop= $('.mencx').css('top');
      var str= htop.split('p');
      var compare= str[0];

      console.log("down");
      console.log("top:"+compare);
      if(mheight>mwheight && compare<=0){
        console.log('开始');
        console.log('height:'+mheight);
        console.log('wheight:'+mwheight);
        $('.mencx').animate({top: '-=85rem'}, 'fast');
        mheight -=1588;
        compare -=1588;
        mheight<mwheight?$('.rightMenu').css('background','grey'):$('.rightMenu').css('background','white');
        console.log("nowTop:"+compare);
        mheight>mwheight && compare>0?$('.middleMenu').css('background','grey'):$('.middleMenu').css('background','white');
        console.log('结束');
        console.log('height:'+mheight);
        console.log('wheight:'+mwheight);
      }
      else{
        $('.rightMenu').css('background','grey');
      }
    },
    up: function(){
      this.$root.eventBus.$emit('mshow',false);
      this.$root.eventBus.$emit('mrshow',false);
      var mwheight= $('.menc').height();
      var mheight= $('.mencx').height()-25.74;
      var total_hm= $('.mencx').height()-25.74;
      var htop= $('.mencx').css('top');
      var str= htop.split('p');
      var compare= parseInt(str[0]);

      console.log("up");
      console.log("top:"+compare);
      console.log('height:'+mheight);
      if(mheight>mwheight && compare<0){
        console.log('up开始');
        console.log('height:'+mheight);
        console.log('wheight:'+mwheight);
        $('.mencx').animate({top: '+=85rem'}, 'fast');
        mheight +=1588;
        compare +=1588;
        mheight<mwheight?$('.rightMenu').css('background','grey'):$('.rightMenu').css('background','white');
        console.log("nowTop:"+compare);
        mheight>mwheight && compare>=0?$('.middleMenu').css('background','grey'):$('.middleMenu').css('background','white');
        console.log('up结束');
        console.log('height:'+mheight);
        console.log('wheight:'+mwheight);
      } else{
        $('.rightMenu').css('background','white');
      }
    },
    hidden_menu: function(){
      if(!$('#men').hasClass('active') && this.msg_show === 'ok' ||  this.msg_show === true ){
        $('#men').addClass('active');
      }
    },
    show_account_info: function(){
      console.log("账户信息");
      if(accountInfo==false){
        this.$root.eventBus.$emit('accountInfo',true);
      }else{
        this.$root.eventBus.$emit('accountInfo',false);
      }
    }
  },
  mounted() {
    var mwheight = $('.menc').height();
    var mheight= $('.mencx').height();
    if(mheight>mwheight){
      $('.rightMenu').css('background','white');
      $('.middleMenu').css('background','white');
    } else{
      $('.rightMenu').css('background','grey');
      $('.middleMenu').css('background','grey');
    }
  },
  created(){
    this.$root.eventBus.$on('mshow', () => {
      this.mshow= false;

    });
    this.$root.eventBus.$on('msg_show', () => {
      this.msg_show = 'ok';
      this.msg_show = true ;
    });

  }
}
</script>
<style lang="css">
#bottomMenu{ flex: none; -webkit-flex: none; display: flex; flex-direction: row; height: 8rem; width: 100%; border-top: 2px solid #999;}
.leftMenu,.middleMenu{ width: 8rem; border-right: 1px solid #999; display: flex!important; justify-content: center; align-items: center; font-size: 3rem;}
.rightMenu{ flex: 1; -webkit-flex: 1; border-right: 1px solid #999; display: flex!important; justify-content: center; align-items: center; font-size: 3rem;}
</style>
