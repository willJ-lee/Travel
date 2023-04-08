<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <router-link tag="li" :to="'/detail/' + item.id" class="item border-bottom" v-for="item of list" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl">
        </div>
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
  @import "~styles/mixins.styl"
  .title
    margin-top: .2rem
    line-height: .8rem
    background: #eee
    text-indent: .2rem
  .item
    overflow: hidden
    height: 1.9rem
    display: flex
    .item-img
      width: 1.7rem
      height: 1.7rem
      padding: .1rem
    .item-info
      min-width: 0
      flex: 1
      padding: .1rem
      .item-title
        line-height: .54rem
        font-size: .32rem
        ellipsis()
      .item-desc
        height: .4rem
        line-height: .4rem
        color: #ccc
        ellipsis()
      .item-button
        margin-top: .2rem
        background: #ff9300
        padding: 0 .06rem
        color: #fff
</style>
