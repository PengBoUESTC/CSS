## CSS 基础

### Day2

#### CSS 基础

+ emmet 使用

	- 快速生成代码
	快捷生成代码 | 方式
	- | -
	按键补全代码 | tab
	生成 对应类名的div | .class_name 
	生成兄弟标签 | ul+div
	生成子标签 | ul>li
	生成对应 id 名的 div  | \#ID_name 
	符号快速生成多行代码 | li\*5
	内部添加默认内容 | div{默认内容}\*5
	符号生成自增序号 | li{$}\*5

	- 格式化代码: <font color = "red">在 emmet.include json 文件中添加字段，实现保存时格式化代码</font>
	~~~json
	"editor.formatOnType":true,
	"editor.formateOnSave": true
	~~~

+ HTML 修改样式繁琐

+ CSS 层叠样式表 --> 标记性语言

+ CSS 使 HTML 能够专注于页面结构，实现结构与样式的分离

+ CSS 语法规范

	- 选择器

	- 样式, 不同属性之间使用 ";" 分割
	~~~css
	p {
		color: red;
	}
	~~~

+ 三种方式

	- 内部样式表: 理论上可以放在任意位置，但是习惯上放在 head 中
	~~~html
	<style type="text/css">
		<!-- 添加样式 -->
	</style>
	~~~

	- 内联样式表： 在标签内部添加属性, <font color="red">书写方便，权重高</font>
	~~~html
	<p style = "color: red;"></p>
	~~~

	- 外部样式表： ```<link rel="stylesheet" type="text/css" href="">```

#### CSS选择器

+ 选择器作用: 选择特定的标签

##### 基础选择器

+ 标签选择器: 根据元素标签选择
~~~css
div {
	color: red;
}

p {
	line-height: 100%;	
}
~~~

+ 通配符选择器
~~~css
* {
	margin: 0;
	padding: 0;
}
~~~

+ 类选择器: 类名可以使用短横线分割；多类名的使用

	- 例子
	~~~css
	.class_name {
		width: 100px;
	}
	~~~

	- 多类名的应用

+ ID选择器： ID 是唯一的，因此不能够多次被调用
~~~css
#id {
	display: block;
}
~~~

+ <font color="red">属性选择器</font>
~~~css
input[value] {
	color : red;
	<!-- input 标签中定义了 value 属性的元素 -->
}

imput[type=password] {
	<!-- 根据属性及属性值选择元素 -->
}

<!-- 结合正则表达选取元素 -->
input[class^=icon] {
	<!-- 选取类名以 icon 开头的元素 -->
}

input[class$=data] {
	<!-- 选择以 data  结尾的元素 -->
}

input[class* = val] {
	<!-- 包含 val 的元素 -->
}
~~~

##### 复合选择器

+ 并集选择器
~~~css
ul, ol {
	color: red;
}
~~~

+ 伪类选择器: 为元素添加一些特殊效果

	- 链接伪类: <font color="red">顺序不能变</font>
	~~~css
	<!-- a:link  未访问过的链接状态-->
	<!-- a:visited 已访问过的链接状态-->
	a:hover {
		color: red
	}
	<!-- a:active 点击时的状态-->
	~~~

	- focus 伪类选择器: <font color="red">选取获得焦点的表单元素</font>
	~~~css
	input:focus {
		background-color: red;
	}
	~~~

	- 结构伪类 : first-child last-child nth-child(n), first-of-type last-of-type nth-of-type
	~~~css
	<!-- child 会把所有的元素都排列序号，选择器从后往前执行 -->
	<!-- type 会把指定的元素排列序号，选择器从前往后执行 -->
		li:first-child {}
		li:nth-child(2n) {}
		li:nth-child(2n+1){}
		li:nth-child(odd){}
	~~~


+ 伪元素选择器

	- <font color="red">通过 CSS 创建一个标签</font> 简化HTML 结构

	- <font color="red">通过与定位结合实现字体图标的添加</font>

	- ::before

	- ::after

	- 应用 : **清除浮动，添加效果**
	~~~css
	li:hover::after{
		<!-- 添加属性 -->
	}
	~~~

+ 子选择器: <font color="red">只选择孩子一级</font>
~~~css
ul>li {
	color: red;
}
~~~

+ 后代选择器： <font color="red"> 选择父级元素所有的符合条件的子孙标签 </font>
~~~css
ul li {
	color: red;
}
~~~

+ <a href="#weight">选择器权重</a>

#### CSS属性

+ 字体相关属性（font）

	- 字体类型: 按照书写先后顺序作为优先级顺序
	~~~css
	.nav {
		font-family: "微软雅黑";
	}
	~~~

	- 字体大小： **标题标签需要单独指定字体大小，不会继承**
	~~~css
	p {
		font-size: 14px;
	}
	~~~

	- 字体粗细
	~~~css
	h1 {
		font-weight: normal(400)| bold(700)| lighter;
	}
	~~~

	- 字体样式
	~~~css
	p {
		font-style: normal|italic;
	}
	~~~

	- 复合属性: 其中 font-size 与 font-family 属性不能够省略
	~~~css
	p {
		font: font-style font-weight font-size/line-height font-family;
		font: italic bold 16px/18px "Microsoft YaHei";
	}
	~~~

+ 文本属性

	- 颜色: 预定义的颜 red、green; 或者16进制的数据 #ccc; **rgba() 参数**
	~~~css
	p {
		color: pink;
	}
	~~~

	- 对齐文本
	~~~css
	p {
		text-align: left| center | right;
	}
	~~~

	- 装饰文本: 下划线 删除线 上划线, <font color="red">常用于取消 **a** 标签的默认样式</font>
	~~~css
	p {
		text-decoration: none| underline| overline| line-through;
	}
	~~~

	- 文本缩进: 文本**首行**缩进, <font color = "red">常用单位 em , em为相对当前字的大小确定的</font>
	~~~css
	p {
		text-indent: 2em;
	}
	~~~

	- 行间距： <font color="red">常用与文本的垂直居中</font>
	~~~css
	span {
		line-height: 100%;
	}
	~~~

+ 背景

	- 背景颜色： background-color

	- 背景图片: background-image, 常用于网站 logo , 装饰性图片， 超大图片
	~~~css
	div {
		background-image: url(images/img1.png);
	}
	~~~

	- 背景平铺: background-repeat
	~~~css
	div {
		background-image: url();
		background-repeat: repeat| repeat-x | repeat-y | no-repeat
	}
	~~~

	- <font color="red">背景位置: background-position: x y;</font>
	~~~css
	div {
		background-position: x y;
		<!-- 方位： left center right top bottom -->
	}
	~~~

	- 背景固定： background-attachment <font color="red">视差滚动</font>
	~~~css
	<!-- 默认值为 scroll 随页面滚动，fixed 不随页面滚动 -->
	~~~

	- 背景的复合写法

	- <font color="red">背景颜色的半透明 rgba</font>


#### 元素的显示模式

+ 元素显示模式的转换

	- 通过属性 dislay 
	~~~css
	a {
		display: inline-block;
	}
	~~~

+ 块元素

	- h1-h6 p div ul ol li 等

	- 特点

	1. 独占一行

	2. 可以设置宽高，margin padding

	3. 宽度默认时 父级元素的宽度 100%

	4. 内部可以放块元素 或 行内元素

	- 注意: <font color="red">文字类型的元素里不能使用块元素</font>

	1. p 标签内部不能使用div

	2. h1-h6 同样不能放 块元素

+ 行内元素

	- 特点

	1. 一行剋放多个行内元素

	2. <font color="red">宽高设置是无效的</font>

	3. <font color="red">宽度靠内部内容撑开</font>

	4. 内部只能放文本或者其他行内元素

+ 行内块元素

	- img input td 等

	- 特点

	1. 不独占一行

	2. 默认宽度为内容的宽度

	3. 可以设置宽高 margin padding 

#### CSS三大特性

##### 层叠性

+ 同一标签不同样式的作用

##### 继承性

+ 父标签样式对子标签样式的影响， 与文本相关的属性

+ 颜色 color, font

+ <font color="red">行高的继承</font>

	- line-height : 可以加单位，也可以不加单位，不加单位为 <font color="red">字体大小的倍数</font>

	- **<font color="red">注意行高继承，而字体大小层叠的情况，由于行高可通过倍数进行表示，因此此时行高的实际像素是不同的</font>**

##### <span name = "weight">优先级</span>

+ 相同标签不同的声明方式带来的最样式结果

+ 
选择器 | 权重
- | -
**继承或者 \*** | 0 0 0 0
标签选择器 | 0 0 0 1
类选择器，伪类选择器，属性选择器 | 0 0 1 0
id 选择器 | 0 1 0 0
行内样式 | 1 0 0 0 
!important | ∞

+ 权重的叠加

#### 盒子模型

<img src="./images/box-model.gif" height="200px" style="float: left">

+ <font color="red">box-sizing 属性更改 盒子模型</font>

+ <font color="red">默认情况下 盒子的 weight 与 height 属性指定的是 content 的大小</font>

+ <font color="red">当元素没有 width 属性时，padding 不会撑开盒子</font>

+ margin：外边距，控制盒子与盒子之间的间距

	- **用于块元素的水平居中， 该块元素必须设置 width**

	- <font color="yellow">**为块元素添加 text-align 属性可以使其内部的行内/行内块元素水平居中**</font>

	- <font color="red">塌陷，当垂直方向上的元素的 margin 父级元素会发生塌陷</font>

	- **父子元素之间通过添加 border、 padding、 overflow: hidden、 浮动、 固定、 绝对定位、 防止塌陷**

+ border：盒子边框

	- 会影响 盒子的大小

	- border: border-width border-style border-color
	属性 | 参数
	- | -
	border-width| xxpx
	border-style| solid 、 dashed、dotted
	border-color| rgba 、# 、关键字

	- boder-top border-bottom border-right border-left

	- <font color="red">表格的边框  border-collapse: collapse</font>

+ padding： 盒子内边距，用于分离边框与内容

	- 会影响盒子的大小

+ content：内容

+ 两种盒子模型

	- box-sizing 属性控制盒子的模型

+ box-sadow： 盒子阴影

	- box-shadow: 水平位移 垂直位移 模糊范围 阴影尺寸 阴影颜色 inset/outset

+ text-shadow: 文字阴影

#### 浮动

+ 网页布局方式： 浮动 display: float

	- **元素脱离标准流**, <font color="red">但是不会覆盖内容</font>

	- **在一行内显示**

	- **浮动的元素具有行内块元素的特性**，<font color="red"> 可以省略 display: inline-block/block 属性</font>

+ 在按照标准流排布的父级元素中放置 float 元素

+ <font color="red"> 块级元素纵向排布需要使用标准流， 水平方向需要使用浮动</font>

##### 清除浮动

+ <font color="red">清除浮动</font>： **父级元素高度不定，由于子元素浮动会脱标，因此父元素高度会变为0**

	- 额外标签法: 在浮动的元素之后添加 属性为 clear: both 的**块元素标签**，撑开父级盒子高度
	~~~css
	.clear {
		clear: both;
		<!-- 添加该属性的元素将浮动元素作为普通元素 -->
	}
	~~~

	- 父级元素添加 overflow: hidden | auto | scroll

	- <font color="red">父级元素添加 after 伪元素</font>
	~~~css
	.clearfix:after {
		content: "";
		display: block;
		height: 0;
		clear: both;
		visibility: hidden;
	}
	.clearfix {
		\*zoom: 1
	}
	~~~

	- <font color="red">父级元素添加 after before 双伪元素</font>: table 为一个块元素，高度有内容决定，content为空，因此高度为0，即变相的引入一个高度为0 的块元素
	~~~css
	.clearfix:after, .clearfix:before {
		content: "";
		display: table;
	}
	.clearfix:after {
		clear: both;
	}
	.clearfix {
		\*zoom: 1;
	}
	~~~

#### 定位

+ (position)定位方式+ 边偏移（top bottom left right）

+ 
定位方式 | 效果 | 说明
-|-|-
static | 标准流 | 
relative | 相对定位 | 相对自身位置进行偏移，**不会脱离标准流**
absolute | 绝对定位 | 相对**最近一级使用定位的父级**元素定位，否则以浏览器为标准
fixed | 固定定位 | 相对于窗口定位,脱离标准流
sticky | 粘性定位 | 不脱标，相对窗口定位，需要边偏移的至少一个参数

##### 定位的应用

+ <font color="red"> **子绝父相** </font>： 子元素使用绝对定位，父级元素使用 相对定位

+ **fixed 定位到版心的右侧： left: 50%; margin-left: 版心宽度/2；**

+ sticky ：当元素相对窗口达到边偏移设定值时表现为固定定位

+ 定位的叠放顺序： z-index 属性

+ 定位实现垂直居中: 绝对定位的元素不能通过 margin: 0 auto; 实现居中
~~~css
.box {
	position: absolute;
	top: 50%;
	margin-top: -height/2;
}
~~~

+ **注意**

	- <font color="red"> 为行内元素添加绝对定位或固定定位后，可直接设定 width 于 height 属性，无需在设置 display 属性</font>

	- <font color="red"> 块元素设置 绝对/固定 定位后的默认大小靠内容撑开</font>

	- <font color="red"> 脱标元素不会触发外边距塌陷的 </font>

#### 元素的隐藏与显示

+ display

	- display: none 隐藏元素，并不占有原来的位置

+ visibility

	- visibility: inherit | hidden | visible | collapse: 隐藏元素，仍保留原有位置

+ overflow

	- overflow: hidden | scroll 多出盒子的部分内容隐藏/滚动条


#### CSS 高级技巧

##### 精灵图(sprites)

+ **减少前端对后台的请求次数**，将大多数背景图片制作在一张背景透明的精灵图中，并通过 background-position 进行控制选择

##### 字体图标

+ 精灵图更改不方便，将一些图标做成字体使用，减少图片的请求与使用; **放大不失真，轻量，灵活，兼容性好**，<font color="red">用于制作简单的背景小图标</font>

+ 使用方式
	
	- 制作/下载字体图标

	- 通过 @font-face 定义字体

	- 为使用了字体图标的标签添加定义的字体

+ 通过导入 ```selection.json``` 文件导入已选择的字体图标，进行字体图标的追加

##### CSS 三角

+ 通过控制边框的**颜色与宽度**制作三角形

#### 用户界面样式

+ 鼠标样式
	
参数| 样式
-|-
default | 默认小白
pointer | 小手
move | 拖动
text | 光标
not-allowed | 禁止

+ 表单轮廓与防止拖拽文本域

	- outline : none;

	- resize: none;

+ **vertical-align**: 用于实现图片与文字的垂直对齐，<font color="red">只针对行内元素或者行内块元素起效，为img、表单元素 添加</font>
参数|说明
-|-
baseline|文字基线对齐
top|顶部对齐
middle|居中对齐
bottom|底部对齐

	- img 默认是基线对齐，因此会与边框底部有小缝隙，该属性可消除图片与区域之间的空白缝隙

+ <font color="red"> 溢出文本省略号显示 </font>

	- 单行文本
	~~~css
	{
		white-space: nowrap
		overflow: hidden;
		text-overflow:ellipsis;
	}
	~~~

	- 多行文本

+ <font color="red">margin 负值的应用</font>

	- 控制相邻盒子边框的重叠
	~~~css
	li {
		border: 1px solid red;
		margin-left: -1px;
	}
	~~~

	- 添加 position: relative 属性，防止边框被遮挡
	~~~css
	li:hover {
		position: relative;
		z-index: 1;
		border: 1px solid blue;
	}
	~~~

#### CSS3新特性

+ 新书幸福 ```filter ： blur(15px)``` : 用于图像的处理 blur 为模糊处理

+ ```calc(100% -30px)``` : 哦那个过计算得到需要的值

##### 过度

+ transition