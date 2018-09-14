<template lang="html">
  <div class="footer">
    <mt-tabbar v-model="selected" fixed class="border-1px-top">
      <mt-tab-item id="Category" >
        <img :src="img1" slot="icon">目录
      </mt-tab-item>
      <mt-tab-item id="Content" to="/brandSale">
        <img :src="img2" slot="icon">正文
      </mt-tab-item>
      <mt-tab-item id="收藏" >
        <img :src="img3" slot="icon">收藏
      </mt-tab-item>
    </mt-tabbar>
  </div>
</template>

<script>
export default {
  data () {
    return {
      selected: "首页",
      img1: "static/icon/indexchoose.png",
      img2: "static/icon/brand.png",
      img3: "static/icon/live.png",
      img4: "static/icon/cart.png",
      img5: "static/icon/me.png"
    }
  },
  computed: {
    otherSelect () {
      return this.$store.state.selectTab
    }
  },
  watch: {
    // 监听 是否从其他的页面跳转过来的数据
    "otherSelect" () {
      this.selected = this.otherSelect
    },
    // this.$.router.push({name: ''})
    // 固定的书写 ""双引号里面是要监听的数据 handler是处理数据改变的函数 deep是否深度监听
    "selected": {
      handler (val,oldval) { //多看文档 handler
        if (this.selected == "Category") {
          this.$router.push('/')
          this.img1="static/icon/indexchoose.png"
        } else {
          this.img1="static/icon/index.png"
        }
        if (this.selected == "Content") {
          this.$router.push('/index/page2')
          this.img2="static/icon/brandchoose.png"
        } else {
          this.img2="static/icon/brand.png"
        }
        if (this.selected == "直播特区") {
          this.$router.push('/livecommunity')
          this.img3="static/icon/livechoose.png"
        } else {
          this.img3="static/icon/live.png"
        }
        if (this.selected == "购物车") {
          this.$router.push('/shopcart')
          this.img4="static/icon/cartchoose.png"
        } else {
          this.img4="static/icon/cart.png"
        }
        if (this.selected == "我的") {
          this.$router.push('/myself')
          this.img5="static/icon/mechoose.png"
        } else {
          this.img5="static/icon/me.png"
        }
      }
      // deep:true//对象内部的属性监听，也叫深度监听
    }
  },


}
</script>

<style lang="stylus" type="stylesheet/stylus" scoped>
@import '../common/stylus/mixin.styl'
.mint-tabbar
  background #fff
  border-1px-top()
  height 1.5625rem
  padding-top -.4rem
  .mint-tab-item.is-selected
    color #FE4070
    background #fff
    text-decoration none
</style>
