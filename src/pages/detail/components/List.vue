<template>
  <div>
    <div class="item" v-for="(item, index) of list" :key="index">
      <div class="item-title border-bottom">
        <span class="iconfont item-title-icon">&#xe71b;</span>
        {{item.title}}
      </div>
      <div class="item-children" v-if="item.children">
        <detail-list :list="item.children"></detail-list>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import "~sty/varibles.styl"
  .item-title
    line-height .8rem
    font-size .32rem
    padding 0 .2rem
    .item-title-icon
      position relative
      top .06rem
      left .06rem
      display inline-block
      width .36rem
      height .36rem
      color $bgColor
      margin-right .1rem
  .item-children
    padding 0 .4rem
</style>
