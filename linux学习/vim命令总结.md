---
title: vim命令总结
date: 2018-10-11 09:21:15
tags:
---
vim使用总结

vim总共有三种模式一个是末行模式、一个是命令模式、还有一个是编辑模式

### 1. 末行模式

命令模式下输入: 或者? 或者/都可以进入末行模式，末行模式主要是通过输入参数进行文档控制

常见的末行模式命令

:set nu  -显示行号

:syntax off/on - 关闭/开启高亮语法

:set nonu - 不显示行号

:wq - 保存文件并退出

:q! - 强制退出

:set autoindent 设置自动缩进(在编写html时建议打开)

/<regex>  搜索满足正则表达式的内容

​	n---向光标下继续搜索
​	N---向光标上继续搜索

?<regex>

​	n---向光标上方继续搜索
​	N---向光标下方继续搜索

:开始行数,结束行数s/词1/词2 (将从开始行数到结束行数中的词1全部替换成词2)

:1,$s/被替换的词/替换的词/gice

​	gice中:
​	g-是全局搜索
​	i-是忽略大小写
​	c-是每次找到询问是否替换

​		n--不替换
​		y--不替换
​		a--全部替换
​		q--退出

​	e-忽略错误

当同时打开多个文件时:ls表示显示所有打开的文件编号

:b 文件编号 切换其他的文件

:vs 垂直拆分窗口

​	光标最开始在左边按两次ctrl+w，光标会切换到右边的窗口
然后在:b 文件编号 切换当前窗口的文件内容

:sp 水平拆分窗口

​	光标最开始在上边窗口按两次ctrl+w，光标会切换到下边的窗口

:qa 退出全部窗口

:wqa 保存并退出全部窗口

:map <键> 命令
​	:map <F2> gg99999999dd 设置F2为快捷键(删除99999999行内容)

:imap - 设置编辑模式下的快捷键
:inoremap _main if __name__ == '__main__':
​	设置在编辑模式下,不要递归(inore)的映射当输入_main补全后面的内容



### 2.命令模式

在编辑模式下按Esc键进入命令模式

在命令模式下按两次shift+z 就是保存文件并退出

#### 2.1 移动光标

gg 光标移动到第一行

G 光标移动到最后一行

nG 光标移动到指定函数

$ 光标移动到行末

0 光标移动到行首

h 光标向左移动一列

​	nh 光标向左移动指定列数

j 光标向下移动一行

​	nj 光标向下移动指定行数

k 光标向上移动一行

​	nk 光标向上移动指定行数

l 光标向右移动一列

​	nl 光标向右移动指定列数

HML(H光标移动当前页行首，M光标移动当前页中间，L光标移动当前页末行)

w 光标移动一个单词

#### 2.2 删除内容

dd 删除光标所在那一行的内容

100dd 删除光标之后的100行内容(包括光标所在行)

dw 删除光标之后的一个单词

d$ 从光标所在的位置删到行尾

d0 从光标所在的位置删到行首

u 撤销删除

ctrl+r 恢复

#### 2.3 复制

yy 复制光标所在的那一行

3yy 复制光标之后的3行(包括光标所在行)

p 在光标所在行粘贴一次

10p 在光标所在行粘贴10次(光标自动下移)

#### 2.4 翻页

ctrl+e 向下翻一行

ctrl+y 向上翻一行

ctrl+f 向下翻一页

ctrl+b 向上翻一页

### 3.编辑模式

i 在光标所在处进入编辑模式

o 在光标下一行进入编辑模式

a 在当前光标的右边进入编辑模式

ctrl+x and ctrl+o 代码提示快捷键

### 4.1 其他常用命令

vim -d 文件一 文件二 (打开两个文件)

