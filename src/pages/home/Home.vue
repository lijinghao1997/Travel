<template>
    <div>
        <home-header :city="city"></home-header>
        <home-swiper :list="swiperList"></home-swiper>
        <home-icons :list="iconList"></home-icons>
        <home-recommand :list="recommendList"></home-recommand>
        <home-weekend :list="weekendList"></home-weekend>
    </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommand from './components/Recommand'
import HomeWeekend from './components/Weekend'
import axios from 'axios';
export default {
  name: 'Home',
  components: {
    //   ES6可以写成直接写HomeHeader
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommand,
    HomeWeekend
  },
  data (){
      return {
        city: '',
        swiperList: [],
        iconList: [],
        recommendList: [],
        weekendList: []
      }
  },
  mounted () {
    this.getHomeInfo()
  },
  methods:{
      getHomeInfo () {
        axios.get('/static/mock/index.json')
            .then(this.getHomeInfoSucc)
      },
      getHomeInfoSucc (res) {
        res = res.data
        if(res.ret && res.data){
            const data = res.data
            this.city = data.city
            this.swiperList=data.swiperList
            this.iconList=data.iconList
            this.recommendList=data.recommendList
            this.weekendList=data.weekendList
        }
        console.log(res)
      }
  }
}
</script>

<style>

</style>
