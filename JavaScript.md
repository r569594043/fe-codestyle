# 前端代码规范

## JavaScript部分

### 空格和缩进
不使用tab缩进，使用四个空格的缩进。
### 花括号
左花括号应该在行的结束，而不应该单独一行（Java习惯）。一直使用花括号括起逻辑块，即使只有一行语句，也应该用花括号括起来。
Bad:  
```js
if (statement) {
    doSomeThing;
} else {
    doSomeThing;
}
```
### 字符串
用单引号定义字符串。
### 分号
语句结束一定要使用分号。
### 使用字面量创建对象和数组
// bad
var item = new Object();

// good
var item = {};

// bad
var items = new Array();

// good
var items = [];

### IIFE（立即执行的函数表达式）
使用IIFE建立作用域。
### 严格模式

### 全局变量
尽量不用全局变量。