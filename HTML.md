# 前端代码规范

## HTML部分

### 使用正确的文档类型

请始终在文档的首行声明文档类型：
```html
<!DOCTYPE html>
```

### 空行和缩进

不要毫无理由地增加空行。  
为了提高可读性，可以增加空行来分隔大型或逻辑代码块。  
使用四个空格的缩进。请勿使用 TAB。

### 元数据

在文档中需定义语言和字符编码：

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>HTML5 Syntax and Coding Style</title>
</head>
```

meta标签描述有关页面的信息，放在页面的head部分，可以使搜索引擎更好的识别。
```html
<meta name="author" content="John Doe">
<meta name="copyright" content="&copy; 2004-2017 Starnet Corp.">
<meta name="keywords" content="html,html5,codestyle">
<meta name="description" content="the description about this page">
<meta name="date" content="2017-06-22T03:25:00+00:00">
```
IE 支持通过特定的 `<meta>` 标签来确定绘制当前页面所应该采用的 IE 版本。除非有强烈的特殊需求，否则最好是设置为 edge mode，从而通知 IE 采用其所支持的最新的模式。
```html
<meta http-equiv="X-UA-Compatible" content="IE=Edge">
```

### HTML 注释

短注释应该在单行中书写，并在 `<!--` 之后增加一个空格：

```html
<!-- This is a comment -->
```

长注释和跨越多行的注释，应该通过 <!-- 和 --> 在独立的行中书写：

```html
<!--
    This is a long comment example. This is a long comment example.
    This is a long comment example. This is a long comment example.
-->
```

长注释缩进四个空格的话更容易阅读。

### 使用小写标签名

Bad:
```html
<SECTION>
    <p>This is a paragraph.</p>
</SECTION>
```

Very Bad:
```html
<Section>
    <p>This is a paragraph.</p>
</SECTION>
```

Good:
```html
<section>
    <p>This is a paragraph.</p>
</section>
```

### 尽量使用语义化的标签
* `<header>`  定义 section 或 page 的页眉。
* `<footer>`  定义 section 或 page 的页脚。
* `<main>`    规定文档的主要内容。
* `<section>` 定义文档中的区段。
* `<article>` 定义文章。
* `<aside>`   定义页面内容之外的内容。
* `<details>` 定义元素的细节。
* `<summary>` 为 `<details>` 元素定义可见的标题。
* `<nav>` 定义导航链接。
* `<progress>`    定义任何类型的任务的进度。
* `<time>`    定义日期/时间。
* `<wbr>` 定义可能的换行符（Word Break Opportunity）。

`div` 和 `span` 是两个典型的没有任何语义的标签，只有在**没有对应语义的标签**时再使用。

### 自闭合标签
自闭合标签（self-closing）可以不关闭标签。例如`<br/>`、`<hr/>`、`<input/>`、`<img/>` ，可以写成`<br>`、`<hr>`、`<input>`、`<img>`。

### 不使用HTML 5废弃的标签
以下标签已经在HTML 5中标记为废弃，请不要使用。
* `<acronym>` ：请使用`<abbr>`。
* `<applet>`：请使用`<embed>` 或 `<object>`。
* `<basefont>`：请使用样式表。
* `<big>`：请使用样式表。
* `<center>`：请使用样式表。
* `<dir>`：请使用`<ul>`。
* `<font>`：请使用样式。
* `<frame>`：HTML 5不支持。
* `<frameset>`：HTML 5不支持。
* `<noframes>`：HTML 5不支持。
* `<strike>`：请使用`<del>` 或 `<s>`。
* `<tt>`：请使用样式。

### 使用小写属性名
Bad:
```html
<div CLASS="menu">
```

Good:
```html
<div class="menu">
```


### 属性值加双引号
Very bad:  
这个属性值无效，因为值中包含空格：
```html
<table class=table striped>
```

Bad:
```html
<table class=striped>
```

Good:
```
<table class="striped">
```


### 必需的属性
请始终对图像使用 `alt` 属性。当图像无法显示时该属性很重要。请始终定义图像尺寸。这样做会减少闪烁，因为浏览器会在图像加载之前为图像预留空间。

Bad:
```html
<img src="html5.gif">
```

Good:
```html
<img src="html5.gif" alt="HTML5" style="width:128px;height:128px">
```
`<a>` 标签的title属性可作为说明信息，并且当鼠标hover时显示为提示信息。

Good:
```html
<a href="https://www.baidu.com/" title="百度搜索">百度一下</a>
```

### 空格和等号

等号两边的空格是合法的，但是精简空格更易阅读。

Bad:
```html
<link rel = "stylesheet" href = "styles.css">
```

Good:
```html
<link rel="stylesheet" href="styles.css">
```

### 合理使用id和类
同一个页面同一个id的元素**只能有一个**，不同的页面可以有多个。  
同一个页面同一个类的元素可以有多个。  
通常用类来定义样式，用id来为JavaScript提供快速选择的途径。

### 有确定值的属性
boolean类型的属性可以不写属性值。例如 `disabled="disabled"`、`readonly="readonly"`、`checked="checked"`、`selected="selected"`，可以写成`disabled`，`readonly`，`checked`，`selected`。

> 元素的布尔型属性如果有值，就是 true，如果没有值，就是 false。

其他类似属性还有：`autofocus`，`async`，`controls`，`autoplay`，`muted`，`loop`，`download`，`hidden`，`novalidate`，`required`。  
下列属性当值为真值时也可以省略属性值。  
* `contenteditable="true"`
* `autocomplete="on"`
* `preload="auto"`
* `spellcheck="true"`

### 命名
id、class命名应当尽可能短，并且意义明确（不要随意自创缩写）。单词全部使用小写，多个单词之间以连字符连接。（参考Bootstrap命名方式）  
Good：btn、nav、msg、info、desc、menu、header、footer、sidebar、detail、logo、btn-small、btn-large  
Bad：d、a1、b2、m10、mn、inf、des、btnA、hd、ft、btn1、delt、lg、btn-s、btn-l  
不以表现来命名，而是根据内容语义来命名。比如：left, right, center, red, black这种以表现来命名，不允许出现；  
Bad：btn-green、btn-red、btn-w100 (代表width:100px)、btn-w50 (代表width:50px)  
Good：btn-success、btn-danger、btn-large、btn-small

### 嵌套
请注意正确的嵌套顺序。行内元素中尽量不嵌套块级元素。  
Bad:
```html
<span>
    <div>nested div</div>
</span>
<a href="#">
    <div>nested div</div>
</a>
```
另外注意以下元素中也不能嵌套块级元素，只能嵌套行内元素。  
标题标记的 `<h1>` ~ `<h6>` 、`<caption>` ，段落标记的 `<p>`。

`<h1>` ~ `<h6>` 、`<a>` 、 `<button>` 不能嵌套两层相同元素。同时 `<a>` 和 `<button>` 也不建议互相嵌套。  
Bad:
```html
<a href="#">
    <a href="#">nested a</a>
</a>
<button>
    <button>nested button</button>
</button>
<h3>
    <h2>nested heading</h2>
</h3>
<a href="#">
    <button>nested button</button>
</a>
<button>
    <a href="#">nested a</a>
</button>
```

### 结构、表现、行为分离
使用外部样式和脚本，样式放在css文件里，脚本放在js文件里。  
尽量不使用内联样式(`style="width:100px"`)和内部样式(`<style>div{width:100px;}</style>`)。  
尽量不使用内联脚本(`onclick="onClick()"`)和内部脚本(`<script>alert('hello world');</script>`)。

在引入 CSS 和 JavaScript 文件时一般不需要指定 `type` 属性，因为 `text/css` 和 `text/javascript` 分别是它们的默认值。

### 样式表位置

外部和内部样式表定义在head结束标签前。

```html
<head>
    <meta charset="UTF-8">
    <title>FrontEnd Code Style</title>
    
    <link rel="stylesheet" href="styles.css">
    <style>
        body { margin: 0; }
    </style>
</head>
```

### 脚本位置

外部和内部脚本定义在body结束标签前。
```html
<body>
    <div class="wrapper">
        ...
    </div>
    
    <script src="jquery.js">
    <script>
        alert("hello html5");
    </script>
</body>
```

### 使用小写文件名

尽量使用小写文件名，不要使用中文文件名，多个单词之间以连字符-分隔。
如：
```
index.html
my-page.html
jquery-1.12.4.js
icon-search.png
```

### 文件扩展名

HTML 文件名应该使用扩展名 **.html**（而不是 .htm）。

CSS 文件应该使用扩展名 **.css**。

JavaScript 文件应该使用扩展名 **.js**。
