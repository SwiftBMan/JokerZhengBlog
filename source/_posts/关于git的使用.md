---
uuid: e712da97-76ed-11e9-b6f1-ff1747528169
title: 关于git的使用
date: 2017-07-26 10:07:49
updated:
categories:
    - git
tags:
    - git
---
---

>文章摘要：git常用命令的使用

<!-- more -->

***
1. 什么是Git？
Git是一个开源的分布式版本控制系统，用于敏捷高效地处理任何或小或大的项目。
Git 是 Linus Torvalds 为了帮助管理 Linux 内核开发而开发的一个开放源码的版本控制软件。
Git 与常用的版本控制工具 CVS, Subversion 等不同，它采用了分布式版本库的方式，不必服务器端软件支持。
2. Git 与 SVN 区别？
GIT不仅仅是个版本控制系统，它也是个内容管理系统(CMS),工作管理系统等。
如果你是一个具有使用SVN背景的人，你需要做一定的思想转换，来适应GIT提供的一些概念和特征。
Git 与 SVN 区别点：
(1) GIT是分布式的，SVN不是：这是GIT和其它非分布式的版本控制系统，例如SVN，CVS等，最核心的区别。
(2) GIT把内容按元数据方式存储，而SVN是按文件：所有的资源控制系统都是把文件的元信息隐藏在一个类似.svn,.cvs等的文件夹里。
(3) GIT分支和SVN的分支不同：分支在SVN中一点不特别，就是版本库中的另外的一个目录。
(4) GIT没有一个全局的版本号，而SVN有：目前为止这是跟SVN相比GIT缺少的最大的一个特征。
(5) GIT的内容完整性要优于SVN：GIT的内容存储使用的是SHA-1哈希算法。这能确保代码内容的完整性，确保在遇到磁盘故障和网络问题时降低对版本库的破坏。
3. Git安装配置
Git 各平台安装包下载地址为：[http://git-scm.com/downloads](http://git-scm.com/downloads)
Mac系统下载后安装即可。
或者
```
$ brew install git
```
4. Git工作流程
一般工作流程如下：
(1) 克隆 Git 资源作为工作目录。
(2) 在克隆的资源上添加或修改文件。
(3) 如果其他人修改了，你可以更新资源。
(4) 在提交前查看修改。
(5) 提交修改。
(6) 在修改完成后，如果发现错误，可以撤回提交并再次修改并提交。
5. 同步到远程仓库
```
$ mkdir ceshi                   # 创建ceshi文件夹
$ cd ceshi                      # 转到ceshi目录
$ git init                      # 初始化git
$ echo "# ceshi" >> README.md   # 写入# ceshi到 README.md
$ git add README.md             # 添加
$ git commit -m "first commit"  # 提交
$ git remote add origin https://git.coding.net/SwiftMan/ceshi.git # 添加远程仓库地址
$ git push -u origin master # 同步到远程仓库
```
6. git的详细使用
- Git 为你的每一个提交都记录你的名字与电子邮箱地址，所以第一步需要配置用户名和邮箱地址。
```
$ git config --global user.name 'runoob' 
$ git config --global user.email test@runoob.com
```
- 创建仓库
Git 使用 git init 命令来初始化一个 Git 仓库，Git 的很多命令都需要在 Git 的仓库中运行，所以 git init 是使用 Git 的第一个命令。
在执行完成 git init 命令后，Git 仓库会生成一个 .git 目录，该目录包含了资源的所有元数据，其他的项目目录保持不变（不像 SVN 会在每个子目录生成 .svn 目录，Git 只在仓库的根目录生成 .git 目录）。
```
$ git init   # 该命令执行完后会在当前目录生成一个 .git 目录
$ git init newrepo # 使用我们指定目录作为Git仓库
```
- 以下命令将目录下以 .c 结尾及 README 文件提交到仓库中。
```
$ git add *.c
$ git add README
$ git commit -m "初始化项目版本"
```
- 我们使用 git clone 从现有 Git 仓库中拷贝项目（类似 svn checkout）
```
$ git clone <repo>
$ git clone <repo> <directory>
参数说明：
repo:Git 仓库。
directory:本地目录。
例如要克隆 Ruby 语言的 Git 代码仓库 Grit，可以用下面的命令：
$ git clone git://github.com/schacon/grit.git
执行该命令后，会在当前目录下创建一个名为grit的目录，其中包含一个 .git 的目录，用于保存下载下来的所有版本记录。
如果要自己定义要新建的项目目录名称，可以在上面的命令末尾指定新的名字：
$ git clone git://github.com/schacon/grit.git mygrit
$ git status -s # 命令用于查看项目的当前状态, -s 参数，以获得简短的结果输出
```
- git diff
```
$ git diff # 尚未缓存的改动
$ git diff --cached # 查看已缓存的改动
$ git diff HEAD # 查看已缓存的与未缓存的所有改动
$ git diff --stat # 显示摘要而非整个 diff
```
- git commit
```
$ git commit -m ‘ddd‘ #  将缓存区内容添加到仓库中
如果你觉得 git add 提交缓存的流程太过繁琐，Git 也允许你用 -a 选项跳过这一步
$ git commit -am '修改 hello.php 文件'
```
- $ git reset HEAD -- hello.php  # 取消hello.php的缓存
- git rm
git rm 会将条目从缓存区中移除。这与 git reset HEAD 将条目取消缓存是有区别的。 "取消缓存"的意思就是将缓存区恢复为我们做出修改之前的样子。
默认情况下，git rm -f file 会将文件从缓存区和你的硬盘中（工作目录）删除。
如果你要在工作目录中留着该文件，可以使用 git rm --cached：
- git mv
git mv 命令做得所有事情就是 git rm --cached 命令的操作， 重命名磁盘上的文件，然后再执行 git add 把新文件添加到缓存区。
- git remote
```
$ git remote # 要查看当前配置有哪些远程仓库
$ git remote -v # 执行时加上 -v 参数，你还可以看到每个别名的实际链接地址
```
- 提取远程仓库
Git 有两个命令用来提取远程仓库的更新。
1、从远程仓库下载新分支与数据：
git fetch
该命令执行完后需要执行git merge 远程分支到你所在的分支。
2、从远端仓库提取数据并尝试合并到当前分支：
git pull
该命令就是在执行 git fetch 之后紧接着执行 git merge 远程分支到你所在的任意分支。
假设你配置好了一个远程仓库，并且你想要提取更新的数据，你可以首先执行 git fetch [alias] 告诉 Git 去获取它有你没有的数据，然后你可以执行 git merge [alias]/[branch] 以将服务器上的任何更新（假设有人这时候推送到服务器了）合并到你的当前分支。
推送你的新分支与数据到某个远端仓库命令
$ git push [alias] [branch]
以上命令将你的 [branch] 分支推送成为 [alias] 远程仓库上的 [branch] 分支，实例如下。
- 删除远程仓库
删除远程仓库你可以使用命令：
git remote rm [别名]
- 建立分支
要先commit一次才会真正建立master分支
创建分支命令：
$ git branch (branchname)
切换分支命令:
$ git checkout (branchname)
当你切换分支的时候，Git 会用该分支的最后提交的快照替换你的工作目录的内容， 所以多个分支不需要多个目录。
合并分支命令:
$ git merge 
没有参数时，git branch 会列出你在本地的分支
$ git branch 
我们也可以使用 git checkout -b (branchname) 命令来创建新分支并立即切换到该分支下，从而在该分支中操作。
- 删除分支
$ git branch -d/-D(没有第一次合并过分支的时候用-D) (branchname)
- 查看提交历史
```
$ git log # 查看提交历史
$ git log --oneline # 查看历史记录的简洁版本
$ git log --oneline --graph # 查看历史中什么时候出现了分支、合并
$ git log --reverse --oneline # '--reverse'参数来逆向显示所有日志

如果只想查找指定用户的提交日志可以使用命令：git log --author , 例如，比方说我们要找 Git 源码中 Linus 提交的部分：
$ git log --author=Linus --oneline -5

如果你要指定日期，可以执行几个选项：--since 和 --before，但是你也可以用 --until 和 --after。 
例如，如果我要看 Git 项目中三周前且在四月十八日之后的所有提交，我可以执行这个（我还用了 --no-merges 选项以隐藏合并提交）：
$ git log --oneline --before={3.weeks.ago} --after={2010-04-18} --no-merges
```
- Git 标签
```
$ git tag -a v1.0  # 创建带注解的标签

$ git log --oneline --decorate --graph # 注意当我们执行 git log --decorate 时，我们可以看到我们的标签了

$ git tag # 查看所有标签

如果我们忘了给某个提交打标签，又将它发布了，我们可以给它追加标签。
例如，假设我们发布了提交 85fc7e7(上面实例最后一行)，但是那时候忘了给它打标签。 我们现在也可以：
git tag -a v0.9 85fc7e7

指定标签信息命令：
$ git tag -a <tagname> -m "w3cschool.cc标签"

PGP签名标签命令：
$ git tag -s <tagname> -m "w3cschool.cc标签"

$ git tag -d v1.0 # 删除标签

查看此版本所修改的内容
$ git show v1.0
```
<!-- 内容 -->
***
{% note info %} 
 #### 相关链接：
 [Git 教程](http://www.runoob.com/git/git-tutorial.html)
{% endnote %}
{% note warning %} 
 转载请注明出处 
 文章有问题请指出
{% endnote %}