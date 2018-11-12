<template>
  <div class="icons">
    <swiper  ref="mySwiper">
        <swiper-slide v-for="(page,index) of pages" :key="index">
           <div v-for="item of page" :key="item.id" class="icon">
                <div class="icon-img">
                    <img class="icon-img-content" :src="item.imgUrl"/>
                </div>
                <p class="icon-desc">{{item.desc}}</p>
            </div> 
        </swiper-slide>     
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data (){
    return{
      iconList: [{
        id: '001',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        desc: '景点门票'
      },{
        id: '002',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/27/dac2bcf9added702.png',
        desc: '海滨海岛'
      },{
        id: '003',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
        desc: '江门必游'
      },{
        id: '004',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png',
        desc: '泡温泉'
      },{
        id: '005',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/96/c70f1e85ae4a4f02.png',
        desc: '自然风光'
      },{
        id: '006',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png',
        desc: '亲子游'
      },{
        id: '007',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
        desc: '名胜古迹'
      },{
        id: '008',
        imgUrl: 'https://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
        desc: '打卡胜地'
      },{
        id: '009',
        imgUrl: 'https://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
        desc: '打卡胜地'
      }
      ]
    }
  },
  computed:{
      pages () {
        //   组装出一个二维数组，来实现多页切换icons轮播效果
          const pages = []
          this.iconList.forEach((item,index)=>{
              const page = Math.floor(index/8)
              if(!pages[page]){
                  pages[page] = []
              }
              pages[page].push(item)
          })
          return pages
      }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .icons >>> .swiper-container
    overflow : hidden
    height : 0
    padding-bottom : 50%
  .icons
    height : 0
    padding-bottom : 50%
    overflow : hidden
    .icon
      position : relative
      overflow : hidden
      width : 25%
      height : 0
      float : left
      padding-bottom : 25%
      .icon-img
        position : absolute
        top : 0
        left : 0
        right : 0
        bottom : .44rem
        box-sizing : border-box
        padding : .1rem
        .icon-img-content
          display : block
          margin : 0 auto
          height : 100%
      .icon-desc
        position : absolute
        left : 0
        right : 0
        bottom : 0
        line-height : .44rem
        height : .44rem
        text-align : center
        white-space : nowrap 
        
        color : $darkTextColor

</style>
