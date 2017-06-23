# 前端代码规范

## CSS部分

### 命名
参见HTML中id和class的[命名规范](HTML%20Code%20Style.md#%E5%91%BD%E5%90%8D)。
单词全部使用小写，多个单词之间以连字符连接。

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
若无必要，不要在id和class前增加类型选择器。
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
后代选择器最多不超过**三层**。
Bad:
```css
#rules .container .rules > .rule .qrcode p {}
```
Good:
```
#rules .qrcode p {}
```
### 组合选择器
使用组合选择器时每个选择器单独占用一行。
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

短规则可以压缩为一行，如下：

```css
.intro { font-family: Verdana; font-size: 16em; }
```
* 在开括号之前和之后使用一个空格
* 在每个属性与其值之间使用冒号加一个空格
* 在每个属性值对（包括最后一个）之后使用分号
* 在每个分号之后添加一个空格
* 只在值包含空格时使用引号来包围值

长规则应分为多行：

```css
body {
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
* 当属性有多个值时在每个逗号之后添加一个空格
* 在每个属性值对（**包括最后一个**）之后使用分号
* 只在值包含空格时使用引号来包围值
* 把闭括号放在新的一行，之前不用空格

规则之间使用一个换行分隔。
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

### 值和单位
当值为0时省略单位和%。
Bad:
```css
width: 0%;
margin: 0px;
animation-duration: 0s;
font-size: 0em;
```
Good:
```css
width: 0;
margin: 0;
animation-duration: 0;
font-size: 0;
```
当值为0点几时省略0。
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
使用尽可能短的16进制颜色值。
Bad:
```css
color: #eebbcc;
```
Good:
```css
color: #ebc;
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
1. 位置属性(position, top, right, z-index, display, float等)
2. 大小(width, height, padding, margin)
3. 文字系列(font, line-height, letter-spacing, color, text-align等)
4. 背景(background, border等)
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
使用[Normalize]()