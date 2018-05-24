<template>
  <swiper :options="swiperOption">
    <swiper-slide v-for="(page, index) of pages" :key="index">
      <div class="icons">
      <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl"/>
          </div>
          <p class="icon-desc">{{ item.desc }}</p>
      </div>
      </div>
    </swiper-slide>
  </swiper>
</template>
<script>
export default {
  name: 'HomeIcon',
  props: {
    iconLists: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconLists.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>
<style lang="scss" scoped>
@import '~styles/variable.scss';
.icons {
    height: 0;
    overflow: hidden;
    padding-bottom: 50%;
    .icon {
        width: 25%;
        float: left;
        padding-bottom: 25%;
        overflow: hidden;
        position: relative;
        height: 0;
        .icon-img {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0.44rem;
            // box-sizing: border-box;
            // padding: .1rem;
            .icon-img-content {
                height: 100%;
                display: block;
                margin: 0 auto;
            }
        }

        .icon-desc {
            position: absolute;
            left: 0;
            right: 0;
            bottom: 0;
            line-height: 0.44rem;
            height: 0.44rem;
            color: $bgTextColor;
            text-align: center;
            @extend .txt-wrap
        }
    }
}
</style>
