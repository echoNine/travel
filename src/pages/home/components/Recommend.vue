<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <router-link tag="li" :to="'/detail/' + item.id" class="item border-bottom" v-for="item of list" :key="item.id">
        <img class="item-img" :src="item.imgUrl" />
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
          </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
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
  .item
    display flex
    height 1.9rem
    overflow hidden
    .item-img
      width 2.8rem
      height 1.7rem
      padding .1rem
    .item-info
      flex 1
      padding .1rem
      min-width 0
      .item-title
        line-height .54rem
        font-size .32rem
        color black
        ellipsis()
      .item-desc
        line-height .4rem
        color gray
        ellipsis()
      .item-button
        line-height .44rem
        background #ff9300
        padding 0 .2rem
        border-radius .06rem
        margin-top .16rem
        color #fff
</style>
