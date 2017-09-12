<template>
  <div id="menudiv" v-if="mshow===true">
    <div class="menudiv_cont">
      <div class="title">
        <div class="img">
          <img src="../assets/img/visible.png" class="one"/>
        </div>
        <div class="subTitle">
          <div>隐藏左侧栏</div>
        </div>
      </div>

      <div class="title">
        <div class="img">
          <img src="../assets/img/account.png" class="two"/>
        </div>
        <div class="subTitle">
          <div>账户信息</div>
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
</template>
<script>
export default {
  
}
</script>
<style lang="css">
#menudiv{ width: 100%; height: 15%; border: 1px solid #999; position: absolute; bottom: 7.8rem; background-color: white; font-size: 2rem; display: flex;}
.menudiv_cont{ padding-top: 1rem}
.one,.two,.three{ width: 2.5rem;}
</style>
