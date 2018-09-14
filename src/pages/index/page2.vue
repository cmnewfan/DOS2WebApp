<template lang="html">
  <div class="page">
    <div class="content" ref="popWrapper">
      
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  data () {
    return {
      url: ""
    }
  },
  methods: {
    _initScroll () {
      this.popScroll = new BScroll(this.$refs.popWrapper, {
        click: true,
        probeType: 3
      })
    }
  },
  created () {
    this.url = "../../../static/contents/content.html"
    this.$nextTick(() => {
      this._initScroll()
    })
  }
}
</script>
<style lang="stylus" scoped>
.page {
    overflow: hidden;
    height: 100%;
    position: absolute;
    left: 0;
    right: 0;
    .rvps1 {
        text-align: center;
    }

    .rvps2 {
        text-align: justify;
    }

    .rvts9 {
        font-size: 18pt;
        font-family: '宋体';
        font-weight: bold;
        color: #ff0000;
    }

    .rvts10 {
        font-size: 14pt;
        font-family: 'Times New Roman', 'Times', serif;
        color: #000000;
    }

    .rvts11 {
        font-size: 14pt;
        font-family: '楷体';
        font-weight: bold;
    }

    .rvts12 {
        font-size: 14pt;
        font-family: '楷体';
        font-weight: bold;
        color: #4169e1;
        text-decoration: underline;
    }

    .rvts13 {
        font-size: 14pt;
        font-family: 'Times New Roman', 'Times', serif;
        font-weight: bold;
        color: #444444;
    }
}
</style>
