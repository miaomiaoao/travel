<!-- The ref attr used to find the swiper instance -->
<template>
<div class="home-swiper">
  <swiper :options="swiperOption">
    <!-- slides -->
    <swiper-slide  v-for="item of swiperLists" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl"/>
    </swiper-slide>
    <!-- Optional controls -->
    <div class="swiper-pagination"  slot="pagination"></div>
    <!-- <div class="swiper-button-prev" slot="button-prev"></div>
    <div class="swiper-button-next" slot="button-next"></div> -->
    <!-- <div class="swiper-scrollbar"   slot="scrollbar"></div> -->
  </swiper>
</div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    swiperLists: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      }
    }
  }
}
</script>
<style lang="scss" scoped>
.swiper-pagination-bullet-active {
    background: red !important;
}
.home-swiper {
    width: 100%;
    height:0;
    overflow: hidden;
    padding-bottom: 31.25%;
    .swiper-img {
        width: 100%;
        background: #eee;

    }
}

</style>
