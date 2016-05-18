title: 'Vim 中 "undo (撤销)"" & "redo (重做)"" 的几种实现方式'
date: 2015-09-13 21:22:43
tags:
  - vim
  - undo
  - redo
  - tips
  - shortcuts
categories: Tips
---

![vim-undo-and-redo](http://zxjsdp1.qiniudn.com/vim-undo-and-redo.png)

Undo (撤销)
----------

在 Vim 中，`undo`(撤销)是最常用的操作之一，可以通过按`u`实现。如果需要进行多次`undo`（例如需要退回到3次修改以前），可以按`3 u`。

也可以键入`:u`或者`:undo`来进行撤销。这样做的缺点是键入一次只能撤销一次，且不如`u`方便快捷。

另外`U`经常被不经意间按到，导致在想要撤销一次更改（`u`）的时候却发现整行的更改都被撤销了。日常使用中`U`真正的使用场景相对`u`来说少很多。

Redo (重做)
----------

当撤销了一次或者几次操作后，发现撤销得多了，就需要`redo`来恢复。

可以通过按`CTRL-R`来进行重做操作。

当然也可以通过键入`:red`或者`:redo`来进行重做。

其他
---

当然还有强大的`:earlier/:later`命令，可以参考[StackOverFlow的一个回答](https://stackoverflow.com/questions/1555779/how-do-i-do-redo-i-e-undo-undo-in-vim)。

> To redo everything you just need to do `later 9999999d`
>
> (assuming that you first edited the file at most 9999999 days ago), or, 
> if you remember the difference between current undo state and needed one,
> Use Nh, Nm or Ns for hours, minutes and seconds respectively. + :later N<CR> <=> Ng+ and :later Nf for file writes.

-------
参考资料：

- [Vim documentation: undo](http://vimdoc.sourceforge.net/htmldoc/undo.html)
- [Undo and Redo](http://vim.wikia.com/wiki/Undo_and_Redo)
- [How do I do redo (i.e. “undo undo”) in Vim?](https://stackoverflow.com/questions/1555779/how-do-i-do-redo-i-e-undo-undo-in-vim)
