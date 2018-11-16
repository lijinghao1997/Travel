<template>
    <div>
        <router-link class="header-abs" tag="div" to="/" >
            <span class="iconfont header-abs-icon" v-show="showAbs">&#xe624;</span>
        </router-link>
        <div class="header-fixed" v-show="!showAbs" :style="opcityStyle">
            <router-link to="/">
                <div class="header-fixed-back">
                    <span class="iconfont">&#xe624;</span>
                </div>
            </router-link>
            景点详情
        </div>
    </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
      return{
          showAbs: true,
          opcityStyle:{
              opacity: 0
          }
      }
  },
  methods:{
      handleScroll () {
          const top = document.documentElement.scrollTop
          if(top > 60){
              let opacity = top/140
              opacity = opacity > 1 ? 1 : opacity
              this.opcityStyle.opacity = opacity
              this.showAbs = false
          }else {
              this.showAbs = true
          }
          console.log(document.documentElement.scrollTop)
      }
  },
  activated () {
      //这个事件绑定在window这个全局对象上，那么在每个页面都会执行这个方法
      //如果不进行揭榜，就会造成较多的bug
      window.addEventListener('scroll',this.handleScroll)
  },
  deactivated () {
      //对全局事件进行解绑,在页面隐藏就不会发生
      window.removeEventListener('scroll',this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';
  .header-abs
    position : absolute
    left : .2rem
    top : .2rem
    width : .8rem
    height : .8rem
    border-radius : .4rem
    text-align : center
    line-height : .8rem
    background : rgba(0, 0, 0, .8)
    .header-abs-icon
     color : #fff
     font-size : .4rem
  .header-fixed
    position : fixed
    top : 0
    left : 0
    right : 0
    height : $headerHeight
    line-height : $headerHeight
    text-align : center
    color : #fff
    background : $bgColor
    .header-fixed-back
      position : absolute
      top : 0
      left : 0
      width : .64rem
      text-align : center
      font-size : .4rem
      color : #fff
</style>


