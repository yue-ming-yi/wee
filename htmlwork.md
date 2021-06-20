## HTML总结

------

### 一、HTML的定义和基本信息

**HTML**是<u>超文本标记语言</u>（HyperText Markup Language）的缩写。我们用 HTML 来构建 Web 页面即所谓的网页。**HTML** 是构成 Web 世界的一砖一瓦。它定义了网页内容的含义和结构。除 HTML 以外的其它技术则通常用来描述一个网页的表现与展示效果（如 CSS），或功能与行为（如 JavaScript）。**HTML** 不是一门编程语言，而是一种用于**定义内容结构的标记语言**。在浏览器中看到的任何网页背后都是一个 **HTML** 文档，只要在网页上点击鼠标右键->查看源代码（用控制台工具也可）就可看到。

### 二 、HTML 文档结构分析

#### HTML元素（elements）

HTML 使用"标记"（markup）来注明文本、图片和其他内容，以便于在浏览器中显示。HTML 标记包含一些规定的"元素"如 <head>，<title>，<body>，<header>，<footer>，<article>，<section>，<p>，<div>，<span>，<img>，<aside>，<audio>，<canvas>，<datalist>，<details>，<embed>，<nav>，<output>，<progress>，<video> 等等。检查我们刚创建的 HTML 文档你会发现，整个 HTML 就由一个个元素组成（可以嵌套），而元素则一般由一对标签（tag）构成。如图所示用来展示段落的元素：

![element](https://qige.io/web/brief-html/img/f63738cc51ebfa14.png)

1. 开始标签（Opening tag）：包含元素的名称（本例为 p），被左、右角括号所包围。表示元素从这里开始或者开始起作用 —— 在本例中即段落由此开始。
2. 结束标签（Closing tag）：与开始标签相似，只是其在元素名之前包含了一个斜杠。这表示着元素的结尾 —— 在本例中即段落在此结束。初学者常常会犯忘记包含结束标签的错误，这可能会产生一些奇怪的结果。
3. 内容（Content）：元素的内容，本例中就是所输入的文本本身。
4. 元素（Element）：开始标签、结束标签与内容相结合，便是一个完整的元素。

#### 解析 HTML 文档

1. `<!DOCTYPE html>`: 声明文档类型。出于历史原因需要，现在可有可无。
2. `<html></html>`: `<html>`元素。这个元素包裹了整个完整的页面，是一个根元素，**其它元素都嵌套到其中**。
3. `<head></head>`: `<head>`元素。 这个元素是一个容器，它包含了所有你想包含在HTML页面中但不想在HTML页面中显示的内容。这些内容包括你想在搜索结果中出现的关键字和页面描述，CSS样式，字符集声明等等。
4. `<meta charset="utf-8">`: 这个元素设置文档使用utf-8字符集编码，utf-8字符集包含了人类大部分的文字。基本上他能识别你放上去的所有文本内容。
5. `<link rel="shortcut icon" href="favicon.ico" type="image/x-icon">`: 指定页面的图标，出现在浏览器标签上。
6. `<title></title>`: 设置页面标题，出现在浏览器标签上，当你标记/收藏页面时它可用来描述页面。
7. `<body></body>`: `<body>`元素。 包含你能在页面看到的所有内容，包括文本，图片，音频，游戏等等。

### 三 、HTML 文档相关说明

#### 注释

如同大部分的编程语言一样，在 HTML 中有一种可用的机制来在代码中书写注释 。注释是被浏览器忽略的，而且是对用户不可见的，它们的目的是允许你描述你的代码是如何工作的和不同部分的代码做了什么等等。为了将一段 HTML 中的内容置为注释，你需要将其用特殊的记号`<!--`和`-->`包括起来， 比如：

```
<p>我在这！</p>
<!-- <p>我在注释内！浏览器将忽略我</p> -->
```

#### 空元素

一般来说，元素都拥有**开始标签，内容，结束标签**。但有一些元素只有一个开始标签，通常用来在此元素所在位置插入/嵌入一些东西，如`<br>, <hr>, <input>, <img>, <a>`等等。我们称其为空元素，如下：

```
<!-- 换行 -->
<p>我可以<br>换行</p> 
<!-- 水平分割线 -->
<hr>
<!-- 输入框 -->
<input>
```

#### 元素的属性

元素是可以有相关属性的。属性包含元素的额外信息，这些信息不会在浏览器中显示出来。一个属性必须包含如下内容：

1. 一个空格，在属性和元素名称之间。(如果已经有一个或多个属性，就与前一个属性之间有一个空格。)
2. 属性名称，后面跟着一个 = 号。
3. 一个属性值，由一对引号 "" 引起来。

### 四、其他HTML页面元素

#### 标题（heading）

HTML 提供了从大到小6级标题，分别是：`<h1> ~ <h6>`，如下所示：

```
<h1>This is heading 1</h1>
<p>This is some text.</p>
<hr>
<h2>This is heading 2</h2>
<p>This is some other text.</p>
<hr>
```

在页面中，标题非常重要：

1. 搜索引擎用标题来索引页面的内容
2. 用户也习惯以标题进行主要内容浏览，以决定是否查看该页面

#### 文本格式

我们需要知道的文本格式标签如下：

```
<p>You can use the mark tag to <mark>highlight</mark> text.</p>
<p><del>This line of text is meant to be treated as deleted text.</del></p>
<p><s>This line of text is meant to be treated as no longer accurate.</s></p>
<p><ins>This line of text is meant to be treated as an addition to the document.</ins></p>
<p><u>This line of text will render as underlined</u></p>
<p><small>This line of text is meant to be treated as fine print.</small></p>
<p><strong>This line rendered as bold text.</strong></p>
<p><em>This line rendered as italicized text.</em></p>
```

**注：** 除本节介绍的这些标签可用于文本的格式外，其它标签都不建议用来进行格式的设置，如：`<font><big><center>`等标签皆为不推荐使用的。HTML 是用来表现页面内容而不是对页面进行修饰的。

#### 超链接 a

##### 超链接语法

```
<a href="https://www.baidu.com/" target="_blank">百度一下</a>
```

说明：

1. `href`即为要跳转去的地址 URL（Uniform Resorce Locator)
2. `target`属性为`_blank`表示在新的页面打开超链接（默认是在当前页面打开即`_self`）
3. 超链接标签包含的内容（当前为文字"百度一下"）即为显示在页面上供用户点击的

##### 锚点

锚点，也称为书签，用于标记页面的某个元素或位置。通过锚点，我们可以轻易的在长页面内实现跳转。先使用`id`属性生成某元素的锚点，然后再使用超链接指向该锚点即可。

#### 图片及文件路径 img

##### 图片

在页面插入一张图片如下：

```
<img src="https://mdbootstrap.com/img/logo/mdb192x192.jpg" alt="MDB Logo" width="200" height="200">
```

说明：

1. `src`属性为要显示图片文件的位置 URL，即图片文件的路径
2. `alt`属性当获取图片出现问题时显示的文字（占位符）
3. 可为图片指定高宽度，但不建议（可能导致图片变形）

##### 文件路径

为获取图片文件，我们需要指定该文件位于何处，这称为文件路径。文件路径有相对路径和绝对路径两种。

| 例子                               | 解释                                   |
| ---------------------------------- | -------------------------------------- |
| `<img src="picture.jpg">`          | 该图片文件与当前文档在同一目录中       |
| `<img src="./images/picture.jpg">` | 该图片文件在当前目录下的`images`目录中 |
| `<img src="../picture.jpg">`       | 该图片文件在上一级目录中               |

#### 表格 Table

页面的内容需要用表格来进行呈现。我们使用`<table>`等标签即可：

```
<table>
    <tr>
      <th>Firstname</th>
      <th>Lastname</th>
      <th>Age</th>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Smith</td>
      <td>50</td>
    </tr>
    <tr>
      <td>Eve</td>
      <td>Jackson</td>
      <td>94</td>
    </tr>
  </table>
```

代码中，`<tr>`表示行, `<td>`表示行中的单元, `<th>`是表头的单元（将会加粗显示）

####  列表 List

##### 无序列表

```
<ul>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
```

无序列表使用`<ul>`标签，默认使用**实心圆点**作为每项的标志，其它的标志可以是空心圆`circle`，实心方块`square`以及不出现标志。

```
<ul type="square">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
```

##### 有序列表

```
<ol>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>
```

有序列表使用`<ol>`标签，默认使用**数字**作为每项的标志，其它的标志可以是大写字母`A`，小写字母`a`，罗马字母`i`等。

```
<ol type="a">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>
```

#### 表单 Form

当网站需要获取我们的一些信息如：用户名、密码、选择买什么、买多少、提出意见等等时，我们就需要使用表单（form）来让用户填写或选择。

#### 其它

HTML 的元素可以以称为**区块** 或 **内联**的方式进行显示。

##### 区块元素

区块元素在浏览器显示时，通常会以**新行**来开始（和结束）。如：`<h1>, <pre>, <ul>, <table>，<`div> 等。

```
<h2>区块元素</h2>
<div>Hello</div>
<div>World</div>
<p>单独一行</p>
```

##### 内联元素

内联元素相反，他们总是一个接一个进行显示，不会新起一行。如： `<span>, <input>, <td>, <a>, <img>`等。

```
<h3>下面的元素将在一行中显示</h3>
<span>姓名：</span>
<input name="username">
<span>哈哈哈</span>
<a href="https://google.com/">Google</a>
<img src="https://mdbootstrap.com/img/logo/mdb192x192.jpg">
```

##### 预设格式

如果想在网页中展示一首诗或一些特别格式的文本，那么使用`pre`标签。

##### 特殊字符

特殊字符可参考[ISO-8859-1 字符实体手册](https://www.runoob.com/tags/ref-entities.html)

