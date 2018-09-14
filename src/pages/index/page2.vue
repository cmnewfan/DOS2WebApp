<template lang="html">
  <div class="page">
    <div class="content" ref="popWrapper">
      <p class=rvps1><a name="process1"></a>
        <p><span class=rvts9>前言：</span></p>
        <p class=rvps2><img width=450 height=626 alt="" hspace=1 vspace=1 src="../../assets/pic1/abcamber3.jpg"><span class=rvts10></span>
            <br><span class=rvts11>前言：</span>
            <br><span class=rvts11>本《神界：原罪2》游侠攻略精华宝典电子书，源自游侠《神界：原罪2》论坛版区的以下两贴：</span>
            <br><span class=rvts11>帖子标题：《神界：原罪2|Divinity: Original Sin
                2》图文攻略：操作/界面+系统教程+全种族/职业/属性/BUFF+全学派技能+全主支线任务/全同伴/全结局 [完]【游侠攻略组】</span>
            <br><span class=rvts11>链接：</span><a class=rvts12 href="http://game.ali213.net/thread-6308935-1-1.html"
                title="Click here!">http://game.ali213.net/thread-6308935-1-1.html</a>
            <br><span class=rvts11>帖子标题：《神界：原罪2|Divinity: Original Sin 2》物品合成公式大全·中英文[完]【游侠攻略组】</span>
            <br><span class=rvts11>链接：</span><a class=rvts12 href="http://game.ali213.net/thread-6309044-1-1.html"
                title="Click here!">http://game.ali213.net/thread-6309044-1-1.html</a>
            <br><span class=rvts13></span>
            <br><span class=rvts11>攻略作者及电子书制作者：</span><a class=rvts14 href="http://game.ali213.net/space-uid-15731464.html"
                title="Click here!">catby1986</a><span class=rvts11>（游侠攻略组组员）</span>
            <br><span class=rvts11>负责人：</span><a class=rvts14 href="http://game.ali213.net/space-uid-15339618.html"
                title="Click here!">苍穹Alex</a><span class=rvts11>（游侠攻略组组长）</span><span class=rvts15></span><a class=rvts14
                    href="http://game.ali213.net/space-uid-813126.html" title="Click here!">zero</a><span class=rvts11>（游侠攻略组辅助负责人）</span>
                <br><span class=rvts16></span>
                <br><span class=rvts11>感谢你的阅读浏览！也欢迎跟帖写出你对攻略的错误更正、内容补充、建议想法，等。</span></p>
        <p><br></p>
        <p><br></p>
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
