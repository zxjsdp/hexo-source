title: 解决VIA声卡的电脑在Win10下外放及耳机无法自动切换及左右声道失衡的问题
date: 2015-09-06 15:44:30
tags:
  - tips
  - driver
  - via
categories: Tips
---

![VIA-audio-driver](http://zxjsdp1.qiniudn.com/VIA-audio-driver.png)

升级Win10后，我电脑的声音功能出现了各种问题。主要的两个问题是：

1. 笔记本自带的外放设备和耳机无法自动切换。默认设备是耳机，当插上耳机的时候，可以播放声音（当然还有左右耳机音量大小不同的问题）。但是当拔掉耳机，则不会自动将设备切换到笔记本外放，因此没有声音。需要手动更改设备到扬声器才外放才有声音，但是此时插上耳机就没有声音了。
2. 耳机左右声道不均衡。耳机的左右两侧声音大小不同，有时候左侧明显比右侧大，有时候右侧明显比左侧大。

刚刚出现问题的时候我怀疑是耳机或者电脑硬件出现了故障。但是经过测试，耳机没有问题，电脑偶尔也会正常，因此大致排除了硬件故障，开始怀疑是软件或者驱动的问题。经过搜索，发现升级 Win10 后别人的使用 VIA 声卡的电脑也出现了类似的问题，因此可以大致判定是驱动不兼容Win10。

有人通过禁用 VIA High Definition Audio 驱动，使用系统默认的 High Definition Audio 驱动来解决问题，有兴趣的话可以参考[解决WIN10系统 VIA HD驱动无法自动切换外置音响和耳机的问题](http://www.onlyke.com/html/387.html)。但是 VIA 的声卡驱动还是提供了一些音效增强的，因此最好的方法是通过更新声卡驱动至最新版来解决。

在VIA官网上找到驱动下载页面：<http://download.viatech.com>，分别选择`Microsoft Windows`，`Windows 10 32-bit/64-bit`，`Audio`，`VIA HD Audio codec ...`，然后进入到下载页面。目前最新的驱动是19-Aug-2015 发布的 `V11.10b`，文件名为`VIAHDAud_v11_1000b_08182015.zip`。下载后安装重启即可解决。 

参考链接：

1. [解决WIN10系统 VIA HD驱动无法自动切换外置音响和耳机的问题](http://www.onlyke.com/html/387.html)
2. [升级Win10系统后没有声音四种解决方案](http://www.kafan.cn/edu/86518814.html)