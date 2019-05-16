---
uuid: e712da92-76ed-11e9-b6f1-ff1747528169
title: npm的一些常用命令
date: 2017-07-19 22:18:45
updated:
categories:
    - 终端命令
tags:
    - npm
---
---

>文章摘要：介绍npm一些常用命令的使用
 
 <!-- more -->

***
<!-- 内容 -->
1. 安装模块
{% codeblock 全局安装 %}
$ npm install <Module Name> -g
{% endcodeblock %}
{% codeblock 局部安装 %}
$ npm install <Module Name>
{% endcodeblock %}
{% note info %}
你需要在当前的目录下执行初始化，也就是说当前目录必须有 package.json 文件。或者，你在当前的目录下人为的建立好node_modules目录否则npm会一直向上寻找package.json的所在目录，或者是node_modules目录，最后终止在用户根目录。
{% endnote %}
2. 查看安装的模块及依赖
{% codeblock 查看全局模块及依赖 %}
$ npm ls -g
{% endcodeblock %}
{% codeblock 查看局部模块及依赖 %}
$ npm ls
{% endcodeblock %}
3. 卸载模块
{% codeblock 全局卸载模块 %}
$ npm uninstall <Module Name> -g
{% endcodeblock %}
{% codeblock 局部卸载模块 %}
$ npm uninstall <Module Name>
{% endcodeblock %}
4. 缓存验证
{% codeblock %}
$ npm cache verify
{% endcodeblock %}
5. 清理缓存
{% codeblock --force强制的意思 %}
$ npm cache clean --force
{% endcodeblock %}
6. 检查模块是否已经过时
{% codeblock %}
$ npm outdated
{% endcodeblock %}
7. 更新模块
{% codeblock %}
$ npm update
{% endcodeblock %}
8. 升级npm
{% codeblock %}
$ npm i -g npm
{% endcodeblock %}
9. 查看npm版本
{% codeblock %}
$ npm -v
{% endcodeblock %}
10. 查看某个模块的版本号
{% codeblock %}
$ npm list <Module name>
{% endcodeblock %}
11. 搜索模块
{% codeblock %}
$ npm search <Module name>
{% endcodeblock %}
***
{% note info %} 
 #### 相关链接：
 [NPM 官网](https://www.npmjs.com)
 [NPM 使用介绍](http://www.runoob.com/nodejs/nodejs-npm.html)
 [NPM 常用命令详解](http://www.cnblogs.com/PeunZhang/p/5553574.html)
{% endnote %}
{% note warning %} 
 转载请注明出处 
 文章有问题请指出
{% endnote %}


