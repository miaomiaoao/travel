<template>
    <div>
        <div class="title">热销推荐</div>
        <div class="item border-bottom">
           <img class="item-img" src="http://img1.qunarzz.com/sight/p0/1706/49/4919241e3c43dfe2a3.water.jpg_200x200_3d9dfcd6.jpg">
           <div class="item-info">
               <div class="item-info-title">大连生涯海洋世界</div>
               <div class="item-info-desc">浪漫大连首站,浪漫的海洋乐园</div>
               <button class="item-button">查看详情</button>
           </div>
        </div>
    </div>
</template>
<script>
export default {
}
</script>
<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.title
    line-height: .8rem
    background: #eeeeee
    text-indent: .2rem
    margin-top: .2rem
.item
    overflow: hidden
    display: flex
    height: 1.9rem
    .item-img
        width: 1.7rem
        height: 1.7rem
        padding: 0.1rem
    .item-info
        flex: 1
        padding: .1rem
        .item-info-title
            line-height: .54rem
            font-size: .32rem
            ellipsis()
        .item-info-desc
            line-height: .4rem
            color: #ccc
            ellipsis()
        .item-button
            line-height: .44rem
            margin-top: .16rem
            background: #ff9300
            padding: 0 .2rem
            border-radius: .06rem
            color: #fff
</style>
