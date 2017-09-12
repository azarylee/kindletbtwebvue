<template>
  <div id="app" class="flexPosition">
    <div class="flexPosition flexDetail" id="core">
      <mainmenu></mainmenu>
      <maincontent></maincontent>
    </div>
    <div id="accountInfo" v-show="accountInfo">
      <h1 class="logo_name">IFFEED</h1>
      <div class="account_frame">
        <p class="username">尊敬的用户：<b>乘风破浪</b></p>
        <p class="account_info">你的账户将于<b>2018-08-08 14：29</b>到期</p>
        <img src="./assets/img/weixin.png" class="erweima">
        <button type="button" class="btn btn-default" id="go_back" @click="goback">返回</button>
      </div>
    </div>
    <div id="font_choice" v-show="fontchoice">
      <div class="dialog-box" id="box">
        <div class="dialog-head">
          <span class="dialog-title h4">设置字体大小</span>
          <span id="dialog_close" @click="dialog_close">X</span>
        </div>
        <div class="dialog-content">
          <div class="container">
              <div class="font_family">
                   <div class="circle" @click="choose_ff(0)" :style="{'background-color':(fontff==0?'black':'white')}"></div><div class="fontStyle">宋体</div>
              </div>
              <div class="font_family">
                   <div class="circle" @click="choose_ff(1)" :style="{'background-color':(fontff==1?'black':'white')}"></div><div class="fontStyle">黑体</div>
              </div>
              <div class="font_family">
                   <div class="circle" @click="choose_ff(2)" :style="{'background-color':(fontff==2?'black':'white')}"></div><div class="fontStyle">楷体</div>
              </div>
              <div class="font_family">
                   <div class="circle" @click="choose_ff(3)" :style="{'background-color':(fontff==3?'black':'white')}"></div><div class="fontStyle">圆体</div>
              </div>
              <div class="font_size">
                  <div><span id="font1" @click="choose_font(0)" :style="{'color':(fontItem==0?'white':'black'),'background-color':(fontItem==0?'black':'white')}">Aa</span></div>
                  <div><span id="font2" :style="{'color':(fontItem==1?'white':'black'),'background-color':(fontItem==1?'black':'white')}" @click="choose_font(1)">Aa</span></div>
                  <div><span id="font3" :style="{'color':(fontItem==2?'white':'black'),'background-color':(fontItem==2?'black':'white')}" @click="choose_font(2)">Aa</span></div>
                  <div><span id="font4" :style="{'color':(fontItem==3?'white':'black'),'background-color':(fontItem==3?'black':'white')}" @click="choose_font(3)">Aa</span></div>
                  <div><span id="font5" :style="{'color':(fontItem==4?'white':'black'),'background-color':(fontItem==4?'black':'white')}" @click="choose_font(4)">Aa</span></div>
                  <div><span id="font6" :style="{'color':(fontItem==5?'white':'black'),'background-color':(fontItem==5?'black':'white')}" @click="choose_font(5)">Aa</span></div>
              </div>
          </div>
        </div>
      </div>
    </div>
    </div>
    <!-- <router-view></router-view> -->
  </div>
</template>

<script>
import mainmenu from './components/menu'
import maincontent from './components/content'

export default {
  data(){
    return{
      accountInfo: false,
      fontchoice: true,
      fontItem: 1,
      fontff:1,
      fontchoice: false
    }
  },
  components:{
    mainmenu,
    maincontent,
  },
  methods:{
    goback: function(){
      this.accountInfo=  false;
      this.$root.eventBus.$emit('mshow',false);
      this.$root.eventBus.$emit('mrshow',false);
    },
    choose_font: function(e){
      this.fontItem= e;
    },
    choose_ff: function(a){
      this.fontff= a;
    },
    dialog_close: function(){
      console.log(1);
      this.fontchoice= false;
    }
  },
  created(){
    this.$root.eventBus.$on('accountInfo', () => {
      this.accountInfo= true;
      this.msg_show= false;
    });
    this.$root.eventBus.$on('fontchoice', () => {
      this.fontchoice= true;
    });
  }
}
</script>

<style>
#app{ display: flex; flex-direction: row; height: 100%; width: 100%; overflow: hidden;}
.flexDetail{ display: flex; display: -moz-box; display: -webkit-box; display: -ms-flexbox; display: -webkit-flex;}
.flexPosition{ position: absolute !important; left: 0; right: 0; top: 0; bottom: 0; overflow: hidden;}
/*menu*/
.title{ display: flex; flex-direction: row; display: -webkit-flex; display: -webkit-box;}
.img{ flex: none; -webkit-flex: none; text-align: center; width: 2.8rem;
    height: 2.8rem; justify-content: center; max-height: 100%; max-width: 100%; line-height: 2rem; margin: 1rem;}
.subTitle{ flex: 1; -webkit-flex: 1; -webkit-box-flex: 1; line-height: 4rem; font-size: 2.1rem; overflow: hidden; white-space: nowrap; text-overflow: ellipsis;}
.title>span{ margin-top: 0.4em;}
.badge{ position: relative; right: 1rem; font-size: 1.5rem!important;}
/*menu*/
/*account info*/
#accountInfo{ width: 100%; height: 100%; background-color: white; display: flex; justify-content: center; position: absolute;}
.logo_name{position: absolute; font-size: 5rem; font-weight: bolder; top: 12rem; margin-bottom: 3rem; width: 100%; height: 10%; text-align: center; border-bottom: 1px solid #999;}
.account_frame{ width: 80%; height: 55%; border: 2px solid black; border-radius: 25px; display: flex; justify-content: center; align-items: center; font-size: 2rem; flex-wrap: wrap; margin: auto auto; margin-top: 30rem;}
.username{ width: 100%; text-align: center; font-size: 3rem;}
.account_info{ width: 100%; text-align: center; font-size: 2.5rem;}
.erweima{ margin-right: 15rem; margin-left: 15rem;}
#go_back{ width: 10rem; height: 5rem; font-size: 2rem;}
/*account info*/
/*font choice*/
#font_choice{ width: 100%; height: 100%; background-color: white;display: flex; justify-content: center; align-items: center; position: absolute;}
.dialog-box{ width: 80%; height: 55%; margin: 0px -250px; border-radius: 10px;
        background: white; z-index: 1; border: 5px solid black;}
.dialog-head{height: 20%;padding: 0px 20px; cursor: move; border-bottom: 2px solid black; font-size: 200%;}
.dialog-title{ display: block; font-size: 3rem!important; text-align: center; width: 100%; height: 100%; line-height: 10rem!important;}
#dialog_close{position: relative; top: -8rem; left: 43rem; font-size: 2rem;}
#dialog-close:hover{background: #eee; padding: 0px 10px; }
.dialog-content{height: 78%;}
.dialog-frame{height: 100%;width: 100%}

.font_family{ width: 100%; height: 2rem; padding: 2rem 7rem; box-sizing: content-box;}
.circle{width: 50px; height: 50px; border: 3px solid black; border-radius: 25px;}
.fontStyle{position: relative; left: 5rem; bottom: 2.8rem; font-size: 2rem;}
.currentSelected{background: black;}
/*弹出框字体设定*/

/*弹出框大小设定*/
.font_size{width: 100%; height: 110px; padding: 3rem; margin-top: 1rem;}
.font_size>div{ display: inline; margin: 1rem;}
#font1{font-size: 2.05rem; padding: 1rem;}
#font2{font-size: 2.20rem; padding: 1rem;}
#font3{font-size: 2.35rem; padding: 1rem; font-weight: bold}
#font4{font-size: 2.50rem; padding: 1rem; font-weight: bold}
#font5{font-size: 2.65rem; padding: 1rem; font-weight: bolder}
#font6{font-size: 2.85rem; padding: 1rem; font-weight: bolder; position: relative; top: 25px;}
.currentFontsize{background: black; color: white;}
/*font choice*/
/*字体*/
.fhei{
 font-family:  STHeiti, san-serif,'Heiti SC','黑体',"sans-serif",PingFang, "Hiragino Sans GB", "Microsoft YaHei", "WenQuanYi Micro Hei", STHei, STHeiti, "MYing Hei S", "MYing Hei T"
}
.fsong{
  font-family:  STSong, serif,'宋体','song T',"sans-serif", "Adobe Songti Std", "Song S", "Song T", NSimSun;
}
.fyuan{
  font-family: STYuan, san-serif,'Hiragino Mincho Pro','微软雅黑','FZHei-B01',"sans-serif",STYuan, STYuanti, YouYuan;
}
.fkai{
  font-family: STKai, serif,'Kaiti SC',"楷体","楷体_GB2312",'Kindle Kai',"sans-serif",STKai, STKaiti, KaiTi, "MKai PRC";
}
.Palatino{
  font-family: "Palatino",STKai, STKaiti, KaiTi, "MKai PRC",serif;
}
.Ember{
  font-family:"Amazon Ember",STKai, STKaiti, KaiTi, "MKai PRC",sans-serif
}
.Bookerly{
  font-family:"Bookerly",STKai, STKaiti, KaiTi, "MKai PRC",serif
}
.Baskerville{
  font-family: "Baskerville",STKai, STKaiti, KaiTi, "MKai PRC",serif;
}
/*字体*/
/*底部导航显示隐藏div*/
#menudiv{ width: 100%; height: 16%!important; border: 1px solid #999; position: absolute; bottom: 8rem!important; background-color: white; font-size: 2rem; display: flex;}
.menudiv_cont{ padding-top: 1rem}
.one,.two,.three{ width: 2.5rem;}
/*底部导航显示隐藏div*/
#rmenudiv{ width: 100%; height: 11%; border: 1px solid #999; position: absolute; bottom: 8rem; background-color: white; font-size: 2rem; display: flex;}
.active{ display: none;}
</style>
