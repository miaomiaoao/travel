<template>
  <div>
    <home-header></home-header>
    <Swiper></Swiper>
    <router-link to="/city" >城市列表</router-link>
  </div>
</template>
<script>
import HomeHeader from './components/Header'
import Swiper from './components/Swiper'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    Swiper
  }
}
</script>
