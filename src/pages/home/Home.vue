<template>
  <div>
    <home-header></home-header>
    <Swiper></Swiper>
    <icons></icons>
    <router-link to="/city" >城市列表</router-link>
  </div>
</template>
<script>
import HomeHeader from './components/Header'
import Swiper from './components/Swiper'
import Icons from './components/Icons'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    Swiper,
    Icons
  }
}
</script>
