---
uuid: e712b380-76ed-11e9-b6f1-ff1747528169
title: UNIX命令详解之目录及文件操作命令
date: 2017-07-27 15:58:05
updated:
categories:
    - UNIX
tags:
    - UNIX命令
---
---


>文章摘要：详解UNIX命令之目录及文件操作命令

<!-- more -->

***
## ls
用法：
```
$ ls [-ABCFGHLOPRSTUWabcdefghiklmnopqrstuwx1] [file ...]
```
参数含义：
-A: 显示除 “.”和“..”外的所有文件
-B: 不输出以 “~”结尾的备份文件。
-C: 按列输出，纵向排序。
-F: 如果是文件夹，名字后面会加个/, 比如：folder/
-G: 输出文件的组的信息。
-H: 不懂这个干嘛用的，欢迎指出。
-L: 列出链接文件名而不是链接到的文件。
-O: 不懂这个干嘛用的，欢迎指出。
-P: 不懂这个干嘛用的，欢迎指出。
-R: 列出所有子目录下的文件。
-S: 以文件大小排序。
-T: 不懂这个干嘛用的，欢迎指出。
-U: 不懂这个干嘛用的，欢迎指出。
-W: 不懂这个干嘛用的，欢迎指出。
-a: 列出目录下的所有文件，包括以 . 开头的隐含文件。
-b: 把文件名中不可输出的字符用反斜杠加字符编号(就象在C语言里一样)的形式列出。
-c: 输出文件的 i 节点的修改时间，并以此排序。
-d: 将目录像文件一样显示，而不是显示其下的文件。
-e: 输出时间的全部信息，而不是输出简略信息。
-f: 此参数的效果和同时指定“aU”参数相同，并关闭“lst”参数的效果；
-g: 无用。
-h: 不懂这个干嘛用的，欢迎指出。
-i: 输出文件的 i 节点的索引信息。
-k: 以 k 字节的形式表示文件的大小。
-l: 列出文件的详细信息。
-m: 横向输出文件名，并以“，”作分格符。
-n: 用数字的 UID,GID 代替名称。
-o: 显示文件的除组信息外的详细信息。
-p: 不懂这个干嘛用的，欢迎指出。
-q: 用?代替不可输出的字符。
-r: 对目录反向排序。
-s: 在每个文件名后输出该文件的大小。
-t: 以时间排序。
-u: 以文件上次被访问的时间排序。
-w: 不懂这个干嘛用的，欢迎指出。
-x: 按列输出，横向排序。
-1: 一行只输出一个文件。
## pwd
```
$ pwd # 本命令用于显示当前的工作目录 
```
## cd
```
$ cd 回到注册进入时的目录 
$ cd /tmp 进入 /tmp 目录 
$ cd ../ 进入上级目录 
```
## mkdir
用法:
```
$ mkdir [-pv] [-m mode] directory ...

mkdir tmp 在当前目录下建立子目录 tmp 
mkdir -m 777 /tmp/abc 用所有用户可读可写可执行的存取模式 
建立目录 /tmp/aaa ，存取模式参看命令 chmod 
mkdir -p /tmp/a/b/c 建立目录 /tmp/a/b/c ，若不存在目录 /tmp/a 
及/tmp/a/b 则建立之 
```
## rmdir
用法:
```
$ rmdir [-p] directory ...

rmdir /tmp/abc 删除目录 /tmp/abc 
rmdir -p /tmp/a/b/c 删除目录 /tmp/a/b/c ，若目录 /tmp/a /b 
及/tmp/a 空，则删除 
```
## cat
用法:
```
$ cat [-benstuv] [file ...]
```
参数说明:
-b 显示行号，不包括空行
-e 在使用-v 选项时，在每一行的行尾显示 ＄ 
-n 显示行号，包括空行
-s 对不存在的文件不作提示
-t 在使用-v 选项时，将制表符（tab） 显示成 ^I，将换页符 
（formfeed）显示成 ^ L 
-u 无缓冲的输出(缺省为有缓冲输出)
-v 显示出文件中的非打印字符，控制字符显示成^n ，n为八进制数字， 
其他非打印字符显示成M-x ， x 为该字符低7位的8进制数值
## head
用法:
```
$ head [-n lines | -c bytes] [file ...]
```
<!-- 内容 -->
参数说明:
-n lines: 控制几行输出，默认10行
-c bytes: 控制字节输出
## cp
用法:
```
$ cp [-R [-H | -L | -P]] [-fi | -n] [-apvX] source_file target_file
$ cp [-R [-H | -L | -P]] [-fi | -n] [-apvX] source_file ... target_directory
```
## mv
用法:
```
$ mv [-f | -i | -n] [-v] source target
$ mv [-f | -i | -n] [-v] source ... directory
```
参数说明:
-i: 在覆盖已存在文件时作提示，若回答 y 则覆盖，其他则中止 
-f: 覆盖前不作任何提示 
## rm
用法:
```
$ rm [-f | -i] [-dPRrvW] file ...
       unlink file
```
说明: 用来删除文件或目录 
参数说明:
-f: 删除文件时不作提示
-r: 递归地删除目录及其所有子目录 
-i: 删除文件之前先作提示
## chmod
用法:
```
$ chmod [-fhv] [-R [-H | -L | -P]] [-a | +a | =a  [i][# [ n]]] mode|entry file ...
$ chmod [-fhv] [-R [-H | -L | -P]] [-E | -C | -N | -i | -I] file ...
```
说明: 改变文件的存取模式，存取模式可表示为数字或符号串
## chown
用法:
```
$ chown [-fhv] [-R [-H | -L | -P]] owner[:group] file ...
$ chown [-fhv] [-R [-H | -L | -P]] :group file ...
```
说明: 
文件的UID表示文件的文件主，文件主可用数字表示， 也可用一个有效的用户名表示，此命令改变一个文件的UID，仅当此文件的文件主或超级用户可使用。
参数说明:
-R: 递归地改变所有子目录下所有文件的存取模式 
## chgrp
用法:
```
$ chgrp [-fhv] [-R [-H | -L | -P]] group file ...
```
说明:
文件的GID表示文件的文件组，文件组可用数字表示， 也可用一个有效的组名表示，此命令改变一个文件的GID，可参看chown。
## cmp
用法:
```
$ cmp [OPTION]... FILE1 [FILE2 [SKIP1 [SKIP2]]]
```
说明:
比较两个文件，若文件1 为 "-" ，则使用标准输入， 两个文件相同则无提示，不同则显示出现第一个不同时的字符数和行号。 
## diff
用法:
```
$ diff [OPTION]... FILES
```
说明:
本命令比较两个文本文件，将不同的行列出来 
## wc
用法:
```
$ wc [-clmw] [file ...]
```
说明:
统计文件的行、字、字符数，若无指定文件，则统计标准输入
参数说明:
-c: 只统计字符数 
-w: 只统计字数
-l: 只统计行数
-m: 只统计字符数
## split
用法:
```
$ split [-a sufflen] [-b byte_count] [-l line_count] [-p pattern]
             [file [prefix]]
```
说明:
split 将指定大文件分解为若干个小文件，每个文件长度为n行(n 缺省时为1000)，第一个小文件名为指定的名字后跟aa，直至zz，名字缺省值为x，若未指定大文件名，则使用标准输入 
## touch
用法:
```
$ touch [-A [-][[hh]mm]SS] [-acfhm] [-r file] [-t [[CC]YY]MMDDhhmm[.SS]] file ...
```
说明: 将指定文件的访问时间和修改时间改变，若指定文件不存在则创建之，若无指定时间，则使用当前时间，返回值是未成功改变时间的文件个数，包括不存在而又未能创建的文件。
参数说明:
-a 只改变访问时间
-m 只改变修改时间
-c 若文件不存在，不创建它且不作提示 
mmddhhmm[yy] 两位表示 月日时分[年] 
## file
用法:
```
file [OPTION...] [FILE...]
```
说明:
file 对指定文件进行测试，尽量猜测出文件类型并显示出来 
-f 文件名文件 文件名文件是一个包含了文件名的文本文件， -f 选项测试 
文件名文件中所列出的文件 
## find
```
$ find [-H | -L | -P] [-EXdsx] [-f path] path ... [expression]
$ find [-H | -L | -P] [-EXdsx] -f path [path ...] [expression]
```
## grep
```
$ grep [-abcDEFGHhIiJLlmnOoqRSsUVvwxZ] [-A num] [-B num] [-C[num]]
    [-e pattern] [-f file] [--binary-files=value] [--color=when]
    [--context[=num]] [--directories=action] [--label] [--line-buffered]
    [--null] [pattern] [file ...]
```
## vi
说明: 
vi 是一个基于行编辑器 ex 上的全屏幕编辑器
***
{% note info %} 
 #### 相关链接：
 [UNIX经典命令详解](http://blog.chinaunix.net/uid-20489505-id-70154.html)
 [Linux命令大全](http://man.linuxde.net)
{% endnote %}
{% note warning %} 
 转载请注明出处 
 文章有问题请指出
{% endnote %}