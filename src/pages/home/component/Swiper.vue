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
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperLists: [{
        id: '000001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/f0/3320ab387c63a602.jpg_750x200_8bdd9ddb.jpg'
      }, {
        id: '000002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/f2/91b285a08ee21c02.jpg_750x200_8a73fd08.jpg'
      }, {
        id: '000003',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/15/9250dbc86a456302.jpg_750x200_b423f532.jpg'
      }]
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
