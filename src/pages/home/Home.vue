<template>
<div>
  <home-header></home-header>
  <home-swiper :list="swiperList"></home-swiper>
  <home-icons :list="iconList"></home-icons>
  <home-recommend :list="recommendList"></home-recommend>
  <home-hottest-spots :list="hottestSpotList"></home-hottest-spots>
</div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeHottestSpots from './components/HottestSpots'
import axios from 'axios'
import { mapState } from 'vuex'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeHottestSpots
  },
  data () {
    return {
      lastCity: '',
      swiperList: [],
      iconList: [],
      recommendList: [],
      hottestSpotList: []
    }
  },
  computed: {
    ...mapState(['city'])
  },
  methods: {
    GetHomeInfo: function () {
      axios.get('/api/index.json?city=' + this.city)
        .then(this.GetHomeInfoSucc)
    },
    GetHomeInfoSucc: function (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.recommendList = data.recommendList
        this.hottestSpotList = data.hottestSpotList
      }
    }
  },
  mounted: function () {
    this.lastCity = this.city
    this.GetHomeInfo()
  },
  activated () {
    if (this.lastCity !== this.city) {
      this.lastCity = this.city
      this.GetHomeInfo()
    }
  }
}
</script>
