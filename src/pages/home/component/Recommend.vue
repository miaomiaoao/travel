<template>
    <div>
        <div class="recommend-title">热销推荐</div>
        <ul>
            <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
                <!--img标签外层添加一个div 用于将图片撑开-->
                <div class="item-img-wrapper">
                    <img src="item.imgUrl" class="item-img"/>
                </div>
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-button">查看详情</button>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/201403/03/77a8f60ea243465fdf2c937e2edd33dd.jpg_200x200_51dd1e90.jpg',
        title: '大连圣亚海洋世界',
        desc: '浪漫大连首站，浪漫的海洋主题乐园'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1705/ed/edd4063a442f30c1a3.img.jpg_200x200_724f9e6a.jpg',
        title: '大连圣亚海洋世界',
        desc: '浪漫大连首站，浪漫的海洋主题乐园'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1705/ed/edd4063a442f30c1a3.img.jpg_200x200_724f9e6a.jpg',
        title: '大连圣亚海洋世界',
        desc: '浪漫大连首站，浪漫的海洋主题乐园'
      }]
    }
  }
}
</script>
<style lang="scss" scoped>
@import '~styles/variable.scss';
.recommend-title {
    line-height: .8rem;
    background-color: #eee;
    text-indent: .2rem;
    margin-top: .2rem;
}
.item {
    display: flex;
    height: 1.9rem;
    overflow: hidden;
    .item-img {
        height: 1.7rem;
        width: 1.7rem;
        padding: .1rem;
    }
    .item-info {
        flex: 1;
        padding: .1rem;
        .item-title {
            line-height: .54rem;
            font-size: .32rem;
            @extend .txt-wrap
        }
        .item-desc {
            line-height: .4rem;
            color: #ccc;
        }
        .item-button {
            line-height: .5rem;
            background: #ff9300;
            padding: 0 .16rem;
            border-radius: .06rem;
            margin-top: .2rem;
        }
    }
}
</style>
