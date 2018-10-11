<template>
  <div class="wrapper">
    <swiper :options="swiperOption" ref="mySwiper">
        <!-- slides -->
        <swiper-slide v-for="item in list" :key="item.id">
            <img class="swiper-img" :src="item.imgUrl"/>
        </swiper-slide>
        <div class="swiper-paginoHation"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'carrousel',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        autoplay: true
      }
    }
  },
  computed: {
    swiper () {
      return this.$refs.mySwiper.swiper
    }
  },
  mounted () {
    // current swiper instance
    // 然后你就可以使用当前上下文内的swiper对象去做你想做的事了
    console.log('this is current swiper instance object', this.swiper)
    this.swiper.slideTo(3, 1000, false)
  }
}
</script>
<style lang="stylus" scoped>
    .wrapper >>> .swiper-pagination-bullet-active
      background: #fff
    .wrapper
      overflow:hidden
      width: 100%
      height: 0
      padding-bottom: 26.67%
      .swiper-img
        width: 100%
</style>
