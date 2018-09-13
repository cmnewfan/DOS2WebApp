<template lang="html">
<div class="goods">
  <div class="content" ref="contentWrapper">
    <el-tree class="content-wrapper" :data="treeData" :props="defaultProps" node-key="id" :default-expanded-keys="[0]" @node-click="handleNodeClick"></el-tree>
  </div>
</div>
</template>

<script>
import BScroll from 'better-scroll'
// 需要引入
import Tree from '../../../static/contents/tree.json';
import ActivityList from '../../components/ActivityList.vue'
import GoodsList from '../../components/GoodsList.vue'
export default {
  data () {
    return {
      // 复选ids,可传入id数组作为初始选中状态,如[3,4,8]
      checkedIds: [],
      // tree数据
      treeData: Tree.data,
      // 设置项
      options: {},
      tabIndex: 0,
      hour: 9,
      min: 13,
      sec: 13,
      defaultProps: {
        children: 'children',
        label: 'label'
      }
    }
  },
  created () {
    this.$nextTick(() => {
      this._initScroll()
    })
    // created是数据初始化的过程 axios会自动解析json格式
    this.$store.dispatch('selectTab', '首页')
    axios.get("/api/data").then(res => {
      this.$store.dispatch('addActivity', res.data.activityLists)
      this.$store.dispatch('addGoods', res.data.goodsList)
      // 异步的 属于放在这里面 等待他们只想完
      // console.log(res.data.goodsList) //获取到里面的数据
    }).catch(err => {
      console.log(err)
    })
    this.interval = setInterval(() => {
      if(this.sec > 0) {
        this.sec--
      } else {
        this.sec = 60
        if(this.min > 0) {
            this.min--
        } else {
          this.min = 60
          this.hour--
        }
      }
      if(this.hour == 0 && this.min == 0 && this.sec == 0)
      clearInterval(this.interval)
    }, 1000)
  },
  components: {
    ActivityList,
    GoodsList
  },
  methods: {
    tabClick (index) {
      this.tabIndex = index
    },
    _initScroll () {
      this.typeScroll = new BScroll(this.$refs.contentWrapper, {
        click: true,
        probeType: 3
      })
    },
    handleNodeClick(data) {
      this.typeScroll.refersh()
    }
  }
}
</script>

<style lang="stylus" type="stylesheet/stylus"  scoped>
@import '../../common/stylus/mixin.styl'
.goods
  overflow hidden
  position absolute
  width 100%
  height 100%
  top 2.4rem
  display flex
  .content
    margin-top -0.1rem
  .content-wrapper
    flex 1
    .types
      // 合理利用弹性布局
      margin-left 0.4rem
      margin-top .4275rem
      height 2rem
      .type-item
        float left
        margin-right .5rem
        text-align center
        img
          height 1.42rem
          width 1.42rem
        .text
          margin-top 0.2rem
    .activity
      padding .6875rem .375rem .15625rem .446667rem
      font-size .346667rem
      color mainColor
      position relative
      border-line()
      .title
        font-size .446667rem
      .time
        font-size .346667rem
        color fontColor
        vertical-align top
        display inline-block
        padding 0rem .45875rem 0rem 1.125rem
      .detail
        border .01rem solid #E4E4E4
        width .88125rem
        height .5625rem
        padding 0rem .09rem
        border-radius 20%
      .more
        position relative
        color fontColor
        arrow-right(.2rem)
    .mixcart-list
      margin-top .5rem
      .tab-title
        padding 0px .8375rem .12rem
        font-size .46875rem
        .title-item
          color fontColor
          &:first-child
            margin-right 1.8375rem
          &.tab-click
            color mainColor
</style>
