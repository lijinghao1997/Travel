<template>
    <div class="header">
        <div class="header-left">
            <span class="iconfont">&#xe624;</span>
        </div>
        <div class="header-input">
            <span class="icontfont">&#xe632;</span>
            输入城市景点游玩主题
        </div>
        <div class="header-right">
            城市
            <span class="iconfont">&#xe62d;</span>
        </div>
    </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>
// 使用scoped来限制样式只对当前组件有效
<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl';
  .header
    display: flex
    height: .86rem
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
      cololr: #ccc
    .header-right
      width: 1.24rem
      float: right
      text-align: center
      .arrow-icon
        margin-left: -.04rem
        font-size: .24rem
</style>
