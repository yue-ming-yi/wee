## css总结

------

### 一、css基本信息

**CSS**是级联样式表（Cascading Style Sheets）的缩写。HTML 用于撰写页面的内容，而 CSS 将决定这些内容该如何在屏幕上呈现。网页的内容是由 HTML的元素构建的，这些元素如何呈现，涉及许多方面，如整个页面的布局，元素的位置、距离、颜色、大小、是否显示、是否浮动、透明度等等。万维网联盟 W3C（World Wide Web Consortium）于1997年推出 CSS 1.0（当前最新的版本是 CSS3），正式推动了内容（HTML）和表现（CSS）的分离。

### 二、css语法

一条CSS样式规则由两个主要的部分构成：选择器，以`{}`包裹的一条或多条声明:

![CSS-syntax](https://qige.io/web/brief-css/img/86e63894cd2a6e2f.jpg)

这条规则表明，页面中所有的一级标题都显示为蓝色，字体大小为12像数。
说明：

- 选择器是您需要改变样式的对象（上图的规则就一级标题生效）。
- 每条声明由一个属性和一个值组成。（无论是一条或多条声明，都需要用`{}`包裹，且声明用`;`分割）
- 属性（property）是您希望设置的样式属性（style attribute）。每个属性有一个值。属性和值被冒号分开。

#### 选择器

一个页面上的元素众多，选择器就用于在页面中找到/选择需要应用这个样式的对象。
除我们前示的元素选择器外，还有`id`和`class`选择器。其中`class`选择器使用非常普遍。

**id 选择器**

```
/* 注意：id选择器前有 # 号。 */
#sky{
  color: blue;
}
```

这条规则表明，找到页面上`id`为`sky`的那个元素让它呈现蓝色，如下所示的页面，**蓝色的天空**这几个字就将会是蓝色的。

```
<p id="sky">蓝色的天空</p>
<p id="forest">绿色的森林</p>
```

**class 选择器**

```
/* 注意：class选择器前有 . 号。 */
.center{
  text-align: center;
}
.large{
  font-size: 30px;
}
.red{
  color: red;
}
```

以上代码定义了三条规则，分别应用于页面上对应的元素，如只要页面上某元素的`class`为`red`，那么就让它呈现红色。
如下所示的页面：

```
<p class="center">我会居中显示的</p>
<p class="red">我是红色的</p>
<p class="center large red">我又红又大还居中</p>
<p class="red">我也可以是红的</p>
```

### 三、css样式

#### 外部样式表

新建如下内容的一个 HTML文件（后缀为.html)：

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <!-- 注意下面这个语句，将导入外部的 mycss.css 样式表文件 -->
  <link rel="stylesheet" type="text/css" href="mycss.css">
  <title>页面标题</title>
</head>
<body>
  <h1>我是有样式的</h1>
  <hr>
  <p class="haha">还是有点丑：)</p>
</body>
</html>
```

在同一目录新建一个样式表文件mycss.css（注意后缀名为css）如下：

```
body {
  background-color: linen;
  text-align: center;
}
h1 {
  color: red;
}
.haha {
  margin-top: 100px;
  color: chocolate;
  font-size: 50px;
}
```

#### 内部样式表

我们也可以将样式放在 HTML 文件中，这称为内部样式表。如：

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <!-- 注意下面这个语句，将导入外部的 mycss.css 样式表文件 -->
  <link rel="stylesheet" type="text/css" href="mycss.css">
  <title>页面标题</title>
  <style>
    body {
      background-color: linen;
      text-align: center;
    }
    h1 {
      color: red;
    }
    .haha {
      margin-top: 100px;
      color: chocolate;
      font-size: 50px;
    }
  </style>
</head>
<body>
  <h1>我是有样式的</h1>
  <hr>
  <p class="haha">还是有点丑：)</p>
</body>
</html>
```

#### 内联样式

所谓内联样式，就是直接把样式规则直接写到要应用的元素中，如：

```
<h3 style="color:green;">I am a heading</h3>
```

#### 级联的优先级

前面我们学习了三种使用样式的方式，如果某元素如`<p>`在外部、内部及内联样式中都被设置`color:red;`、`color:green;`、`color:blue;`，那么到底是什么颜色，也即到底哪个有效呢？
这就涉及样式的优先级问题，从高到低分别是：

1. 内联样式
2. 内部样式表或外部样式表
3. 浏览器缺省样式

### 四、css其他要素

#### 颜色

颜色在网页中的重要性不言而喻。
我们可以采用颜色名称也可以使用颜色RGB16进制值，来设定前景或背景的颜色。如：

```
<!-- 颜色名称 -->
<h3 style="background-color:Tomato;">Tomato</h3>
<h3 style="background-color:Orange;">Orange</h3>
<h3 style="background-color:DodgerBlue;">DodgerBlue</h3>
<h3 style="background-color:MediumSeaGreen;">MediumSeaGreen</h3>
<h3 style="background-color:Gray;">Gray</h3>
<h3 style="background-color:SlateBlue;">SlateBlue</h3>
<h3 style="background-color:Violet;">Violet</h3>
<h3 style="background-color:LightGray;">LightGray</h3>
<hr>
<!-- 颜色值，3个字节分别代表RGB（Red，Green，Blue）的0～255的值 -->
<h3 style="background-color:#ff0000;">#ff0000</h3>
<h3 style="background-color:#0000ff;">#0000ff</h3>
<h3 style="background-color:#3cb371;">#3cb371</h3>
<h3 style="background-color:#ee82ee;">#ee82ee</h3>
<h3 style="background-color:#ffa500;">#ffa500</h3>
<h3 style="background-color:#6a5acd;">#6a5acd</h3>
<!-- 文本颜色 -->
<h3 style="color:Tomato;">Hello World</h3>
<p style="color:DodgerBlue;">Lorem ipsum dolor sit, amet consectetur adipisicing elit.</p>
<p style="color:MediumSeaGreen;">Ad facilis est ducimus rem consectetur, corporis o
```

#### 尺寸

我们可以用 `height` 和 `width` 设定元素内容占据的尺寸。常见的尺寸单位有：像数 `px`，百分比 `%`等。
新建如下 HTML 文件：

```
<html>
  <head>
    <link rel="stylesheet" href="./mycss.css">
  </head>
  <body>
    <div class="example-1">
      这个元素高 200 pixels，占据全部宽度
    </div>
    <div class="example-2">
      这个元素宽200像素,高300像素
    </div>
  </body>
</html>
```

#### 对齐

对于**元素中的文本**，我们可以简单的设置`text-align`属性为`left, center, right`即可（显然缺省的是左对齐）

#### 盒子模型

盒子模型指的是一个 HTML 元素可以看作一个盒子。从内到外，这个盒子是由**内容 content, 内边距 padding, 边框 border, 外边距 margin**构成的，如下图所示：

![box](https://qige.io/web/brief-css/img/bd78f5d3be0673d6.jpg)

**说明：**

- Content 盒子的内容，如文本、图片等
- Padding 填充，也叫内边距，即内容和边框之间的区域
- Border 边框，默认不显示
- Margin 外边距，边框以外与其它元素的区域

#### 边框与边距

无论边框、内边距还是外边距，它们都有上下左右四个方向。

#### 定位

`position`属性用于对元素进行定位。该属性有以下一些值：

- static 静态
- relative 相对
- fixed 固定
- absolute 绝对

设置了元素的`position`属性后，我们才能使用`top, bottom, left, right`属性，否则定位无效。

##### static

设置为静态定位`position: static;`，这是元素的默认定位方式，也即你设置与否，元素都将按正常的页面布局进行。
即：按照元素在 HTML出现的先后顺序从上到下，从左到右进行元素的安排。

##### relative

设置为相对定位`position: relative;`，这将把元素相对于他的静态（正常）位置进行偏移

##### fixed

设置为固定定位`position: fixed;`，这将使得元素固定不动（即使你上下左右拖动浏览器的滚动条）。
此时元素固定的位置仍由`top, bottom, left, right`属性确定，但相对的是视口（viewport，就是浏览器的屏幕可见区域）

##### absolute

设置为绝对定位`position: absolute;`，将使元素相对于其**最近设置了定位属性（非static）的父元素**进行偏移。
如果该元素的所有父元素都没有设置定位属性，那么就相对于`<body>`这个父元素。

#### 溢出

当元素内容超过其指定的区域时，我们通过溢出`overflow`属性来处理这些溢出的部分。
溢出属性有一下几个值：

- visible 默认值，溢出部分不被裁剪，在区域外面显示
- hidden 裁剪溢出部分且不可见
- scroll 裁剪溢出部分，但提供上下和左右滚动条供显示
- auto 裁剪溢出部分，视情况提供滚动条

#### 浮动

在一个区域或容器内，我们可以设置`float`属性让某元素水平方向上向左或右进行移动，其周围的元素也会重新排列。一个浮动元素会尽量向左或向右移动，直到它的外边缘碰到包含框或另一个浮动框的边框为止。浮动元素之后的元素将围绕它。

#### 不透明度

我们可以用`opacity`对任何元素（不过常用于图片）设置不透明度。

#### 组合选择器

##### 后代选择器

以空格作为分隔，如：`.haha p` 代表在`div`元素内有`.haha`这种类的所有元素。

##### 子选择器

也称为直接后代选择器，以`>`作为分隔，如：`.haha > p` 代表在有`.haha`类的元素内的直接`<p>`元素。

#### 伪类和伪元素

伪类（pseudo-class）或伪元素（pseudo-element）用于定义元素的某种特定的状态或位置等。
比如我们可能有这样的需求：

- 鼠标移到某元素上变换背景颜色
- 超链接访问前后访问后样式不同
- 离开必须填写的输入框时出现红色的外框进行警示
- 保证段落的第一行加粗，其它正常
- ...

使用伪类/伪元素的语法如下：

```
/* 选择器后使用 : 号，再跟上某个伪类/伪元素 */
selector:pseudo-class/pseudo-element {
  property:value;
}
```

