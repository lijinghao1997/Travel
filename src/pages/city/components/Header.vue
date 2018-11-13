<template>
    <div>
        <div class="header">
            城市选择
            <router-link to="/">
                <div class="header-back">
                    <span class="iconfont">&#xe624;</span>
                </div>
            </router-link> 
        </div>
    </div>   
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl';
  .header
    position : relative
    height : $headerHeight
    line-height : $headerHeight
    overflow : hidden
    text-align : center
    color : #fff
    background : $bgColor
    .header-back
      position : absolute
      top : 0
      left : 0
      width : .64rem
      text-align : center
      font-size : .4rem
      color : #fff
</style>

