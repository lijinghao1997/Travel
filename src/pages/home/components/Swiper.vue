<template>
<div class="wrapper">
    <swiper :options="swiperOption" ref="mySwiper" v-if="showSwiper">
    <!-- slides -->
      <swiper-slide v-for="(item) of list" :key="item.id" >
          <img class="swiper-image" :src="item.imgUrl">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
</div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
      list: Array,
  },
  computed:{
    showSwiper () {
      return this.list.length
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
          id: '0001',
          imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1809/31/da037478f37cf202.jpg_750x200_a02cf862.jpg'
        },{
          id: '0002',
          imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1809/c6/2467595fffc3b302.jpg_750x200_cca13d51.jpg'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff
  .wrapper
    overflow: hidden
    width:100%
    padding-buttom: 31.25%
    background: #eee
    .swiper-image
      width: 100%
</style>
