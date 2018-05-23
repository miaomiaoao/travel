<template>
  <swiper :options="swiperOption">
    <swiper-slide v-for="(page, index) of pages" :key="index">
      <div class="icons">
      <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl"/>
          </div>
          <p class="icon-desc">{{ item.desc }}</p>
      </div>
      </div>
    </swiper-slide>
  </swiper>
</template>
<script>
export default {
  name: 'HomeIcon',
  data () {
    return {
      iconLists: [{
        id: '000001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        desc: '热门景点热门景点热门景点热门景点热门景点'
      },
      {
        id: '000002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/3e/86314b2af03b7502.png',
        desc: '水上乐园'
      },
      {
        id: '000003',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
        desc: '必游榜单'
      },
      {
        id: '000004',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/95/8d02011d149bdb02.png',
        desc: '成都定制'
      },
      {
        id: '000005',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/97/02f5043b51b2102.png',
        desc: '情迷九寨'
      },
      {
        id: '000006',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
        desc: '芙蓉七景'
      },
      {
        id: '000007',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/b6/37560ece9c62b502.png',
        desc: '成都周边'
      },
      {
        id: '000008',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ed/cf572be30fc32f02.png',
        desc: 'Q+精选'
      }, {
        id: '000009',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ed/cf572be30fc32f02.png',
        desc: 'Q+精选'
      }],
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconLists.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>
<style lang="scss" scoped>
@import '~styles/variable.scss';
.icons {
    height: 0;
    overflow: hidden;
    padding-bottom: 50%;
    .icon {
        width: 25%;
        float: left;
        padding-bottom: 25%;
        overflow: hidden;
        position: relative;
        height: 0;
        .icon-img {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0.44rem;
            // box-sizing: border-box;
            // padding: .1rem;
            .icon-img-content {
                height: 100%;
                display: block;
                margin: 0 auto;
            }
        }

        .icon-desc {
            position: absolute;
            left: 0;
            right: 0;
            bottom: 0;
            line-height: 0.44rem;
            height: 0.44rem;
            color: $bgTextColor;
            text-align: center;
            @extend .txt-wrap
        }
    }
}
</style>
