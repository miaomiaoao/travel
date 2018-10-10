<template>
  <div>
    <home-header></home-header>
    <Swiper></Swiper>
    <icons></icons>
    <recommend></recommend>
  </div>
</template>
<script>
import HomeHeader from './components/Header'
import Swiper from './components/Swiper'
import Icons from './components/Icons'
import Recommend from './components/Recommend'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    Swiper,
    Icons,
    Recommend
  }
}
</script>
