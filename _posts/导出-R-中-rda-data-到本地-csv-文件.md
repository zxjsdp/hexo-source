title: 导出 R 中 .rda data 到本地 csv 文件
date: 2015-09-22 13:22:19
tags:
  - r
  - csv
  - export
  - rda
---

R包中经常会包含一些经典数据供学习使用，可以使用`data(...)`的方式直接加载这些数据。但是有时候需要查看这些数据的原始格式，作为使用自己数据时候的格式参考，但是`.rda`格式又不是纯文本格式，因此将`.rda`导出到纯文本格式是非常有用的小技巧。

可以使用如下命令导出`.rda`到`.csv`文件：

<pre>
data(data_name, package="package_name")

write.table(data_name, "C:/out.csv", sep=",", col.names=TRUE, row.names=FALSE, quote=FALSE, na="*")
</pre>
