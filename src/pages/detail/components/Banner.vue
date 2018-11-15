<template>
    <div>
        <div class="banner" @click="handleBannerClick">
            <img class="banner-img" src="http://img1.qunarzz.com/sight/p0/1508/89/895a1b7add84f23faca053ce9e3153db.water.jpg_600x330_93d96bdf.jpg">
            <div class="banner-info">
                <div class="banner-title">北京欢乐谷(AAA景区)</div>
                <div class="banner-number"><span class="iconfont banner-icon">&#xe632;</span>39</div>
            </div>
        </div>
        <common-gallery v-show="showGallery" @close="handleClose"></common-gallery>
    </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
export default {
  name: 'DetailBanner',
  components: {
      CommonGallery,
  },
  data () {
      return{
          showGallery: false,
      }
  },
  methods: {
      handleBannerClick () {
          this.showGallery = true
      },
      handleClose (){
          this.showGallery = false
      }
  }
}
</script>

<style lang='stylus' scoped>
  .banner
    position : relative
    overflow : hidden
    height : 0
    padding-bottom : 55%
    .banner-img
      width : 100%
    .banner-info
      position : absolute
      left : 0 
      right : 0
      bottom : 0 
      line-height : .6rem
      display : flex
      color : #fff
      background-image : linear-gradient(top, rgba(0,0,0,0), rgba(0,0,0,0.8))
      .banner-title
        flex : 1
        font-size : .32rem
        padding: 0 .2rem
      .banner-number
       font-size : .24rem
       padding : 0 .4rem
       line-height : .4rem
       height : .32rem
       border-radius : .2rem
       background : rgba(0,0,0,.8)
       margin-top : .14rem
       .banner-icon 
         font-size : .24rem

</style>

