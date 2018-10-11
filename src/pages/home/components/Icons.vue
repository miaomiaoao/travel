<template>
  <div class="icons">
      <swiper :option="swiperOption" ref="mySwiper">
          <swiper-slide v-for="(page, index) in pages" :key="index">
              <div class="icon" v-for="item in page" :key="item.id">
                <div class="icon-img">
                    <img class="icon-img-content" :src="item.imgUrl">
                </div>
                <p class="icon-desc">{{item.desc}}</p>
            </div>
          </swiper-slide>
      </swiper>
  </div>
</template>
<script>
export default {
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        autoplay: false
      },
      iconLists: [
        {
          id: 0,
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
          desc: '景点门票'
        }, {
          id: 1,
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
          desc: '景点门票'
        }, {
          id: 2,
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
          desc: '景点门票'
        }, {
          id: 3,
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
          desc: '景点门票'
        }, {
          id: 4,
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
          desc: '景点门票'
        }, {
          id: 5,
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
          desc: '景点门票'
        }, {
          id: 6,
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
          desc: '景点门票'
        }, {
          id: 7,
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
          desc: '景点门票'
        }, {
          id: 8,
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
          desc: '景点门票'
        }, {
          id: 9,
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
          desc: '景点门票'
        }, {
          id: 10,
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
          desc: '景点门票'
        }, {
          id: 11,
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
          desc: '景点门票'
        }
      ]
    }
  },
  props: {
    list: Array
  },
  computed: {
    pages () {
      const pages = []
      if (this.list.length > 8) {
        this.list.forEach((item, index) => {
          const page = Math.floor(index / 8)
          if (!pages[page]) {
            pages[page] = []
          }
          pages[page].push(item)
        })
      }
      return pages
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/mixins.styl'
@import '~styles/variable.styl'
    .icons
      margin-top: .1rem
    .icon
      overflow: hidden
      width: 25%
      height: 0
      float: left
      padding-bottom: 25%
      position: relative
      .icon-img
        position: absolute
        left: 0
        right: 0
        top: 0
        bottom: 0.44rem
        padding: .1rem
        .icon-img-content
          display: block
          margin: 0 auto
          height: 100%
      .icon-desc
        position: absolute
        left: 0
        right: 0
        bottom: 0
        text-align: center
        height: 0.44rem
        line-height: .44rem
        color: $bgTextColor
        ellipsis()
</style>
