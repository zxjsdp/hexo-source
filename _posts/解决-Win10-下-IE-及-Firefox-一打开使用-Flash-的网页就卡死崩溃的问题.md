title: 解决 Win10 下 IE 及 Firefox 一打开使用 Flash 的网页就卡死崩溃的问题
date: 2015-09-15 09:55:16
tags:
  - tips
  - win10
  - firefox
  - flash
categories: Tips
---

Flash 导致巨大的资源占用以及卡顿崩溃等等是一直以来都存在的问题。虽然 YouTube 等国外的主流网站很多都已经开始强制使用 HTML5 来播放视频，Firefox 和 Chrome 等浏览器也逐渐开始禁止播放 Flash 内容，但是在国内 Flash 还是占据主流位置的，毕竟国内的视频网站大多靠视频播放前的超长广告来赚钱，它们暂时没有意愿去做出有利于用户体验或者纯粹地追求技术进步的行动。

![adobe-flash-player](http://zxjsdp1.qiniudn.com/adobe-flash-player.jpg)

近期一位同学的电脑（联想 x420s，Intel i7 处理器，仅核心显卡）出现了很奇怪的问题，只要进入含有 Flash 元素的网页，不论是 IE 还是 Firefox（包括新建配置）都会马上卡死，Chrome则不会。尝试了各种方法无果，由于 IE 和 Firefox 均会出现问题，因此可以排除是 Firefox 自己的 Flash Player Plugin 问题。后来想到会不会是因为 Flash 硬件加速造成的。这台电脑近期升级了 Win10，有可能跟之前声卡驱动类似，是因为驱动不完全兼容 Win10。于是在设备管理器中核心显卡上右键`更新驱动程序软件`，然后选择`自动搜索更新的驱动程序软件`，系统就自己搜寻适合的显卡驱动并且安装了（为 Win10 的驱动搜索成功率点赞）。更新完成重启，IE 和 Firefox 打开 Flash 网页卡死的现象均消失了。

如果以后再遇到不正常的情况，根据之前声卡和这次显卡的教训，可能要着重考虑是不是旧驱动对 Win10 的兼容性造成的了。

----------

Flash 在某个版本后加入了沙箱，虽然是为了增加安全性，但是却非常明显地导致了性能下降和崩溃现象。可以通过某些方法关闭沙箱来改善：

1. 新建纯文本文件，命名为`mms.cfg`，向里面添加如下内容：

        RTMFPP2PDisable=1
        SilentAutoUpdateEnable=1
        AutoUpdateDisable=0
        ProtectedMode=0

1. 根据32位或者64位系统，进入相应的目录，将`mms.cfg`文件复制到这个目录（可能需要管理员权限）：

    - Windows 32位系统：C:\windows\system32\macromed\flash
    - Windows 64位系统：C:\windows\syswow64\macromed\flash

这样可以关闭沙箱，并且禁用 Flash 的自动上传。

针对 Firefox，还有另外一些设置以供参考：

1. 使用免沙箱版本的 Flash Player（文件名类似于`NPSWF32_19_0_0_162.dll`，可在[卡饭论坛 Firefox 专区](http://bbs.kafan.cn/forum.php?mod=forumdisplay&fid=215&page=1)寻找网友维护的提取免沙箱版 Flash 文件），放置于`C:\Program Files (x86)\Mozilla Firefox\plugins`目录下。
2. 进入`about:addons`，点击左侧的`插件`，在插件列表中寻找`Shockwave Flash xx.xx.xx...`，点击`选项`，取消选择`开启 Flash 保护模式`。
3. 进入`about:config`，在搜索栏里输入`protected`，寻找`dom.ipc.plugins.flash.disable-protected-mode`，双击将 value 改为`true`。
4. 进入`about:config`，寻找`plugin.allow.asyncdrawing`和`dom.ipc.plugins.asyncInit`，将值都改为`true`。

另外对于视频花屏卡顿等现象，也有人尝试关闭 Flash 的硬件加速即可缓解。具体方法是在任意 Flash 元素上右键，打开 Flash 选项，取消使用 Flash 硬件加速即可。当然取消硬件加速可能会造成 CPU 使用率增加。


参考资料：

- [视频卡顿，火狐卡蹦？flash官方提供了默认的关闭沙箱简单方法，且一劳永逸。。](bbs.kafan.cn/thread-1781001-1-1.html)
- [简单粗暴解决flash视频卡顿问题](http://bbs.kafan.cn/thread-1848863-1-1.html)
