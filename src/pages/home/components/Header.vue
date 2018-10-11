<template>
  <div class="header">
    <div class="header-left iconfont">&#xe660;</div>
    <div class="header-input">
      <span class="iconfont">&#xe651;</span>输入景点/城市/游玩/主题</div>
    <div class="header-right">
      {{city}}
      <span class="iconfont">&#xe65c;</span>
      </div>
  </div>
</template>
<script>

export default {
  name: 'Header',
  props: {
    city: String
  }
}
</script>
<style lang="stylus" scoped>
  .header
     display: flex
     background: #00bcd4
     line-height: .86rem
     color: #fff
     .header-left
        width: .64rem
        float: left
        text-align: center
      .header-input
        flex: 1
        height: .64rem
        line-height: .64rem
        margin-left: .2rem
        background: #ffffff
        border-radius: .1rem
        margin-top: .12rem
        color: #ccc
        padding-left: 0.2rem
      .header-right
        width: 1.22rem
        float: right
        text-align: center;

</style>
