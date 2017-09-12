<template>
  <div id="cont">
    <div class="waitMsg" v-if="msg_show===true">{{ message }}</div>
    <!-- <div class="blank" v-else-if="msg_show===false"></div> -->
    <div class="contentList flexPosition" v-else-if="msg_show=='ok'">
      <div class="contentc" @click="hidde_rm">
        <div class="contentcx" v-if="science===true" style="top:0px">
          <div class="article">
            <div class="contTitle" name="title">知识付费市场很大，优质内容的生产依然是重中之重</div>
            <div class="contDetail">
              <div class="author" name="author">吴晓波频道</div>
              <div class="date">{{ date1 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">Alexa进大学，亚马逊打算这样实现“一石三鸟”</div>
            <div class="contDetail">
              <div class="author" name="author">DeepTech深科技</div>
              <div class="date">{{ date1 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">iPhone8什么时候上市？或9月22日发售</div>
            <div class="contDetail">
              <div class="author" name="author">科技讯</div>
              <div class="date">{{ date2 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">谷歌萤火虫无人车退役 开始转向量产车研发</div>
            <div class="contDetail">
              <div class="author" name="author">Waymo</div>
              <div class="date">{{ date3 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">苹果无人车测试短途运送 与汽车厂商合作</div>
            <div class="contDetail">
              <div class="author" name="author">新浪新闻</div>
              <div class="date">{{ date3 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">iPhone口袋内爆炸烧伤用户</div>
            <div class="contDetail">
              <div class="author" name="author">北京晨报网</div>
              <div class="date">{{ date3 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">新无线网技术或将取代Wi-Fi</div>
            <div class="contDetail">
              <div class="author" name="author">网易新闻</div>
              <div class="date">{{ date4 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">美国首次将超级计算机送上太空</div>
            <div class="contDetail">
              <div class="author" name="author">cnBeta全文版</div>
              <div class="date">{{ date4 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">喜茶蹲、喜茶蹲、喜茶蹲完便利店蹲；便利店蹲、便利店蹲、便利店蹲完该谁蹲？</div>
            <div class="contDetail">
              <div class="author" name="author">创业帮杂志</div>
              <div class="date">{{ date4 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">小岛秀夫喜迎54岁生日《死亡搁浅》风格蛋糕亮了</div>
            <div class="contDetail">
              <div class="author" name="author">cnBeta全文版</div>
              <div class="date">{{ date5 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">张旭豪发公开信：百度外卖保持既有品牌和独立运营</div>
            <div class="contDetail">
              <div class="author" name="author">新浪科技>焦点新闻</div>
              <div class="date">{{ date5 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">咦，捡到一个珠光宝气的小金块？快放下，那是蛾子的家！</div>
            <div class="contDetail">
              <div class="author" name="author">果壳网</div>
              <div class="date">{{ date5 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">2017世界机器人大会：不容错过的15款机器人</div>
            <div class="contDetail">
              <div class="author" name="author">中国科技网</div>
              <div class="date">{{ date5 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">开学季遇“黑科技”：新生刷脸报到 网上挑寝室</div>
            <div class="contDetail">
              <div class="author" name="author">中国新闻网</div>
              <div class="date">{{ date5 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">00后CEO：互联网创业时代哪有那么多“神童”</div>
            <div class="contDetail">
              <div class="author" name="author">新京报</div>
              <div class="date">{{ date5 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">互联网域名管理办法发布 域名注册必须实名</div>
            <div class="contDetail">
              <div class="author" name="author">法制日报</div>
              <div class="date">{{ date5 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">小米MIX2真机亮屏：开黑利器</div>
            <div class="contDetail">
              <div class="author" name="author">科技讯</div>
              <div class="date">{{ date5 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">盘点王者荣耀中最智障的队友有哪些</div>
            <div class="contDetail">
              <div class="author" name="author">科技讯</div>
              <div class="date">{{ date5 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">华为Mate10处理器确认：麒麟970强势来袭！</div>
            <div class="contDetail">
              <div class="author" name="author">科技讯</div>
              <div class="date">{{ date5 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">索尼大法情怀依旧：音频新品目不暇接</div>
            <div class="contDetail">
              <div class="author" name="author">法制日报</div>
              <div class="date">{{ date5 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">盘点王者荣耀中最智障的队友有哪些</div>
            <div class="contDetail">
              <div class="author" name="author">科技讯</div>
              <div class="date">{{ date5 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">华为Mate10处理器确认：麒麟970强势来袭！</div>
            <div class="contDetail">
              <div class="author" name="author">科技讯</div>
              <div class="date">{{ date5 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">索尼大法情怀依旧：音频新品目不暇接</div>
            <div class="contDetail">
              <div class="author" name="author">法制日报</div>
              <div class="date">{{ date5 }}</div>
            </div>
          </div>

        </div>
        <div class="contentcx" v-if="business===true" style="top:0px">
          <div class="article">
            <div class="contTitle" name="title">周黑鸭创始人：经营企业，逐利则败，逐产品则得人心</div>
            <div class="contDetail">
              <div class="author" name="author">长江商业评论</div>
              <div class="date">{{ date1 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">【关注】首次曝光！海军新型战机在我国南海上空夜航单飞</div>
            <div class="contDetail">
              <div class="author" name="author">经济日报</div>
              <div class="date">{{ date1 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">在唯快不破的互联网大时代，慢热谨慎的网易为什么成了？</div>
            <div class="contDetail">
              <div class="author" name="author">吴晓波频道</div>
              <div class="date">{{ date1 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">【夜读】为什么越来越多人在朋友圈戒掉了情绪？</div>
            <div class="contDetail">
              <div class="author" name="author">21世纪经济报道</div>
              <div class="date">{{ date2 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">用脚投票的选择——中国人口迁移跟踪（深度！）</div>
            <div class="contDetail">
              <div class="author" name="author">21世界经济报道</div>
              <div class="date">{{ date2 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">2017中国民企500强发布 全名单看这里！</div>
            <div class="contDetail">
              <div class="author" name="author">经济日报</div>
              <div class="date">{{ date3 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">商务部：将加强中国企业境外投资真实性的审查</div>
            <div class="contDetail">
              <div class="author" name="author">中国新闻网</div>
              <div class="date">{{ date3 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">调控政策延续去年第四季度以来的收紧态势 楼市降温已成不争事实</div>
            <div class="contDetail">
              <div class="author" name="author">证券日报</div>
              <div class="date">{{ date3 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">8月份IPO审核速度放缓 环比大幅下降</div>
            <div class="contDetail">
              <div class="author" name="author">证券日报</div>
              <div class="date">{{ date4 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">过分炒作“养老金入市”不可取</div>
            <div class="contDetail">
              <div class="author" name="author">经济日报</div>
              <div class="date">{{ date5 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">董明珠牵线200亿关联交易惹争议 或影响银隆上市</div>
            <div class="contDetail">
              <div class="author" name="author">证券日报</div>
              <div class="date">{{ date5 }}</div>
            </div>
          </div>

          <div class="article">
            <div class="contTitle" name="title">逾900亿客户备付金"入表" 支付机构利息收入面临冲击</div>
            <div class="contDetail">
              <div class="author" name="author">每日经济新闻</div>
              <div class="date">{{ date5 }}</div>
            </div>
          </div>

        </div>
        <div class="contentcx" v-if="douban===true" id="douban" style="top:0px">
          <div class="article">
            <div class="contTitle" name="title">经营企业，逐利则败，逐产品则得人心</div>
            <div class="contDetail">
              <div class="author" name="author">长江商业评论</div>
              <div class="date">{{ date1 }}</div>
            </div>
          </div>
        </div>
        <div class="contentcx" v-if="toutiao===true" id="toutiao" style="top:0px">
          <div class="article">
            <div class="contTitle" name="title">吴京《战狼2》50亿庆功宴，为什么只请了两个人？</div>
            <div class="contDetail">
              <div class="author" name="author"></div>
              <div class="date">{{ date1 }}</div>
            </div>
          </div>
          <div class="article">
            <div class="contTitle" name="title">老公外出打工三年，带回50万，知道钱的来历，我把家砸了离婚</div>
            <div class="contDetail">
              <div class="author" name="author"></div>
              <div class="date">{{ date2 }}</div>
            </div>
          </div>
          <div class="article">
            <div class="contTitle" name="title">他们为求一夜爆红，草根身份造假多年！韩红当面揭穿直接轰下台！</div>
            <div class="contDetail">
              <div class="author" name="author"></div>
              <div class="date">{{ date3 }}</div>
            </div>
          </div>
        </div>
        <div class="contentcx" v-if="zhihu===true" id="zhihu" style="top:0px"></div>
      </div>
      <bottommenur></bottommenur>
    </div>
  </div>
</template>
<script>
import bottommenur from '../components/bottommenur'

export default {
  data(){
    return{
      message: '请稍等，正在努力加载中……',
      msg_show: false,
      date1: '1d',
      date2: '6h',
      date3: '4h',
      date4: '3h',
      date5: '1h',
      accountInfo: false
    }
  },
  components:{
    bottommenur
  },
  methods:{
    change: function(){
      this.msg_show= 'ok';
    },
    hidde_rm: function(){
      this.$root.eventBus.$emit('mshow',false);
      this.$root.eventBus.$emit('mrshow',false);
    }
  },
  created() {
    this.$root.eventBus.$on('msg_show', () => {
        this.msg_show = true ;
        setTimeout(() =>{
          this.change();
        },2000);
    });
    this.$root.eventBus.$on('science', () => {
      this.science= true;
      this.business= false;
      this.douban= false;
      this.toutiao= false;
      this.zhihu= false;
    });
    this.$root.eventBus.$on('business', () => {
      this.business= true;
      this.science= false;
      this.douban= false;
      this.toutiao= false;
      this.zhihu= false;
    });
    this.$root.eventBus.$on('douban', () => {
      this.business= false;
      this.science= false;
      this.douban= true;
      this.toutiao= false;
      this.zhihu= false;
    });
    this.$root.eventBus.$on('toutiao', () => {
      this.business= false;
      this.science= false;
      this.douban= false;
      this.toutiao= true;
      this.zhihu= false;
    });
    this.$root.eventBus.$on('zhihu', () => {
      this.business= false;
      this.science= false;
      this.douban= false;
      this.toutiao= false;
      this.zhihu= true;
    });

  }
}
</script>
<style>
#cont{ flex: 1; -webkit-flex: 1; display: flex; flex-direction: column; width: 100%; height: 100%; position: relative;}
.blank{ height: 100%;}
.waitMsg{ display: flex; justify-content: center; align-items: center; height: 100%; font-size: 2rem;}
.waitMsg>span{align-items: center; justify-content: center;}
.contentList{ display: flex; flex-direction: column; display: -webkit-box; height: 100%;}
.contentc{ flex: 1; -webkit-flex: 1; width: 100%; overflow: hidden;}
.contentcx{  position: relative;}
.article{ width: 90%; margin: 1rem auto; height: 4.8rem; margin-bottom: 5rem;}
.contTitle{ overflow: hidden; white-space: nowrap; text-overflow: ellipsis; font-size: 2.5rem; width: 90%; font-weight: bold;}

.contDetail{ flex-wrap: nowrap; display: flex; flex-direction: row;border-bottom: 1px solid silver; padding-bottom: 1rem;}
.author{ font-size: 2rem; flex: 1; -webkit-flex: 1; width: 60%;}
.date{ font-size: 2rem; flex:none; -webkit-flex: none; text-align: right;}
</style>
