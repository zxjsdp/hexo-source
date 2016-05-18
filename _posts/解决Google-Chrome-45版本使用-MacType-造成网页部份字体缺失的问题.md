title: 解决Google Chrome 45版本使用 MacType 造成网页部份字体缺失的问题
date: 2015-09-09 16:28:11
tags:
  - chrome
  - mactype
  - font
  - tips
categories: Chrome
---

在Windows平台上，如果屏幕分辨率较低，则字体发虚。这时可以通过使用MacType可以得到非常不错的字体渲染效果。

当 Google Chrome 开启 DirectWrite 后，使用 MacType 对 Chrome 的字体进行渲染就经常出现各种问题。比较严重的问题之一是造成网页字体中某些字符的缺失。例如`Chrome`这个词可能就会显示成`C rome`。但是字符是存在的，当复制单词到其他地方，可以看到原来缺失的字符正常显示。

临时的解决办法之一是通过调整网页字体缩放比例，使得字体暂时可以显示。但是不同的缩放比例会有不同的字符无法正常显示。

在Chrome45版本之前， 可以通过在`chrome://flags`里面修改相关参数解决这个问题：

    chrome://flags/  #disable-direct-write
    chrome://flags/  #enable-one-copy

同时停用硬件加速，并为 Chrome 的快捷方式目标添加启动参数 `--disable-directwrite-for-ui`。

从45版本开始，这样的设置下同样会产生缺字的现象。

在卡饭论坛Chrome专区，有人提出一种解决方案。我修改后目前为止没有再出现缺字的现象([45.0.2454.85m (64-bit) 使用 mactype 浏览网页部分文字缺失](http://bbs.kafan.cn/thread-1851291-1-1.html))：

具体步骤：

1. 进入`chrome://flags`；
2. 调整`#num-raster-threads` 为`1`。

参考链接：

- [45.0.2454.85m (64-bit) 使用 mactype 浏览网页部分文字缺失](http://bbs.kafan.cn/thread-1851291-1-1.html)
- [你们的 Chrome 有没有丢失文字的情况](https://www.v2ex.com/t/184034)
- [chrome+mactype 的诡异渲染错误](https://www.v2ex.com/t/180832)
