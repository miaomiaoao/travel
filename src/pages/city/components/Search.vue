<template>
    <div class="search">
        <input type="text"  placeholder="输入城市名或者拼音">
    </div>
</template>
<script>
export default {
}
</script>
<style lang="stylus" scoped>
@import '~styles/variable.styl'
.search
    background: $bgColor
    height: .72rem
    padding: .1rem

    input
      background: #fff
      margin: 0 auto
      width: 100%
      height: 0.62rem
      padding: 0.1rem
      box-sizing: border-box
      border-radius: .06rem
      text-align: center
</style>
