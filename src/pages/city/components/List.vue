<template>
    <div class="list" ref="wrapper">
        <div class="wrapper">
              <div class="area">
            <div class="title border-topbottom">当前城市</div>
            <div class="button-list">
                <div class="button-wrapper">
                    <div class="button">{{this.$store.state.city}}</div>
                </div>
            </div>
        </div>
         <div class="area">
            <div class="title  border-bottomtop">热门城市</div>
            <div class="button-list">
                <div class="button-wrapper" v-for="item in hotCities" :key="item.id" @click="handleChangeCity(item.name)">
                    <div class="button">{{item.name}}</div>
                </div>
            </div>
        </div>
        <div class="area  border-topbottom" v-for="(city, letter) in cities" :key="letter" :ref="letter">
        <div class="title">{{letter}}</div>
        <div class="item-list border-bottom" v-for="(item, index) in city" :key="index" @click="handleChangeCity(item.name)">
            <div class="item">{{item.name}}</div>
        </div>
        </div>
        </div>
    </div>
</template>
<script>
import BScroll from 'better-scroll'
import { mapMutations } from 'vuex'
export default {
  props: {
    cities: {
      type: [Array, Object]
    },
    hotCities: {
      type: Array
    },
    currentLetter: {
      type: String
    }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  },
  watch: {
    currentLetter () {
      if (this.currentLetter) {
        this.scroll.scrollToElement(this.$refs[this.currentLetter][0])
      }
    }
  },
  methods: {
    handleChangeCity (city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  }
}
</script>
<style lang="stylus" scoped>
  .list
    overflow: hidden
    position: absolute
    right: 0
    bottom: 0
    top: 1.78rem
    left: 0
    .area
    .border-topbottom
        &:before
          border-color: #cccccc
        &:after
          border-color: #ccc
    .border-bottom
        &:before
          border-color: #ccc
    .title
        background: #eeeeee
        height: .54rem
        line-height: .54rem
        padding-left: 0.2rem
    .button-list
        padding: .1rem .6rem .1rem .1rem
        overflow: hidden;
        .button-wrapper
          width: 33.3333%
          float: left
        .button
          margin: .1rem
          padding: .1rem 0
          text-align: center
          border: .02rem solid #ccc
          border-radius: .06rem
    .item-list
        .item
          height: .76rem
          line-height: .76rem
          padding-left: .2rem
</style>
