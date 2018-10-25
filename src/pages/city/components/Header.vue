<template>
    <div class="header">
        <router-link to="/">
           <div class="header-left iconfont">&#xe660;</div>
        </router-link>
        <div class="title">城市选择</div>
    </div>
</template>
<script>
export default {
}
</script>
<style lang="stylus" scoped>
@import '~styles/variable.styl'
    .header
       background: $bgColor
       height: .86rem
       line-height: .86rem
       display: flex
       color: #fff
       a
           color: #fff
       .header-left
           width: .64rem
           text-align: center
       .title
           text-align: center
           flex: 1
</style>
