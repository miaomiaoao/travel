<template>
  <div>
    <home-header :city="city"></home-header>
    <home-swiper :swiperLists="swiperLists"></home-swiper>
    <home-icon :iconLists="iconLists"></home-icon>
    <home-recommend :recommendLists="recommendLists"></home-recommend>
    <home-weekend></home-weekend>
  </div>
</template>
<script>
import HomeHeader from './component/Header.vue'
import HomeSwiper from './component/Swiper.vue'
import HomeIcon from './component/Icon.vue'
import HomeRecommend from './component/Recommend.vue'
import HomeWeekend from './component/Weekend.vue'
import axios from 'axios'
export default {
  name: 'Home',
  data () {
    return {
      city: '',
      swiperLists: [],
      iconLists: [],
      recommendLists: []
    }
  },
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcon,
    HomeRecommend,
    HomeWeekend
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        this.city = '北京'
        this.swiperLists = res.data.swiperLists
        this.iconLists = res.data.iconLists
        this.recommendLists = res.data.recommendLists
        console.log(this.swiperLists)
        console.log('***************')
      }
      console.log(res)
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>
