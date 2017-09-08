---
title: sublimeText
date: 2017-01-07 11:28:41
categories: sublimeText
keywords: sublime 快捷键
tags: 命令
---


sublime text 3快捷键与使用技巧介绍
<!--more-->

#快捷键

强大的快捷键，提高你的编码效率。
常用快捷键

CTRL+N：新建文件
CTRL+w：关闭文件
CTRL+O：打开文件
CTRL+Z：撤销
CTRL+Y：撤销还原
CTRL+F：查找
CTRL+H：替换
Esc：小工具窗口隐藏
 
#编码快捷键

Ctrl+Shift+P 打开命令面板，如设置编码语言
Tab：缩进、自动完成
Shift+Tab 去除缩进
Ctrl+J 合并行（已选择需要合并的多行时）
Ctrl+T 词互换
Ctrl+U 软撤销
Ctrl+K Backspace 从光标处删除至行首
Ctrl+KK 从光标处删除至行尾
Ctrl+K+T 折叠属性
Ctrl+K+U 改为大写
Ctrl+K+L 改为小写
Ctrl+K+0 展开所有
Ctrl+Enter 插入行后（快速换行）
Ctrl+Shift+/ 注释已选择内容
Ctrl+Shift+↑可以移动此行代码，与上行互换
Ctrl+Shift+↓可以移动此行代码，与下行互换
Ctrl+Shift+[ 折叠代码
Ctrl+Shift+] 展开代码
Ctrl+/ 注释整行（如已选择内容，同“Ctrl+Shift+/”效果）
Ctrl+Shift+A 选择光标位置父标签对儿
Ctrl+Shift+D 复制光标所在整行，插入在该行之前
Ctrl+Shift+K 删除整行
Ctrl+Shift+L 鼠标选中多行（按下快捷键），即可同时编辑这些行
Ctrl+Shift+M 选择括号内的内容（按住-继续选择父括号）
Ctrl+Shift+Enter 光标前插入行
Ctrl+PageDown 、Ctrl+PageUp 文件按开启的前后顺序切换
Ctrl+鼠标左键 可以同时选择要编辑的多处文本
Shift+鼠标右键（或使用鼠标中键）可以用鼠标进行竖向多行选择
 
#查找快捷键

CTRL+P：查找当前项目中的文件和快速搜索，快速查找标签位置
Ctrl+P输入 @ 查找文件主标题/函数；或输入：跳转到文件某行
CTRL+G：跳转到指定行
CTRL+F：查找
Ctrl+D 选词 （反复按快捷键，即可继续向下同时选中下一个相同的文本进行同时编辑）
Ctrl+L 选择整行（按住-继续选择下行）
Ctrl+M 光标移动至括号内开始或结束的位置
Ctrl+R 快速列出/跳转到某个函数
ctrl+shift+F 在文件夹内查找，与普通编辑器不同的地方是sublime允许添加多个文件夹进行查找

#其他快捷键

Ctrl+K+B 开启/关闭侧边栏
Ctrl+Tab 当前窗口中的标签页切换
Ctrl+F2 设置书签
Shift+F2 上一个书签
Alt+Shift+1（非小键盘）窗口分屏，恢复默认1屏
Alt+Shift+2 左右分屏-2列
Alt+Shift+3 左右分屏-3列
Alt+Shift+4 左右分屏-4列
Alt+Shift+5 等分4屏
Alt+Shift+8 垂直分屏-2屏
Alt+Shift+9 垂直分屏-3屏
Alt+. 闭合当前标签
Alt+F3 选中文本按下快捷键，即可一次性选择全部的相同文本进行同时编辑
Tab 缩进 自动完成
F2 下一个书签
F6 检测语法错误
F9 行排序(按a-z)
F11 全屏模式

#安装插件准备步骤

安装package control

1.按Ctrl+`调出console
2.在底部代码行贴上以下代码并回车：

sublimeText 2：
```
import urllib2,os; pf='Package Control.sublime-package'; ipp = sublime.installed_packages_path(); os.makedirs( ipp ) if not os.path.exists(ipp) else None; urllib2.install_opener( urllib2.build_opener( urllib2.ProxyHandler( ))); open( os.path.join( ipp, pf), 'wb' ).write( urllib2.urlopen( 'http://sublime.wbond.net/' +pf.replace( ' ','%20' )).read()); print( 'Please restart Sublime Text to finish installation')
```

sublimeText 3:
```
import urllib.request,os; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); open(os.path.join(ipp, pf), 'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())
```
3.重启sublime text，如果在Perferences->package settings中看到package control这一项，则安装成功。

点击Preferences→Package Control，显示以下弹窗：
```
Disable Package ：禁用插件
enable Package ：启用插件
Install Package ：安装插件
List Package ：查看已安装插件列表
Remove Package ：移除插件
Upgrade Package ：升级插件
```

安装插件

Preferences→Package Control→Install Package，输入插件名称，会看到编辑器的底部在loading下载安装中，安装完后，一般重启即可。


#编码快捷键，前端必备-Emmet

Emmet作为zen coding的升级版，对于前端来说，可是必备插件，如果你对它还不太熟悉，可以在其官网（http://docs.emmet.io/）上看下具体的视频教程。或者是也可以再这里看http://docs.emmet.io/cheat-sheet/
举例：ul#nav>li.item$*4>a{Item $}  然后Tab键
显示结果是
```
<ul id="nav">
    <li class="item1"><a href="">Item 1</a></li>
    <li class="item2"><a href="">Item 2</a></li>
    <li class="item3"><a href="">Item 3</a></li>
    <li class="item4"><a href="">Item 4</a></li>
</ul>
```
有够快么？还有更多例子，请看http://docs.emmet.io/abbreviations/syntax/##

####快捷输出dtd头文件，即HTML头部信息

在没装emmet插件的情况下，如果输入html，显示的仅是简单的html结构，不包含dtd头文件，这让人很郁闷。不过以下的解决方法挺不错，支持多种头文件，html5的写法也支持哦~
在装了emmet插件之后，可以使用html:4t、html:4s、html:xt、html:xs、html:xxs、html:5等6中dtd设置中的一种，然后TAB键，即可快速生成头文件。关于头文件，以前经常使用的是html:xt这个格式的，也就是dreamweaver自动生成的头文件。不过现在标准的是html:5的头文件，基本的浏览器都支持了，没什么问题。

#让Sublime Text2支持快捷键在浏览器中预览

用过dreamweaver的同学都知道，F12能快捷在浏览器中浏览正在编辑的文件。而这个功能在sublime需要，点击右键，然后open in browser。这显然还不够便捷。下面来看怎么解决吧~
Sublime Text2支持用Python编写插件，详细步骤是：
一、点击菜单Tools -> New Plugin…，在创建好的py文件输入下列内容：

```
import sublime, sublime_plugin
import webbrowser
 
url_map = {
    '/Users/jerry/Sites/test/' : 'http://test/',
}
 
class OpenBrowserCommand(sublime_plugin.TextCommand):
    def run(self,edit):
        window = sublime.active_window()
        window.run_command('save')
        url = self.view.file_name()
        for path, domain in url_map.items():
            if url.startswith(path):
                url = url.replace(path, domain).replace('\\', '\/')
                break
 
        webbrowser.open_new(url)
```

将文件保存到Packages/User目录（Packages可通过菜单里的Browser Packages…打开），文件名随意，如open_browser.py。插件部分完工了。
二、接下来，为刚才的插件分配快捷键。点菜单Tools -> Command Palette…，或者f12，打开命令集，选择“key Bindings – User”打开个人快捷键配置，输入下列内容：

```
[{ "keys": ["f12"], "command": "open_browser" }]
```
这就是要做的全部工作，可以测试下了。打开一个html文件，f12试试，没意外的话文件会在默认浏览器打开了。url_map里配置的站点目录到URL的映射应该也是可用的。
PS：如果要指定用什么浏览器预览，也可以将最后一行代码改成这样：
```
webbrowser.get('safari').open_new(url)
```

实用的sublime插件集合 
http://blog.csdn.net/jianhua0902/article/details/43761899




