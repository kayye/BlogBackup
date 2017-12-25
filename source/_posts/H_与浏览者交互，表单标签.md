---
title: H_与浏览者交互，表单标签
date: 2016-04-23 20:27:45
tags: HTML
categories: HTML
---


网站怎样与用户进行交互？
----------------------
　　　答案是使用HTML表单(form)。表单是可以把浏览者输入的数据传送到服务器端，这样服务器端程序就可以处理表单传过来的数据。

　　　语法：
            <from method="传送方式" action="服务器文件">  

讲解：

+ 1.<form>：该标签是成对出现的，以<form>开始，以</form>结束。

+ 2.action ：浏览者输入的数据被传送到的地方,比如一个PHP页面(save.php)。

+ 3.数据传送的方式(get/post)

```
    <from method=post" action="save.php">
        <label for="username">用户名:</label>   
        <input type="text" name="username" />        -----用户名输入框
        <label for="pass">密码:</label>
        <input type="password" name="pass" />        -----密码输入框
    </from>

```

>注意：
>1、所有表单控件（文本框、文本域、按钮、单选框、复选框等）
都必须放在<form></form>标签之间（否则用户输入的信息可提交不到服务器上哦！）。
>
>2、method:post/get的区别这一部分内容属于后端程序员考虑的问题。感兴趣的小伙伴可以查看本小节的wiki，里面有详细介绍。


---
<!--more-->

文本(密码)输入框,<input>标签
---------------------
　　　语法：
            <form>
                <input type="text/password" name="名称" value="文本" />
            </form>

+　1、type：
　　    -当type="text"时，输入框为文本输入框;
　　    -当type="password"时, 输入框为密码输入框。

+ 2、name：为文本框命名，以备后台程序ASP 、PHP使用。

+ 3、value：为文本输入框设置默认值。(一般起到提示作用)


　　　举例：

```
        <form>
            姓名：
                <input type="text" name="myName" />
            <br />
            密码：
                <input type="password" name="pass" />
            </form>

```

---

单选框，复选框,<input>标签
---------------
　　　语法：
            <input type="radio/checkbox" value="值" name="名称" checked="checked" />

+ 1、type:
　　　当 type="radio" 时，控件为单选框
　　  当 type="checkbox" 时，控件为复选框

+ 2、value：提交数据到服务器的值（后台程序PHP使用）

+ 3、name：为控件命名，以备后台程序 ASP、PHP 使用

+ 4、checked：当设置 checked="checked" 时，该选项被默认选中　  

>注意:同一组的单选按钮，name 取值一定要一致

　　　举例：

```
        <form action="save.php" method="post" >
            <label>性别:</label>
            <label>男</label>
                <input type="radio" value="1"  name="gender" />
            <label>女</label>
                <input type="radio" value="2"  name="gender" />
            </form>

```
---

提交按钮，<input>标签
-----------------
　　　语法：
            <input type="submit" value="提交" name ="..." />

+ 1.type：只有当type值设置为submit时，按钮才有提交作用
+ 2.value：按钮上显示的文字


---

重置按钮,<input>标签
-------------------------
　　　语法：
            <input type="reset" value="重置" name="..." />

+ 1.type：只有当type值设置为reset时，按钮才有重置作用
+ 2.value：按钮上显示的文字

---

文本域，<textare>标签
------------------------
　　　语法:
            <textarea rows="行数" cols="列数">文本</textarea>

+ 1、<textarea>标签是成对出现的，以<textarea>开始，以</textarea>结束。

+ 2、cols ：多行输入域的列数。

+ 3、rows ：多行输入域的行数。

+ 4、在<textarea></textarea>标签之间可以输入默认值。

　　　举例：

```
            <form method="post" action="sava.php">
                <label>联系我们</label>
                <textarea cols="50" rows="10">
                    在这里输入默认内容
                </textarea>
            </form>

```

>注意:这两个属性可用css样式的width和height来代替：
　　　col用width、row用height来代替。


---

下拉列表框，<select>标签
--------------------
　　　语法：
            <select>
                <option value="提交值1">选项1</option>
                <option value="提交值1">选项2</option>
                ...
            </select>


>注意：value="提交值"，是向服务器提交的值

+ 1.设置默认选中
　　　设置selected="selected"属性，则该选项就被默认选中。

　　　举例：
        <option value="旅游" selected="selected">旅游</option>

+ 2.设置多选
　　　在<selec>标签中设置multiple="multiple"属性，就可以实现多选功能，

　　　在 widows 操作系统下，进行多选时按下Ctrl键同时进行单击（在 Mac下使用 Command +单击），可以选择多个选项。

　　　举例：
        <select multiple="multiple">
            ....
        </select>


---

from表单中的<label>标签
----------------------
　　　label标签不会向用户呈现任何特殊效果，它的作用是为鼠标用户改进了可用性。
　　　如果你在 label 标签内点击文本，就会触发此控件。就是说，当用户单击选中该label标签时，浏览器就会自动将焦点转到和标签相关的表单控件上（就自动选中和该label标签相关连的表单控件上）。

　　　
　　　语法：
            <label for="控件id名称">

>注意：标签的 for 属性中的值应当与相关控件的 id 属性值一定要相同。

　　　举例：

```
            <form>
                <label for="male">男</label>
                <input type="radio" name="gender" id="male" />
                <br />
                <label for="female">女</label>
                <label type="radio" name="gender" id="female" />
                <br />
                <label for="email">输入你的邮箱地址</label>
                <input type="email" id="email" placeholder="Enter email">
            </form>

```