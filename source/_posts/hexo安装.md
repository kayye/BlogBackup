---
title: hexo install
date: 2017-09-06 22:29:41
categories: hexo
keywords: 用法
tags: 教程
---


安装环境
===========
·安装node.js
进入官网(https://nodejs.org/en/)
下载安装包，直接点击安装就可以了
<!--more-->
·安装git （因为要给github上传文章）
git官网(http://git-scm.com)
Windows: 直接下载和安装
Mac：进入git网站下载和安装，或者进入这里下载
Ubuntu：打开终端复制粘贴命令 sudo apt-get install git-core


·安装、配置Hexo
```
npm install -g hexo-cli
```

·创建hexo目录并初始化
```
$ mkdir hexo
$ cd hexo
$ hexo init
```

·然后就可以生成网站，启动服务了：
```
$ hexo clean   
$ hexo generate
$ hexo server
```

·hexo文件夹
先来看一下hexo文件夹下的内容：
```
hexo/
|- node_modules/  # hexo需要的模块，不需要上传GitHub
|- themes/        # 主题文件，需要上传GitHub的dev分支
|- sources/       # 博文md文件，需要上传GitHub的dev分支
|- public/        # 生成的静态页面，由hexo deploy自动上传到gh-page分支
|- package.json   # 记录hexo需要的包信息，不需要上传GitHub
|- _config.yml    # 全局配置文件，需要上传GitHub的dev分支
|- .gitignore     # hexo生成默认的.gitignore，它已经配置好了不需要上传的hexo文件
```


配置自己的_config.yml
============
翻到最下面
```
deploy:
  type: git
  repository: https://github.com/<自己的github账号>/blog.git
  branch: gh-pages
```

主题
========




