<template>
  <div>
    <home-header></home-header>
    <Swiper :list="swiperLists"></Swiper>
    <icons :list="iconLists"></icons>
    <recommend :list="recommendLists"></recommend>
    <weekend :list="weekendLists"></weekend>
  </div>
</template>
<script>
import HomeHeader from './components/Header'
import Swiper from './components/Swiper'
import Icons from './components/Icons'
import Recommend from './components/Recommend'
import Weekend from './components/Weekend'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    Swiper,
    Icons,
    Recommend,
    Weekend
  },
  data () {
    return {
      swiperLists: [],
      iconLists: [],
      recommendLists: [],
      weekendLists: []
    }
  },
  mounted () {
    this.getHomeInfo()
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json').then(this.getHomeInfoSuccess)
    },
    getHomeInfoSuccess (rst) {
      if (rst.data.ret && rst.data.data) {
        const data = rst.data.data
        this.swiperLists = data.swiperLists
        this.iconLists = data.iconLists
        this.recommendLists = data.recommendLists
        this.weekendLists = data.recommendLists
      }
    }
  }
}
</script>
