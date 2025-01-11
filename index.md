---
title: Welcome to my blog
---
# HTML基础

## html概述

​	定义：html是构建网页和 web 应用程序的超文本标记语言

​	基本骨架：

```html
<!-- ! + Enter/Tab键 可以快速生成html的基本骨架-->
<!DOCTYPE html>
<html>
<head>
    <title>html练习页面</title>
</head>
  <body>
    网页主体
  </body>
</html>
```



## html的基本标签

### 标题和段落标签

```html
<h1>这是标题标签</h1>

<p>这是段落标签</p>

<!-- 换行 -->
<br>
<!-- 水平线 -->
<hr>
```



### 文本格式化标签

​	左列的语义化标签

| 标签名 | 效果                  | 标签名 | 效果          |
| ------ | --------------------- | ------ | ------------- |
| strong | <strong>加粗</strong> | b      | <b>加粗</b>   |
| em     | <em>倾斜</em>         | i      | <i>倾斜</i>   |
| ins    | <ins>下划线</ins>     | u      | <u>下划线</u> |
| del    | <del>删除线</del>     | s      | <s>删除线</s> |



### 图片和超链接标签

​	**\<img>**

```html
<!-- src用于指定图像的路径 -->
<img src="./cat.jpg" alt="替换文本" title="提示文本">
```

​	**\<a>**

```html
<!-- href是连接地址 target="_blank"是新建跳转	-->
<a href="https://www.baidu.com/" target="_blank">我是百度网址</a>
```

​	

### 音频和视频

​	音频标签：**\<audio>**

```html
<!-- src 支持格式：MP3、Ogg、Wav -->
<audio src="./media/music.mp3" controls loop autoplay></audio>
```

​	视频标签：**\<video>**

```html
<!-- src 支持格式：MP4、WebM、Ogg -->
<video src="视频的URL"></video>
```

​	常用属性

| 属性     | 作用                  |
| -------- | --------------------- |
| src      | 视频/音频URL          |
| controls | 显示视频/音频控制面板 |
| loop     | 循环播放              |

​	

# HTML的进阶

## 列表

​	**无序列表**

```html
<!-- ul 标签里面只能包裹 li 标签，li 标签里面可以包裹任何内容 -->
<ul>
  <li>第一项</li>
  <li>第二项</li>
  <li>第三项</li>
</ul>
```

​	**有序列表**

```html
<ol>
  <li>第一项</li>
  <li>第二项</li>
  <li>第三项</li>
</ol>
```

​	**自定义列表**

```html
<dl>
  <dt>列表标题</dt>
  <dd>列表描述 / 详情</dd>
   ……
</dl>
```



## 表格\<table>

```html
<table border="1">
  <tr>
    <th>动物</th>
    <th>饮食</th>
    <th>爱好</th>
  </tr>
  <tr>
    <td>猫猫</td>
    <td>吃鱼</td>
    <td>睡觉</td>
  </tr>
</table>
```

​	表格合并单元格的步骤：

​		跨行合并，保留最上单元格，添加属性 rowspan="x"

​		跨列合并，保留最左单元格，添加属性 colspan="x"

​		x取值是数字，表示需要合并的单元格数量



## 表单\<form>

### 文本框、密码框、文本域

```html
<!-- text为文本框，placeholder属性为提示信息 -->
<input type="text" placeholder="提示信息">

<!-- password为密码框 -->
<input type="password" placeholder="提示信息">

<!-- textarea为文本域，一般禁用文本选择和拖拽 -->
<textarea cols="50" rows="10">默认提示文字</textarea>
<script>
  textarea {
  user-select: none; /* 禁用文本选择和拖拽 */
}
</script>
```

 

### 单选框、多选框、下拉菜单

```html
<!-- radio为单选控件，checked属性表示选中 -->
<input type="radio" name="gender" checked> 男
<input type="radio" name="gender"> 女

<!-- checkbox为多选控件 -->
<input type="checkbox" name="hobby" value="readbooks"/>
<input type="checkbox" name="hobby" value="playchess"/>

<!-- select 是下拉菜单 -->
<select name="sex">
	<option value="man">男</option>
	<option value="woman">女</option>
</select>
```

 

### disabled属性和label 标签 

​	**\<disabled>**

```html
<!-- disabled禁止向表单输入元素 -->
<input type="..." disabled >
```

​	**\<label>**

```html
<!-- 是标签内的内容都可点击聚焦 -->
<label><input type="radio"> 女</label>
```



### 上传文件 

​	添加 multiple 属性可以实现文件多选功能。

```html
<!-- enctype="multipart/form-data"指定上传方式为二进制文件 -->
<form  action="#" method="post" enctype="multipart/form-data">    
	<!-- 上传文件 -->
	<input type="file" name="file1"/>
	<br>
	<!-- type为hidden时，内容隐藏，隐藏的信息随提交而提交 -->
	<input type="hidden" name="act" value="click"/>
	<input type="submit" value="提交"/>
</form>
```



### 按钮\<button>

```html
<button type="">按钮</button>
```

| type属性值     | 说明                                   |
| -------------- | -------------------------------------- |
| submit（默认） | 提交按钮，点击后可以提交数据到后台     |
| reset          | 重置按钮，点击后将表单控件回复默认值   |
| button         | 普通按钮，默认没有功能，一般配合js使用 |

```html
<!-- form 表单区域,action="" 发送数据的地址 -->
<form action="">
  用户名：<input type="text">
  <br><br>
  密码：<input type="password">
  <br><br>

  <button type="submit">提交</button>
  <button type="reset">重置</button>
  <button type="button">普通按钮</button>
</form>
```



## Emmet 写法

​	html标签代码的简写方式

| 说明           | 标签结构                       | Emmet       |
| -------------- | ------------------------------ | ----------- |
| 类选择器       | \<div class="box">\</div>      | 标签名.类名 |
| id选择器       | \<div id="box">\</div>         | 标签名#id名 |
| 同级标签       | \<div>\</div>\<p>\</p>         | div+p       |
| 父子级标签     | \<div>\<p>\</p>\</div>         | div>p       |
| 多个相同的标签 | \<span>\</span>\<span>\</span> | span*2      |
