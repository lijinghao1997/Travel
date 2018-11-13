<template>
    <div class="header">
        <div class="header-left back-icon">
            <span class="iconfont">&#xe624;</span>
        </div>
        <div class="header-input">
            <span class="iconfont">&#xe632;</span>
            输入城市景点游玩主题
        </div>
        <router-link to="/city">
          <div class="header-right">
            {{this.city}}
            <span class="iconfont arrow-icon">&#xe62d;</span>
          </div>
        </router-link>
        
    </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>
// 使用scoped来限制样式只对当前组件有效
<style lang="stylus" scoped>
  @import '~styles/varibles.styl';
  .header
    display: flex
    height: .86rem
    background : $bgColor
    color: #fff
    .header-left
        position : relative
        width: .64rem
        float: left
        .back-icon
          position : absolute
          top : 0
          left : 0
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
      color: #fff
      .arrow-icon
        margin-left: -.04rem
        font-size: .24rem
</style>
