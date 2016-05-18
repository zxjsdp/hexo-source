title: '解决 Python 使用 multiprocessing 模块时 "ImportError: cannot import name Empty"错误'
date: 2015-09-11 09:46:29
tags:
  - python
  - multiprocessing
  - error
categories: Python
---

![python-queue-import-error](http://zxjsdp1.qiniudn.com/python-queue-import-error.png)

最近在使用 Python 编写一个用到 multiprocessing 的模块时，运行时出现了 `ImportError: cannot import name 'Empty'` 错误。后来想明白了原来是当前文件夹下我自己新增加了一个`queue.py`的模块，增加这个文件的时候忘记考虑名字的问题，造成了对标准库中相应`queue.py`的干扰。

    /usr/lib/python2.7/multiprocessing/queues.py

我的`queue.py`中并没有实现`Empty`等类，自然无法顺利导入。将我自己的`queue.py`改命后问题即可解决。

以后增加自己的文件时一定要对名字进行慎重考虑，不要干扰到标准库。这样的问题在Python3使用绝对导入的时候应该不会怎么出现了。

参考链接：
- <https://stackoverflow.com/questions/28594311/is-multiprocessing-in-python-3-4-broken>
