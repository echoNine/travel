<template>
  <div>
    <div class="title">火爆景点</div>
    <ul>
      <li class="item border-bottom" v-for="item of list" :key="item.id">
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
  props: {
    list: Array
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
    padding-bottom 38.5%
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
