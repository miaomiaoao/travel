<template>
  <div class="home-header">
    <div class="home-header-left">
      <span class="iconfont">&#xe6ec;</span>
    </div>
    <div class="home-header-center">
      <span class="iconfont">&#xe6ac;</span>
      搜索旅游地/酒店/景点
    </div>
    <div class="home-header-right">
      <span class="iconfont">{{ city }}&#xe614;</span>
    </div>
  </div>
</template>
<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>
<style lang="scss" scoped>
@import '~styles/variable.scss';

.home-header {
  height: .86rem;
  line-height: .86rem;
  background:  $bgColor;
  display: flex;
  text-align: center;
  color: #333;

  .home-header-left {
    height: .64rem;
    width: .64rem;
    line-height: .64rem;
    float: left;
    background: #ffffff;
    border-radius: 50%;
    margin: .11rem .11rem;
    .iconfont {
        font-size: 18px;
    }
  }

  .home-header-center {
    flex: 1;
    line-height: 0.66rem;
    background-color: #ffffff;
    margin: 0.1rem .1rem;
    border-radius: .1rem;
    text-align: left;
    padding-left: .2rem;
     .iconfont {
        font-size: 13px;
    }
  }

  .home-header-right {
    height: .64rem;
    width: 1rem;
    line-height: .64rem;
    float: right;
    // background: #ffffff;
    // border-radius: 50%;
    margin: .11rem .11rem;
    .iconfont {
        font-size: 14px;
        color: white;
    }
  }
}
</style>
