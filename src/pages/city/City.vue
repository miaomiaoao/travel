<template>
    <div class="city">
        <Header></Header>
        <search></search>
        <list :cities= "cities" :hot-cities="hotCities" :current-letter="currentLetter"></list>
        <alphabet :cities="cities" @click="onClick"></alphabet>
    </div>
</template>
<script>
import Header from './components/Header'
import Search from './components/Search'
import List from './components/List'
import Alphabet from './components/Alphabet'
import axios from 'axios'
export default {
  components: {
    Header,
    Search,
    List,
    Alphabet
  },
  data () {
    return {
      hotCities: [],
      cities: [],
      currentLetter: ''
    }
  },
  mounted () {
    this.getCityInfo()
  },
  methods: {
    getCityInfo () {
      axios.get('/api/city.json').then(this.getCityInfoSuccess)
    },
    getCityInfoSuccess (rst) {
      if (rst.data.ret) {
        const data = rst.data.data
        this.hotCities = data.hotCities
        this.cities = data.cities
      }
    },
    onClick (letter) {
      this.currentLetter = letter
    }
  }
}
</script>
<style lang="stylus" scoped>

</style>
