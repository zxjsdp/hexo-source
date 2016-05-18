title: 更改 Adobe Acrobat DC 的默认光标为手型工具而不是选择工具
date: 2015-09-18 23:21:36
tags:
  - tips
  - acrobat
  - cursor
categories: Tips
---

当使用 Acrobat 打开 PDF 文档的时候，默认的光标为选择工具。但是大多数情况下，可能我使用 Acrobat 的大部分情况下仅仅是为了阅读，使用手型工具进行页面的拖拽非常方便，因此每次打开 PDF 后都需要手动点击一次手型工具非常麻烦。如何将打开 PDF 后 Acrobat 的默认光标设置为手型工具呢？

![acrobat-hand-tool-0](http://zxjsdp1.qiniudn.com/acrobat-hand-tool-0.png)

我曾经仅仅这样设置，但是发现没有效果：

    菜单栏
      | 
     编辑
      |
    首选项
      | -- 一般
            |-- 在“使用手形工具阅读文章”处打勾

![acrobat-hand-tool-1](http://zxjsdp1.qiniudn.com/acrobat-hand-tool-1.png)

后来发现原来还要进行另外一项设置：

    菜单栏
      | 
     编辑
      |
    首选项
      | -- 辅助工具
            |-- 将“总是显示键盘选择光标”选项取消打勾（位于其它辅助工具处）

![acrobat-hand-tool-2](http://zxjsdp1.qiniudn.com/acrobat-hand-tool-2.png)

这样默认的光标就是手型工具啦。
