<template>
  <div class="header">
    <div class="header-left iconfont">&#xe660;</div>
    <div class="header-input">
      <span class="iconfont">&#xe651;</span>输入景点/城市/游玩/主题
    </div>
    <router-link to="/city">
       <div class="header-right">
        {{this.city}}
        <span class="iconfont">&#xe65c;</span>
      </div>
    </router-link>
  </div>
</template>
<script>
import { mapState } from 'vuex'
export default {
  name: 'Header',
  computed: {
    ...mapState(['city'])
  }
}
</script>
<style lang="stylus" scoped>
  .header
     display: flex
     background: #00bcd4
     line-height: .86rem
     color: #fff
     a
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
        padding-left: .2rem
        min-width: 1.04rem
        float: right
        text-align: center;
</style>
