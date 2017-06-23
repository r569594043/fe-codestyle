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
`<header>`  定义 section 或 page 的页眉。
`<footer>`  定义 section 或 page 的页脚。
`<main>`    规定文档的主要内容。
`<section>` 定义文档中的区段。
`<article>` 定义文章。
`<aside>`   定义页面内容之外的内容。
`<details>` 定义元素的细节。
`<summary>` 为 <details> 元素定义可见的标题。
`<nav>` 定义导航链接。
`<progress>`    定义任何类型的任务的进度。
`<time>`    定义日期/时间。
`<wbr>` 定义可能的换行符（Word Break Opportunity）。

`div` 和 `span` 是两个典型的没有任何语义的标签，只有在没有对应的语义的标签的时候再使用。

### 自闭合标签
自闭合标签可以不关闭标签。例如`<br/>`、`<hr/>`、`<input/>`、`<img/>` ，可以写成`<br>`、`<hr>`、`<input>`、`<img>`。

### 不使用HTML 5废弃的标签
以下标签已经在HTML 5中标记为废弃，请不要使用。
`<acronym>` ：请使用`<abbr>`。
`<applet>`：请使用`<embed>` 或 `<object>`。
`<basefont>`：请使用样式表。
`<big>`：请使用样式表。
`<center>`：请使用样式表。
`<dir>`：请使用`<ul>`。
`<font>`：请使用样式。
`<frame>`：HTML 5不支持。
`<frameset>`：HTML 5不支持。
`<noframes>`：HTML 5不支持。
`<strike>`：请使用`<del>` 或 `<s>`。
`<tt>`：请使用样式。

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
`<a>`标签的title属性可作为说明信息，并且当鼠标hover时显示为提示信息。

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
同一个页面同一个id的元素只能有一个，不同的页面可以有多个。
同一个页面同一个类的元素可以有多个。
通常用类来定义样式，用id来为JavaScript提供快速选择的途径。

### 有确定值的属性
boolean类型的属性可以不写属性值。例如 `disabled="disabled"`、`readonly="readonly"`、`checked="checked"`、`selected="selected"`，可以写成`disabled`，`readonly`，`checked`，`selected`。
其他类似属性还有：`autofocus`，`async`，`controls`，`autoplay`，`muted`，`loop`，`download`，`hidden`，`novalidate`，`required`。
下列属性当值为真值时也可以省略属性值。
`contenteditable="true"`
`autocomplete="on"`
`preload="auto"`
`spellcheck="true"`

### 命名
id、class命名要足够表达含义，不要随意自创缩写（但是可以使用大家广泛采用的缩写），单词全部使用小写，多个单词之间以连字符连接。（参考Bootstrap命名方式）
Good：btn、nav、msg、info、desc、menu、header、footer、sidebar、detail、logo、btn-small、btn-large
Bad：d、a1、b2、m10、mn、inf、des、btnA、hd、ft、btn1、delt、lg、btn-s、btn-l
使用语义而不是表现去命名。
Good：btn-success、btn-danger、btn-large、btn-small
Bad：btn-green、btn-red、btn-w100 (代表width:100px)、btn-w50 (代表width:50px)

### 结构、表现、行为分离
使用外部样式和脚本，样式放在css文件里，脚本放在js文件里。
尽量不使用内联样式(`style="width:100px"`)和内部样式(`<style>div{width:100px;}</style>`)。
尽量不使用内联脚本(`onclick="onClick()"`)和内部脚本(`<script>alert('hello world');</script>`)。

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
index.html
my-page.html
jquery-1.12.4.js
icon-search.png

### 文件扩展名

HTML 文件名应该使用扩展名 **.html**（而不是 .htm）。

CSS 文件应该使用扩展名 **.css**。

JavaScript 文件应该使用扩展名 **.js**。
