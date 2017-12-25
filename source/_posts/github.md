---
title: github
date: 2017-09-12 15:29:41
categories: github
keywords: 用法
tags: 教程
---

github的操作问题   
====




+ github分支问题 


```
创好新的分支
git banch <分支名> #创建分支
git checkout       #切换分支
git checkout -b    #切换+创建分支

创建好后切换到新分支，先进行push
git push origin <新分支名>
```
<!--more-->

+ Another git process seems to be running in this repository...”问题解决
![](/assets/blogImg/github/running in this repository.png)
造成原因，多数为git push 过程中突然中断而造成的。

根据vs2017的git管理工具的提示信息，打开文件夹选项，打开显示隐藏文件，进入工作区目录下的隐藏文件.git，其中的index.lock文件删除掉，然后重新打开git bash进程，问题解决。
![](/assets/blogImg/github/running_solve.jpg)