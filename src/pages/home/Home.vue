<template>
    <div>
        <home-header></home-header>
        <home-swiper></home-swiper>
    </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
export default {
  name: 'Home',
  components: {
    //   ES6可以写成直接写HomeHeader
    HomeHeader,
    HomeSwiper
  }
}
</script>

<style>

</style>
