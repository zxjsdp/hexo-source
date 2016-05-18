title: Python 在指定范围内获得不重复的随机数列表
date: 2015-09-21 00:25:16
tags:
  - python
  - random
  - tips
categories: Python
---

以前获得随机数列表都是使用

<pre>
import random

def get_random():
    int(round(random.random() * 100))  # 获取 100 以内的四舍五入整数随机数

def get_random_list(num):
    return [get_random() for _ in range(num)]  # 获取 num 个 100 以内的四舍五入整数随机数
</pre>

后来发现一个更好的方法：

<pre>
import random

random_list = random.sample(range(100), 10)  # 获取 10 个 100 以内的随机数。可以使用 int(round(num))获得四舍五入的整数
</pre>

参考资料：

- [how do i create a LIST of unique random numbers?](https://stackoverflow.com/questions/9755538/how-do-i-create-a-list-of-unique-random-numbers)
