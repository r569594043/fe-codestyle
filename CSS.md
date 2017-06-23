# 前端代码规范

## CSS部分

### 命名
参见HTML中id和class的[命名规范](HTML%20Code%20Style.md#%E5%91%BD%E5%90%8D)。  
命名应当尽可能短，并且意义明确。单词全部使用小写，多个单词之间以连字符连接。不以表现来命名，而是根据内容语义来命名。比如：left, right, center, red, black这种以表现来定命名，不允许出现。

Bad:
```css
#navigation {}
.atr {}
.btn-red
```
Good:
```css
#nav {}
.author {}
.btn-danger {}
```
### 注释
参见如下注释。
```css
/* This is a comment */
```
```css
/*
    This is a long comment example. This is a long comment example.
    This is a long comment example. This is a long comment example.
*/
```

### 类型选择器
若无必要，不要在id和class前增加类型选择器限定。  
Bad:
```css
ul#example {}
div.error {}
```
Good:
```css
#example {}
.error {}
```
### 后代选择器
选择器的嵌套层级最多不超过**三层**。  
Bad:
```css
.page-container #stream .stream-item .info .info-header .username {}
```
Good:
```
.info-header .username {}
```
### 选择器分组
使用选择器分组时每个选择器单独占用一行。  
Bad:
```css
a:focus, a:active {
  position: relative; top: 1px;
}
```
Good:
```css
h1,
h2,
h3 {
  font-weight: normal;
  line-height: 1.2;
}
```

### 空格和缩进
如下：

```css
body > .wrapper {
    background-color: lightgrey;
    font-family: "Arial Black", Helvetica, sans-serif;
    font-size: 16em;
    color: black;
}
```

* 开括号与选择器位于同一行
* 在开括号之前用一个空格
* 使用四个空格的缩进
* 在每个属性与其值之间使用冒号加一个空格
* 对于以逗号分隔的属性值，每个逗号后面都应该插入一个空格
* 在每个属性值对（**包括最后一个**）之后使用分号
* 分号后不要留空格
* 每个属性值对单独占一行
* 只在值包含空格时使用引号来包围值
* 把闭括号放在新的一行，之前之后都不要空格
* &gt;、+、~ 选择器的两边各保留一个空格
* 属性选择器中的值用双引号包围

规则集之间使用一个换行分隔。  
Good:
```css
html {
  background: #fff;
}

body {
  margin: auto;
  width: 50%;
}
```

### 缩写属性
尽量使用缩写属性。  
Bad:
```css
border-top-width: 1px;
border-top-style: solid;
border-top-color: #000;
font-family: palatino, georgia, serif;
font-size: 100%;
line-height: 1.6;
padding-bottom: 2em;
padding-left: 1em;
padding-right: 1em;
padding-top: 0;
```
Good:
```css
border-top: 1px solid #000;
font: 100%/1.6 palatino, georgia, serif;
padding: 0 1em 2em;
```
但是也不要滥用缩写属性，当只需要设置单个值的时候不要使用缩写属性。  
Bad:
```css
.element {
    margin: 0 0 10px;
    background: red;
    background: url("image.jpg");
}
```

Good:
```
.element {
    margin-bottom: 10px;
    background-color: red;
    background-image: url("image.jpg");
}
```

### 值和单位
当值为0时省略单位和%。  
Bad:
```css
width: 0%;
margin: 0px;
font-size: 0em;
```
Good:
```css
width: 0;
margin: 0;
font-size: 0;
```
当值为-1至1之间的小数时省略前导的0。  
Bad:
```css
font-size: 0.8em;
line-height: 0.5;
```
Good:
```css
font-size: .8em;
line-height: .5;
```
### 颜色
尽量使用16进制颜色值，英文字符采用小写。并且尽可能短。  
Bad:
```css
color: #eebbcc;
background: #03E4D5;
```
Good:
```css
color: #ebc;
background: #03e4d5;
```
### 字体
字体族尽量使用英文名，如果有空格需要放在双引号中。常见中文字体对应英文名如下：
<table>
    <thead>
        <tr><th>字体</th><th>操作系统</th><th>Family Name</th></tr>
    </thead>
    <tbody>
        <tr>
            <td>宋体 (中易宋体)</td>
            <td>Windows</td>
            <td>SimSun</td>
        </tr>
        <tr>
            <td>黑体 (中易黑体)</td>
            <td>Windows</td>
            <td>SimHei</td>
        </tr>
        <tr>
            <td>微软雅黑</td>
            <td>Windows</td>
            <td>Microsoft YaHei</td>
        </tr>
        <tr>
            <td>微软正黑</td>
            <td>Windows</td>
            <td>Microsoft JhengHei</td>
        </tr>
        <tr>
            <td>华文黑体</td>
            <td>Mac/iOS</td>
            <td>STHeiti</td>
        </tr>
        <tr>
            <td>冬青黑体</td>
            <td>Mac/iOS</td>
            <td>Hiragino Sans GB</td>
        </tr>
        <tr>
            <td>文泉驿正黑</td>
            <td>Linux</td>
            <td>WenQuanYi Zen Hei</td>
        </tr>
        <tr>
            <td>文泉驿微米黑</td>
            <td>Linux</td>
            <td>WenQuanYi Micro Hei</td>
        </tr>
    </tbody>
</table>

使用方式如下：
```css
h1 {
    font-family: "Microsoft YaHei";
}
```
font-family 按「英文字体在前、中文字体在后」、「效果佳 (质量高/更能满足需求) 的字体在前、效果一般的字体在后」的顺序编写，最后必须指定一个通用字体族( serif / sans-serif )。

### 动画
在可能的情况下应选择这样四种变换：

* transform: translate(npx, npx);
* transform: scale(n);
* transform: rotate(ndeg);
* opacity: 0..1;

典型的，可以使用 translate 来代替 left 作为动画属性。  
示例：

Bad:
```css
.box {
    left: 0;
    transition: left 1s;
}
.box:hover {
    left: 20px; /* move right for 20px */
}
```

Good:
```css
.box {
    transition: transform 1s;
}
.box:hover {
    transform: translate(20px); /* move right for 20px */
}
```

### Hacks
不使用浏览器探测（CSS Hacks）。  
可以针对低版本ie浏览器使用条件判断，将样式放在独立的文件中。
```html
<!--[if IE 6]>
<link rel="stylesheet" type="text/css" href="css/ie6.css" />
<![endif]-->
<!--[if IE 7]>
<link rel="stylesheet" type="text/css" href="css/ie7.css" />
<![endif]-->
```

### 属性顺序
推荐的CSS属性书写顺序：
1. 定位(position, top, right, z-index, display, float等)
2. 盒模型(width, height, padding, margin)
3. 字体和文本(font, line-height, letter-spacing, color, text-align等)
4. 视觉(background, border等)
5. 其他(animation, transition等)

详细顺序参见[RECESS](https://github.com/twitter/recess/blob/master/lib/lint/strict-property-order.js#L36)

### 厂商前缀
按如下顺序使用厂商前缀：
```css
background: -webkit-linear-gradient(red, yellow);
background: -moz-linear-gradient(red, yellow);
background: -o-linear-gradient(red, yellow);
background: linear-gradient(red, yellow);
-webkit-transform: rotate(90deg);
-moz-transform: rotate(90deg);
-ms-transform: rotate(90deg);
-o-transform: rotate(90deg);
transform: rotate(90deg);
```

### CSS Reset
使用 [Normalize](http://necolas.github.io/normalize.css/) 代替 [CSS Reset](http://meyerweb.com/eric/tools/css/reset/)

### 多组合少继承
多使用组合方式定义样式（参考Bootstrap）。比如先定义.btn样式基础，.btn-success定义绿色按钮，.btn-lg定义大尺寸按钮。  
组合三个类 `<button class="btn btn-success btn-lg"></button>` 定义绿色大尺寸的按钮，  
另外三个类`<button class="btn btn-danger btn-sm"></button>` 定义红色小尺寸按钮。
