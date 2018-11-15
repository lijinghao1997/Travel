<template>
    <div>
        <detail-bannner></detail-bannner>
        <detail-header></detail-header>
        <div class="content"></div>
    </div>
</template>

<script>
import DetailBannner from './components/Banner'
import DetailHeader from './components/Header'
export default {
  name: 'Detail',
  components: {
      DetailBannner,
      DetailHeader,
  }
}
</script>

<style lang='stylus' scoped>
    .content
      height : 50rem
</style>

