<template>
  <div>
    <div class="banner" @click="handdleBannerClick">
      <img class="banner-img" :src="bannerImg"/>
      <div class="banner-info">
        <div class="banner-tittle">两江夜游·朝天系列游船</div>
        <div class="banner-number">
          <span class="iconfont arrow-icon banner-icon">&#xe609;</span>
          {{this.bannerImgs.length}}
          </div>
      </div>
    </div>
    <common-gallary :imgs="bannerImgs" v-show="showGallary" @close="closeBox"></common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  props: {
    sightName: String,
    bannerImg: String,
    bannerImgs: Array
  },

  data () {
    return {
      showGallary: false
    }
  },
  methods: {
    handdleBannerClick () {
      this.showGallary = true
    },
    closeBox () {
      this.showGallary = false
    }
  },
  components: {
    CommonGallary
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    overflow hidden
    height 0
    padding-bottom: 55%
    position relative
    .banner-img
      width 100%
    .banner-info
     display flex
     position absolute
     left 0
     right 0
     bottom 0
     line-height .6rem
     color #fff
     background-image linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,.8))
     .banner-tittle
      flex 1
      font-size .32rem
      padding 0 .2rem
     .banner-number
      height .32rem
      line-height .32rem
      padding 0 .4rem
      border-radius .2rem
      background rgba(0,0,0,.8)
      font-size .24rem
      margin-top .14rem
      .banner-icon
        font-size .24rem

</style>
