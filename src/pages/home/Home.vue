<template>
    <div>
        <home-header></home-header>
    </div>
</template>

<script>
import HomeHeader from './components/Header'
export default {
  name: 'Home',
  components: {
    //   ES6可以写成直接写HomeHeader
    HomeHeader: HomeHeader
  }
}
</script>

<style>

</style>
