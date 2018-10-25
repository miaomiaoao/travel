<template>
   <div>
     <ul class="alphabet">
         <li
            v-for="(alphabet, index) in alphabetList"
            :key="index"
            @click="handleLetterClick"
            @touchstart.prevent="handleTouchStart"
            @touchmove="handleTouchMove"
            @touchend="handleTouchEnd"
            :ref="alphabet">
             {{alphabet}}
         </li>
     </ul>
   </div>
</template>
<script>
export default {
  props: {
    cities: {
      type: [Object, Array]
    }
  },
  data () {
    return {
      touchStatus: false,
      startY: 0
    }
  },
  updated () {
    this.startY = this.$refs.A[0].offsetTop
  },
  computed: {
    alphabetList () {
      const alphabetList = []
      for (let i in this.cities) {
        alphabetList.push(i)
      }
      return alphabetList
    }
  },
  methods: {
    handleLetterClick (e) {
      const letter = e.currentTarget.innerText
      this.$emit('click', letter)
    },
    handleTouchStart () {
      this.touchStatus = true
    },
    handleTouchMove (e) {
      if (this.touchStatus) {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY - 79
          const index = Math.floor((touchY - this.startY) / 20)
          const letter = this.alphabetList[index]
          if (index >= 0 && index <= this.alphabetList.length) {
            this.$emit('click', letter)
          }
        }, 16)
      }
    },
    handleTouchEnd () {
      this.handleTouchEnd = false
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/variable.styl'
.alphabet
    position: absolute
    right: .1rem
    top: 1.58rem
    bottom: 0
    width: .4rem
    color: $bgColor
    display: flex
    justify-content: center
    flex-direction: column
    text-align: center
    li
      height: .4rem
      line-height: .4rem
</style>
