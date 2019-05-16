---
uuid: e712da91-76ed-11e9-b6f1-ff1747528169
title: brew命令的使用
date: 2017-07-18 00:38:28
updated: 
categories:
    - 终端命令
tags:
    - brew
---
---
>介绍brew一些常用命令的使用
  
 <!-- more -->

***
1. 查看brew帮助
```
$ brew help
```
2. 搜索软件
 ```
 $ brew search [TEXT|/REGEX/]
 ```
3. 安装软件
```
$ brew install FORMULA...
```
4. 卸载软件
```
$ brew uninstall FORMULA...
```
5. 显示已经安装的软件列表
```
$ brew list [FORMULA...]
```
6. 查看过期的软件
```
$ brew outdated
```
7. 更新 Homebrew 自己
```
$ brew update
```
8. 更新某个具体软件
```
$ brew upgrade [FORMULA...]
```
9. 更新所有软件
```
$ brew upgrade
```
10. 查看软件信息、网站、选项
```
$ brew (info|home|options) [FORMULA...]
```
11. 清除软件老版本
```
$ brew cleanup
```
12. 清除某个软件老版本
```
$ brew cleanup FORMULA...
```
13. 查看配置
```
$ brew config
```
14. 查看有没有安装的问题
```
$ brew doctor
```
15. 更新和软件升级
```
$ brew update && brew upgrade
```
***
{% note info %} 
 #### 相关链接：
 [Homebrew官网](https://brew.sh)
{% endnote %}
{% note warning %} 
 转载请注明出处 
 文章有问题请指出
{% endnote %}









