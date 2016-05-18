title: Vagrant 通过修改 Vagrantfile 增加 Host 和 VirtualMachine 同步目录
date: 2015-09-12 21:40:09
tags:
  - vagrant
  - share
  - vagrantfile
categories: Tips
---

默认情况下，Vagrantfile 所在的目录与虚拟机中`/vagrant/`是同步的，对于大部分情况下的文件交换以及修改已经足够方便。

但是，某些情况下，需要增加另外的目录。例如如果在`/vagrant/`下使用`virtualenv venv`来新建 virtualenv，经常会因为权限问题导致无法顺利进行。比较常见的错误信息是`OSError: [Errno 71] Protocol error`。

![vagrant-virtualenv-error](http://zxjsdp1.qiniudn.com/vagrant-virtualenv-error.png)

因此可以在`/home/vagrant/`目录下来使用`virtualenv`。同时修改**Vagrantfile**，如果想要同步一下两个目录：

1. Host 机中的`learning`目录（即 **Vagrantfile**所在同一目录下新建`learning`目录）
2. 虚拟机中的`/home/vagrant/learning`

应该修改`Vagrantfile`中如下选项。

    # Share an additional folder to the guest VM. The first argument is
    # the path on the host to the actual folder. The second argument is
    # the path on the guest to mount the folder. And the optional third
    # argument is a set of non-required options.

    config.vm.synced_folder "learning/", "/home/vagrant/learning"

修改完成后使用`vagrant reload 虚拟机id`使更改生效。

参考资料：

- [Vagrant Configuration](https://docs.vagrantup.com/v2/synced-folders/basic_usage.html)
