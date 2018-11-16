<template>
    <div>
        <detail-bannner :bannerImg="bannerImg"></detail-bannner>
        <detail-header></detail-header>
        <div class="content">
            <detail-list :list="categoryList" :galleryImgs="galleryImgs"></detail-list>
        </div>
    </div>
</template>

<script>
import DetailBannner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
      DetailBannner,
      DetailHeader,
      DetailList,
  },
  mounted () {
    this.getDetailInfo()
  },
  methods:{
    getDetailInfo () {
        axios.get('/static/mock/detail.json')
             .then(this.getDetailInfoSucc)
    },
    getDetailInfoSucc (res) {
        res = res.data
        if(res.ret && res.data){
            const data = res.data
            this.categoryList = data.categoryList
            this.sightName = data.sightName
            this.bannerImg = data.bannerImg
            this.galleryImgs = data.galleryImgs
        } 
    }
  },
  data () {
      return {
          categoryList: [],
          sightName: '',
          bannerImg: '',
          galleryImgs: []
      }
  }
}
</script>

<style lang='stylus' scoped>
    .content
      height : 50rem
</style>

