<template>
  <div>
    <div class="title">火爆景点</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" />
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeHottestSpots',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: '//img1.qunarzz.com/sight/p0/1909/11/11482fe19c41b2efa3.water.jpg_256x160_2a317c55.jpg',
        title: '南浔古镇',
        desc: '水乡古镇九十九，不如南浔走一走'
      }, {
        id: '0002',
        imgUrl: '//img1.qunarzz.com/sight/p0/201405/27/8211cadd5d9fefeaa044c5b7eefc695d.jpg_256x160_5d730aee.jpg',
        title: '千岛湖',
        desc: '亲近大自然，放飞心情'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import "~sty/mixins.styl"
  .title
    line-height .8rem
    background #eee
    margin-top .2rem
    text-indent .2rem
    font-size .3rem
  .item-img-wrapper
    height 0
    overflow hidden
    padding-bottom 62.5%
    .item-img
      width 100%
  .item-info
    padding .1rem
    .item-title
      line-height .54rem
      font-size .32rem
      color black
      ellipsis()
      padding-left .15rem
    .item-desc
      line-height .4rem
      color gray
      ellipsis()
      padding-left .15rem
</style>
