title: 使用 Python 获取两个列表的交集、并集、差集的常用方法
date: 2015-09-19 23:51:53
tags:
  - python
  - intersection
  - union
  - difference
categories: Python
---

在数据处理中经常需要使用 Python 来获取两个列表的交集，并集和差集。在 Python 中实现的方法有很多，我平时只使用一两种我所熟悉的，但效率不一定最高，也不一定最优美，所以这次想把常用的方法都搜集总结一下。

![intersection-union-difference](http://zxjsdp1.qiniudn.com/intersection-union-difference.png)

交集（Intersection）
------------------

<pre>
>>> a = [1, 2, 3, 4, 5, 6]
>>> b = [2, 4, 6, 8 ,10]
>>> a and b
[2, 4, 6]
</pre>

方法一：

<pre>intersection = list(set(a).intersection(b))</pre>

方法二：

<pre>intersection = list(set(a) & set(b))</pre>

方法三：

<pre>intersection = [x for x in b if x in set(a)]   # list a is the larger list b</pre>

方法四：

<pre>intersection = list((set(a).union(set(b)))^(set(a)^set(b)))</pre>

**注意：如果不考虑顺序并且一定要使用 loop 的话，不要直接使用 List，而应该使用 Set。在 List 中查找元素相对 Set 慢了非常非常多。**

参考资料：

- [Python - Intersection of two lists](https://stackoverflow.com/questions/642763/python-intersection-of-two-lists)
- [How to find list intersection?](https://stackoverflow.com/questions/3697432/how-to-find-list-intersection)
- [List intersection in python: let’s do it quickly](http://blog.michelemattioni.me/2015/01/10/list-intersection-in-python-lets-do-it-quickly/)
- [python 求两个list的差集，并集和交集](http://segmentfault.com/a/1190000000761405)

并集（Union）
-----------

<pre>
>>> a = [1, 2, 3, 4, 5, 6]
>>> b = [2, 4, 6, 8 ,10]
>>> a or b
[1, 2, 3, 4, 5, 6, 8, 10]
</pre>

方法一：
<pre>union = list(set(a) | set(b))</pre>

方法二：
<pre>list(set(a).union(set(b)))</pre>

**注意：如果不考虑顺序并且一定要使用 loop 的话，不要直接使用 List，而应该使用 Set。在 List 中查找元素相对 Set 慢了非常非常多。**

参考资料：

- [Python set Union and set Intersection operate differently?](https://stackoverflow.com/questions/19580944/python-set-union-and-set-intersection-operate-differently)
- [How to find the intersection and union of two lists in Python](http://www.saltycrane.com/blog/2008/01/how-to-find-intersection-and-union-of/)
- [python 求两个list的差集，并集和交集](http://segmentfault.com/a/1190000000761405)


差集（Difference Set）
--------------------

<pre>
>>> a = [1, 2, 3, 4, 5, 6]
>>> b = [2, 4, 6, 8 ,10]
>>> a or b
[1, 2, 3, 4, 5, 6, 8, 10]
</pre>

方法一：
<pre>
difference = list(set(b).difference(set(a)))    # elements in b but not in a
difference = list(set(a).difference(set(b)))    # elements in a but not in b
</pre>

方法二：
<pre>difference = list(set(a_list)^set(b_list))</pre>

方法三：
<pre>
difference = list(set(a)-set(b))    # elements in b but not in a
difference = list(set(a)-set(b))    # elements in a but not in b
</pre>

方法四：
<pre>
difference = [x for x in b if x not in set(a)]    # elements in b but not in a
difference = [x for x in b if x not in set(a)]    # elements in a but not in b
</pre>

**注意：如果不考虑顺序并且一定要使用 loop 的话，不要直接使用 List，而应该使用 Set。在 List 中查找元素相对 Set 慢了非常非常多。**

参考资料：

- [Get difference between two lists](https://stackoverflow.com/questions/3462143/get-difference-between-two-lists)
- [Retaining order while using Python's set difference](https://stackoverflow.com/questions/10005367/retaining-order-while-using-pythons-set-difference)
- [How to find the intersection and union of two lists in Python](http://www.saltycrane.com/blog/2008/01/how-to-find-intersection-and-union-of/)
- [python 求两个list的差集，并集和交集](http://segmentfault.com/a/1190000000761405)

