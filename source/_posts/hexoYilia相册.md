---
title: hexo yilia添加相册功能
date: 2017-10-11 11:40:41
categories: hexo
keywords: 用法
tags: 教程
---


看了网上的那么多种方法，感觉还是这种方法的相册框架比较好看，而且json    还有时间显示，虽然在过程中有很多问题需要去调试，但还是在不断调试中实现了。
个人认为思路的确很重要的，有思路才能不断地去解决问题嘛，
1.首先要在主题那创建个photo目录
2.那图片存放到一个地方（例如github）用来做图片源
3.页面中的相册格式，有小图片，愿大图片之分

-----------
实现

+ 进入到你的博客目录下git bash执行
```
 hexo new page "photos"
```
![](/assets/blogImg/hexoyilia添加相册/目录.png)
<!--more-->
.在博客的source文件夹下建立一个photos文件夹
.将样式文件放到photos文件夹下[github](https://github.com/kayye/BlogBackup)里面有样式文件
![](/assets/blogImg/hexoyilia添加相册/样式文件.png)
+ 修改ins.js里面的放图片地址
```
 var render = function render(res) {
      var ulTmpl = "";
      for (var j = 0, len2 = res.list.length; j < len2; j++) {
        var data = res.list[j].arr;
        var liTmpl = "";
        for (var i = 0, len = data.link.length; i < len; i++) {
          var minSrc = 'https://raw.githubusercontent.com/kayye/BlogBackup/master/min_photos/' + data.link[i];
          var src = 'https://raw.githubusercontent.com/kayye/BlogBackup/master/photos/' + data.link[i];
          var type = data.type[i];
          var target = src + (type === 'video' ? '.mp4' : '.jpg');
          src += '';

```
minSrc和src地址，分别是你放小图片，大图片的创库

+ 图形的处理python脚本
还需要安装python工具[教程](https://www.liaoxuefeng.com/wiki/001374738125095c955c1e6d8bb493182103fac9270762a000/001374738150500472fd5785c194ebea336061163a8a974000)
blog根目录要有这几个脚本文件
![](/assets/blogImg/hexoyilia添加相册/根目录.png)
使用
```
python too.py
```
生成大图片小图片，并且自动上存到github上
若出现no module named PIL错误
出现这错误的原因是: PIL 模块找不到,PIL 模块已经过时了.
需要pip install pillow

+ 图片的格式要求
![](/assets/blogImg/hexoyilia添加相册/图片要求.png)
最前面是日期，然后用_进行分隔
后面是图片的描述信息，注意不要包含_和.符号

+ 最后就是
进入到你博客目录, 执行 python tool.py(处理图片,上传图片,生成 json 文件)
hexo clean (清理之前的 HTML 等)
hexo g (生成 HTML 文件)
hexo s (看看效果如何)
最后部署到你的博客上.



