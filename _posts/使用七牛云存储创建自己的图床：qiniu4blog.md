title: 使用七牛云存储作为Blog的高速图床：qiniu4blog
date: 2016-06-01 23:00:50
tags:
  - tips
  - image
  - qiniu
  - qiniu4blog
  - blog
categories: Tips
---

## qiniu4blog 介绍

qiniu4blog 是一个使用 Python 实现的 library，方便快速上传本地图片到七牛云并生成外链地址。项目 GitHub 地址为： <https://github.com/wzyuliyang/qiniu4blog>，主页地址：<http://wzyuliyang.github.io/qiniu4blog/>。

![qiniu4blog](http://zxjsdp1.qiniudn.com/qiniu4blog_screenshot.png)

## 使用步骤

1. 安装 qiniu4blog:

        pip install qiniu4blog
        # Or
        pip install --user qiniu4blog

2. 新建同步需要上传到七牛上的图片的文件夹（若不需要监听目录则可跳过这一步）：

        mkdir /Users/username/Pictures/QiNiuPictures

3. 在 Home 目录下新建配置文件 qiniu.cfg（例如 `/Users/username` 或  `C:\Users\username\qiniu.cfg`）

        [config]
        bucket = qiniu_bucket_name
        accessKey = XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX-XXXX
        secretKey = XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
        path_to_watch = /Users/username/Pictures/QiNiuPictures

        [custom_url]
        enable = false
        addr = someuser.qiniudn.com

4. 在 terminal 中尝试使用 `qiniu4blog`。若找不到可执行文件，可能需要将可执行文件所在的目录加到 `PATH` 中。

    `qiniu4blog` 的可执行文件在 Mac OSX 下为：

        /Users/username/Library/Python/2.7/bin

    主要有如下两种使用方式，执行完成后图片外链地址将显示在 terminal 并已复制到剪切板：

    - 方式一，直接指定对应的图片路径：
    
            $ qiniu4blog /path/to/image.png

    - 方式二，监听步骤二中设置的监听目录，即步骤三中 `path_to_watch` 的路径：

            $ qiniu4blog  # 然后将需要上传的图片拷贝至七牛图片文件夹即可：/Users/username/Pictures/QiNiuPictures

