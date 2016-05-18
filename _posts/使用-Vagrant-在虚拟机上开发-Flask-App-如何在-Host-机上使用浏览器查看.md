title: 使用 Vagrant 在虚拟机上开发 Flask App 如何在 Host 机上使用浏览器查看
date: 2015-09-13 09:23:25
tags:
  - vagrant
  - flask
  - app
  - web
categories: Tips
---

![vagrant-flask-app](http://zxjsdp1.qiniudn.com/vagrant-flask-app.png)

如果需要在 Vagrant 中开发 Flask App，同时使用 Host 机的浏览器进行查看，可以通过如下设置实现：

1. 在`Vagrantfile`中，添加端口转发：

        # Create a forwarded port mapping which allows access to a specific port
        # within the machine from a port on the host machine. In the example below,
        # accessing "localhost:8080" will access port 80 on the guest machine.
        # config.vm.network "forwarded_port", guest: 80, host: 8080

        config.vm.network "forwarded_port", guest: 5000, host: 5000

2. 在虚拟机中，创建 Flask App 的时候，修改调用`run()`的方法使服务器公开可用，让操作系统监听所有公网 IP。

        app.run(host='0.0.0.0')

做完这些，使用`vagrant reload 虚拟机id`来使`Vagrantfile`的更改生效。再运行 Flask App 的时候，就可以在 Host 机中使用**http:localhost:5000**来访问 Flask App 了。

参考资料：

- [Vagrant, Flask — App not running on 10.10.10.10, 127.0.0.1](https://stackoverflow.com/questions/29088056/vagrant-flask-app-not-running-on-10-10-10-10-127-0-0-1)
- [Having problems accessing port 5000 in Vagrant](https://stackoverflow.com/questions/23230599/having-problems-accessing-port-5000-in-vagrant)
- [快速入门¶](http://docs.jinkan.org/docs/flask/quickstart.html#quickstart)
