title: 如何将任意文件固定在 Win10 的开始屏幕中
date: 2015-09-17 09:59:59
tags:
  - tips
  - windows
  - win10
  - pin
  - start page
categories: Tips
---

虽然`Wox`和`Launchy`是我日常启动程序的主力方式，不过开始屏幕的图标方便归类，这是快速启动工具所不能提供的，因此我也会将最常用的程序在开始屏幕上分类固定。

最近需要将一个常用的批处理文件(\*.bat)固定在开始菜单中。但是发现不论是`*.bat`文件本身还是这个批处理的快捷方式（\*.lnk），右键菜单中都没有**固定到“开始”屏幕**这个选项。那么如何实现将这个批处理固定到开始屏幕中呢？

其实开始菜单（`C:\Users\Username\AppData\Roaming\Microsoft\Windows\Start Menu`），开始屏幕中、最常用程序、最近使用的项目（`C:\Users\Username\AppData\Roaming\Microsoft\Windows\Recent`）、最近访问的位置（`C:\Users\Username\Links\RecentPlaces.lnk`）等等都是指向保存有许多快捷方式的文件夹的快捷方式。当新安装一个软件后，这个软件将快捷方式复制一份到开始菜单的文件夹中，与其他程序的快捷方式放置在一起，在开始菜单里就会显示出这个新安装的程序了。在开始菜单里显示的快捷方式上点击右键，菜单中是一定有**固定到“开始”屏幕**这个选项的。

因此可以进入到开始菜单目录（`C:\Users\Username\AppData\Roaming\Microsoft\Windows\Start Menu`），将批处理文件(\*.bat)或者其快捷方式（\*.lnk）放置于其中，然后到开始菜单中寻找这个程序，右键选择**固定到“开始”屏幕**。

![pin-lnk-to-start-page](http://zxjsdp1.qiniudn.com/pin-lnk-to-start-page.png)

另外，**最近使用的项目**与**最近访问的位置**是非常好用的功能，但是被大多数人忽略了（需要将`Username`替换成你的用户名）。

- 最近使用的项目（`C:\Users\Username\AppData\Roaming\Microsoft\Windows\Recent`）
- 最近访问的位置（`C:\Users\Username\Links\RecentPlaces.lnk`）

