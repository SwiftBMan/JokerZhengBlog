---
uuid: e712da93-76ed-11e9-b6f1-ff1747528169
title: yarn一些常用命令的使用
date: 2017-07-21 11:44:49
updated:
categories:
    - 终端命令
tags:
    - yarn
---
---

>文章摘要：介绍yarn的一些常用命令的使用 

 <!-- more -->

***
1. 初始化项目
{% codeblock %}
$ yarn init
{% endcodeblock %}
2. 添加依赖包
{% codeblock %}
$ yarn add [package]
$ yarn add [package]@[version]
$ yarn add [package]@[tag]
{% endcodeblock %}
{% codeblock %}
$ yarn add [package] --dev
$ yarn add [package] --peer 
$ yarn add [package] --optional
{% endcodeblock %}
3. 升级依赖包
{% codeblock %}
$ yarn upgrade [package]
$ yarn upgrade [package]@[version]
$ yarn upgrade [package]@[tag]
{% endcodeblock %}
4. 移除依赖包
{% codeblock %}
$ yarn remove [package]
{% endcodeblock %}
5. 安装项目的全部依赖
{% codeblock %}
$ yarn install 
或
$ yarn
{% endcodeblock %}
<!-- 内容 -->
***
{% note info %} 
 #### 相关链接：
 [yarn官网](https://yarnpkg.com/zh-Hans/)
{% endnote %}
{% note warning %} 
 转载请注明出处 
 文章有问题请指出
{% endnote %}