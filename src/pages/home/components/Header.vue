<template>
    <div class="header">
        <div class="header-left ">
            <span class="iconfont back-icon">&#xe624;</span>
        </div>
        <div class="header-input">
            <span class="iconfont">&#xe632;</span>
            输入城市景点游玩主题
        </div>
        <router-link to="/city">
          <div class="header-right">
            {{this.$store.state.city}}
            <span class="iconfont arrow-icon">&#xe62d;</span>
          </div>
        </router-link>
        
    </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  
}
</script>
// 使用scoped来限制样式只对当前组件有效
<style lang="stylus" scoped>
  @import '~styles/varibles.styl';
  .header
    display: flex
    height: $headerHeight
    background : $bgColor
    color: #fff
    .header-left
      width: .64rem
      float: left
      .back-icon
        text-align: center
        font-size: .4rem
    .header-input
      flex: 1
      line-height: .64rem
      height: .64rem
      background: #fff
      border-radius: .1rem
      margin-top: .12rem
      margin-left: .2rem
      padding-left: .2rem
      color: #ccc
    .header-right
      min-width: 1.04rem
      float: right
      text-align: center
      padding : 0.1rem
      color: #fff
      .arrow-icon
        margin-left: -.04rem
        font-size: .24rem
</style>
