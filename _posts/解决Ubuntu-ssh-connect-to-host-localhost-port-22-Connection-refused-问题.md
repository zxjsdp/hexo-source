title: '解决 Ubuntu "ssh: connect to host localhost port 22: Connection refused" 问题'
date: 2015-09-16 11:16:18
tags:
  - ubuntu
  - linux
  - ssh
  - error
categories: Linux
---

最近 ssh 连不上一台新安装的 Ubuntu，显示错误信息：`ssh: connect to host xxx.xxx.xxx.xxx port 22: Connection refused`。

于是在这台 Ubuntu 上尝试`ssh localhost`，也提供类似的错误信息：`ssh: connect to host localhost port 22: Connection refused`。

ssh 无法连接成功的原因可能跟防火墙等因素有关。不过因为这是新系统，因此并没有相关的配置。因此最可能的原因是 ssh 命令没有安装或 daemon 没有启动。使用如下命令即可解决：

    sudo apt-get install openssh-server

参考资料：

- [ssh: connect to host localhost port 22: Connection refused](https://askubuntu.com/questions/403936/ssh-connect-to-host-localhost-port-22-connection-refused)
- [ssh: connect to host localhost port 22: Connection refused ](https://www.linuxquestions.org/questions/linux-desktop-74/ssh-connect-to-host-localhost-port-22-connection-refused-935331/)
- [在ubuntu中配置SSH(解决connect to host localhost port 22: Connection refused问题) ](http://blog.csdn.net/feliciafay/article/details/6561414)
