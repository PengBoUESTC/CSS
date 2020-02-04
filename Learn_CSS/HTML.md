## HTML5

### Day1

+ 网页的基本组成

	- 图片 文字 连接 视频等

+ 什么是HTML

	- 超文本标记语言

+ 常用的浏览器

	- IE Edage 

	- chrome

	- opera

	- firfox

	- safari

+ web 标准的三大组成部分

	- HTML -- 结构

	- CSS  -- 表现

	- JavaScript -- 行为

#### HTML基础标签

+ 基本的骨架
~~~html
<!DOCTYPE html>
<!-- 声名 HTML 版本 -->
<html lang = "zh-CN">
<head>
	<!-- head 部分 -->
	<title> 网页的标题 </title>
	<meta charset="utf-8">
	<!-- 定义文件的编码规范 -->
</head>
<body>
	<!-- body 部分 -->
</body>
</html>
~~~

##### 标题标签

- ```<h1> - <h6>```

- 标题标签独占一行

##### 段落标签

- ```<p></p>```

- 块元素

##### 换行标签

- ```<br />```

- 单元素标签

##### 文本格式化标签

- ```<strong> 加粗标签 </strong> 语义更强```
	<strong name = "strong"> 加粗 </strong>

- ```<b> 加粗 </b>```

- ```<em> 倾斜 </em> 语义更强```
	<em> 倾斜 </em>

- ```<i> 倾斜 </i>```

- ```<del> 删除线 </del> 语义更强```
	<del> 删除线 </del>

- ```<s> 删除 </s>```

- ```<ins> 下划线 </ins>  语义更强```
	<ins> 下划线 </ins>

- ```<u> 下划线 </u>```

##### div 标签

- 无语义的块元素标签

##### span 标签
	
- 无语义的 行内元素标签，**无宽高属，靠内容撑开**

#### 图像标签

- ```<img src="图片路径" alt = "替换文本" title = "提示文本">```
<img name= "image" src="./images/logo.png" alt = "logo图片" title = "logo 图片" height="80px">

- 行内块元素, **不独占一行，但是拥有 height 属性与 width 属性**

#### 超链接标签

+ 应用及属性

	- ```<a href="跳转路径" target= "打开网页方式">连接文本</a>```
	<a href="http://www.baidu.com" target="_blank">跳转</a>

	- 通过设置 href 跳转外部连接与内部连接

	- 通过设置元素的 **id** 属性，设置锚点，并通过a 标签跳转到指定锚点, 
	<a href="#strong">跳转到加粗</a>

	- 下载连接： 当 href 里面的地址是一个文件或者压缩包（exe, zip），会下载这个文件
	<a href="./images/logo.7z">下载文件</a>

	- target : \_blank、 \_self

#### 特殊字符
	
+ 用于显示特殊的字符，如空格 > < 等

	- < : &lt, > : &gt

	- 空格 : &nbsp

#### 表格标签

- 表格的作用

	- 显示或者展示数据

	- 布局

+ 标签
<table align= "cemter">
	<thead>
			<tr>
				<th> table 标签 </th>
				<th> thead 标签 </th>
				<th> tbody 标签 </th>
				<th> th 标签 </th>
				<th> tr 标签 </th>
				<th> td 标签</th>
			</tr>
	</thead>
	<tbody>
			<tr>
				<td>用于定义一个表格</td>
				<td>用于表示表格的头部区域</td>
				<td>用于表示表格的单元格部分</td>
				<td>table head用于定义表头</td>
				<td>table row 用于定义一行</td>
				<td>table data 用于定义单元格</td>
			</tr>
	</tbody>
</table>

+ 相关属性
<table border="3">
	<thead>
			<tr>
				<th align="center"> 属性名 </th>
				<th align="center"> 属性值 </th>
				<th align="center"> 作用标签</th>
				<th align="center"> 效果 </th>
			</tr>
	</thead>
	<tbody>
			<tr align="center">
				<td> align </td>
				<td> left、 center、 right</td>
				<td> table th td </td>
				<td> 表格的对齐方式 </td>
			</tr>
			<tr align="center">
				<td> border </td>
				<td> 1、""</td>
				<td> table th td</td>
				<td> 为元素添加边框 </td>
			</tr>
			<tr align="center">
				<td> cellpadding </td>
				<td> 像素值 </td>
				<td> table </td>
				<td> 文字与单元格边框的距离 </td>
			</tr>
			<tr align="center">
				<td> cellspacing </td>
				<td> 像素值 </td>
				<td></td>
				<td>单元格之间的距离 </td>
			</tr>
			<tr align="center">
				<td> width height</td>
				<td> 像素值或百分比 </td>
				<td></td>
				<td> 表格的宽度 </td>
			</tr>
			<tr align="center">
				<td> <p lineheight = "100%">图片</p> </td>
				<td> <img src="./images/logo.png" width="50px" title="图片" alt="图片"></td>
				<td></td>
				<td><p lineheight = "100%"><a href="#image" >连接</a></p></td>
			</tr>
	</tbody>
</table>

+ 合并单元格
	
	- <font color = "red">将属性写在**目标单元格**上，跨行时为最上单元格跨列时为最左单元格</font>

	- 跨行合并 rowspan
	<table border= '5px'>
		<tr height= "30px">
			<td></td>
			<td colspan="2">删除这行多余 n-1 列</td>
		</tr>
		<tr height = "30px">
			<td rowspan="2">删除这列 n-1 行一个 td </td>
			<td></td>
			<td></td>
		</tr>
		<tr height = "30px">
			<td></td>
			<td></td>
		</tr>
	</table>

	- 跨列合并 colspan

	- **合并完毕单元需要删除多余的单元格**

#### <font color = "red">列表标签</font>

+ **用于布局**

+ 种类

	- 无序列表 ： ul li (ul 中只能放 li)

	- 有序列表 ： ol li

	- 自定i列表 ： 用于对术语或者名词进行描述
	~~~html
	<dl>
		<dt> 名词1 </dt>
		<dd> 解释1 </dd>
		<dd> 解释2 </dd>
		<dt> 关注我们 </dt>
		<dd> 新浪微博 </dd>
		<dd> 官方微信 </dd>
	</dl>
	~~~

#### 表单标签

+ 应用

	- 收集用户信息

+ 组成

	- 表单域 ： 包含表单元素的区域，确定数据提交的部分 ```<form></form>```

	- 表单控件/表单元素 ==> <font color="red">行内块元素</font>
	标签 | 作用 | 应用 | 说明
	- | - | - | - | 
	input| 数据输入（单标签）| 提示信息： ```<input type="" name="">``` | <a href="#type"> type 选择</a>
	select|选择给定值|提示信息： <select><option></option></select>|至少包含一个option;selected="selected"
	textarea| 多行文本输入| <textarea></textarea>| 留言板、评论; cols rows 属性

	- input 标签中 type 的值
	<table name = "type">
		<thead align="left">
			<tr>
				<th> 值 </th>
				<th> 描述 </th>
			</tr>
		</thead>
		<tbody align="left">
			<tr>
				<td>button</td>
				<td>定义可点击的普通按钮，用于 JS 启动脚本</td>
			</tr>
			<tr>
				<td>checkbox</td>
				<td>name 属性设置为相同，定义复选框</td>
			</tr>
			<tr>
				<td>file </td>
				<td>定义输入字段和浏览按钮，供文件上传</td>
			</tr>
			<tr>
				<td>hidden</td>
				<td>定义隐藏的输入字段</td>
			</tr>
			<tr>
				<td>image</td>
				<td>定义图像形式的按钮</td>
			</tr>
			<tr>
			<td>password</td>
			<td>密码形式的输入</td>
			</tr>
			<tr>
				<td>radio</td>
				<td> name 属性设置为相同，定义单选按钮</td>
			</tr>
			<tr>
				<td>reset</td>
				<td>定义重置按钮，表单中的数据重置到默认值</td>
			</tr>
			<tr>
				<td>submit</td>
				<td>提交按钮</td>
			</tr>
			<tr>
				<td>text</td>
				<td>定义**单行**的输入字段</td>
			</tr>
		</tbody>
	</table>

	- 提示信息

+ **表单元素的 neme 属性，用于区别不同的表单元素**

+ **value 属性， 提交到后台的数据**

+ **checked 属性，用于给 radio checkbox 设置默认值**

+ **maxlength 用于限制最大输入长度**

+ <font color = "red">label ： 标注标签</font>
~~~html
<label for = "id_value">name : </label><input type="checkbox" name="duoxuan" id = "id_value">
~~~

+ 代码
~~~html
<form action = "" method = "" name = "">
	name : <input type="text" name="name">
</form>
~~~
~~~html
<select>
	<option selected = "selected">1</option>
	<option>2</option>
	<option>3</option>
</select>
~~~

#### HTML5 新增标签

+ head nav artical aside footer section

##### 视频标签 video

+ 支持的视频格式

	- MP4:浏览器兼容性最好

	- webm

	- ogg

+ 应用
~~~html
<video controls>
<!-- 可通过source 标签引入多张视频格式用于兼容性的优化 -->
	<source src="xx.mp4" type="">
	<source src="xxx.ogg" type="">
	<source src="xxx.webm" type="">
</video>
~~~

+ 相关属性
属性 | 值| 说明
-|-|-
controls | controls | 视频的控制按钮
autoplay | autoplay | 打开自动播放，谷歌禁止自动播放需要额外添加 muted 属性
muted | muted| 静音播放
loop | loop | 循环播放
preload  | auto 、 none | 是否预加载视频，若有autoplay 则忽略该属性
poster | ulr | 界面图片

##### 音频标签 audio

+ 格式

	- mp3 : 兼容性最好

	- wav

	- ogg

+ 应用
~~~html
<audio>
	<!-- 与video 类似的解决兼容性问题 -->
	<source src="xx.mp3" type="">
</audio>
~~~

+ 属性
属性 | 值| 说明
-|-|-
controls | controls | 
autoplay | autoplay | 
loop | loop | 

##### 表单

+ **input 新增的 type 类型**
type | 说明
-|-
number | 数字
color | 颜色
search | 搜索框
email | 
tel | 手机号
url | 
... | 

+ 表单新增属性
属性 | 值 | 说明
-|-|-
required | required | 不能为空的元素
autofocus | autofocus | 自动获取焦点
placeholder | strig 文本 | 添加默认内容
autotemplate | on 、 off | 是否记录提交成功的内容,默认为 on 