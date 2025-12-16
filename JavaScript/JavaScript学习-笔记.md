# 黑马程序员前端JavaScript入门到精通全套视频教程，javascript核心进阶ES6语法、API、js高级等基础知识和实战教程

[视频链接](https://www.bilibili.com/video/BV1Y84y1L7Nn/?spm_id_from=333.337.search-card.all.click&vd_source=0a0dd058ef849bffba564af91a70780d)

百度网盘链接：https://pan.baidu.com/s/1MxueOHXGQtmE-ypRq1kELA&pwd=9987

2025年7月13号

## 1 JavaScript 基础

### 1.1 JavaScript简介(p3)

**1 什么是 JavaScript 语言？**

> 是一种运行在客户端（浏览器）的编程语言，实现人机交互效果

2 JavaScript的组成（有什么？）

> 1）ECMAScript： 规定了js基础语法核心知识。
>
> 2）DOM： 操作文档，比如对页面元素进行移动、大小、添加删除等操作
>
> 3）BOM：操作浏览器，比如页面弹窗，检测窗口宽度、存储数据到浏览器等等

3 实现页面中点击按钮，显示粉色，其他不显示。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <style>
    .pink {
      color: pink;
    }
  </style>
</head>
<body>
<button> 按钮1</button>
<button> 按钮2</button>
<button> 按钮3</button>
<button> 按钮4</button>
<script>
  const buttonList = document.querySelectorAll('button');
  buttonList.forEach(button => {
    button.addEventListener('click', (event) => {
      document.querySelector('.pink') && (document.querySelector('.pink').className = '');
      const ele = event.target;
      ele.className = 'pink';
    });
  });
</script>
</body>
</html>
```

4 JavaScript 书写位置

> 1 内部 JavaScrip: 直接写在html文件里，用script标签包住。规范：script标签写在body标签的底部
>
> 2 外部 JavaScript：一般将 JavaScript 代码写js 文件中，然后通过 `script` 标签的 `src` 属性引入，如果 script 标签使用 src
> 属性引入了某 js 文件，那么 标签的代码会被忽略
>
> ```html
> <script src="./my.js"></script>
> ```
>
> 3 内联 JavaScript: 代码写在标签内部
>
> ```html
> <body>
> 	<button onclick="alert('111')"> 按钮4</button>
> </body>
> ```

### 1.2 注释

JavaScript支持两种注释方式

> 1 单行注释：//
>
> 2 多行注释：/*  */ 多行注释不能嵌套

### 1.3 结束符

> 结束符是分号(;)，可省略，为了统一风格，统一加或者不加

### 1.4 输入与输出(p6)

> 1 概念：输出和输入也可理解为人和计算机的交互，用户通过键盘、鼠标等向计算机输入信息，计算机处理后再展示结果给用户，这便是一次输入和输出的过程。
>
> 2 输出
>
>  document.wirte()： 向body内输出内容，如果输出的内容写的是标签，也会被解析成网页元素
>
>  alert()：页面弹出警告对话框
>
>  console.log():  控制台输出语法，程序员调试使用
>
> 3 输入
>
>  prompt('111')： 显示一个对话框，对话框中包含一条文字信息，用来提示用户输入文字
>
> 4 JavaScript 代码执行顺序
>
>  按HTML文档流顺序执行JavaScript代码。 alert() 和 prompt() 它们会跳过页面渲染先被执行

### 1.5 字面量

1 概念

> 直接出现在程序中的数据值。

2 类型(??后续再添加)

> 1 数值
>
> 2 字符串
>
> 3 布尔值
>
> 4 空对象null

### 1.6 变量

1 概念

> 变量是计算机存储数据的“容器”，本质是计算机存储数据的一个内存空间

2 变量的声明|定义，初始化(变量的赋值)

> var|const|let 变量名 = 数据值

3 变量命令的规范

> 1 不能用关键字
>
> 2 只能用下划线、字母、数字、$组成，且数字不能开头(标识符)
>
> 3 字母严格区分大小写
>
> 4 建议
>
>  起名要有意义
>
>  遵守小驼峰命名法

4 let和var的区别(？再整理)

### 1.7 常量

1 概念

> 使用 const 声明的变量称为“常量”

2 注意点

> 1 声明的时候必须赋值（初始化），值不允许修改

### 1.8 数组

1 概念（p11）

> 数组是值的有序集合

2 相关概念

> 数组字面量：let arr = [10, '111']
>
> 元素：数组中的值
>
> 索引下标：元素所在的位置，从0开始
>
> 长度：数组中元素的个数，length属性获取
>
> 取值：数组名[下标]

## 2  面试专属

### 2.1 基础

#### 2.1.1 JavaScript数据类型

1 数据类型概念

>JavaScript一共有8种数据类型，其中有7种原始数据类型和1种引用数据类型。7种原始数据类型：Undefined、Null、Boolean、Number、String、Symbol（es6新增，表示独一无二的值）和BigInt（es10新增）。1种引用数据类型——Object，Object本质上是由一组无序的名值对组成的，里面包含
function、Array、Date等。JavaScript不支持任何创建自定义类型的机制，而所有值最终都将是上述 8 种数据类型之一。

> 注意：BigInt 是一种数字类型的数据，它可以表示任意精度格式的整数，使用 BigInt 可以安全地存储和操作大整数，即使这个数已经超出了
> Number 能够表示的安全整数范围

2 数据类型的存储

> **原始**数据类型: 直接存储在栈(stack)中，占据空间小、大小固定，属于被频繁使用数据，所以放入栈中存储
>
> 引**用**数据类型：同时存储在栈（stack）和堆（heap）中，占据空间大、大小不固定。引用数据类型在**栈中存储了指针**，该指针指向堆中该
**对象的起始地址**。当解释器寻找引用值时，会首先检索其在栈中的地址，取得地址后从堆中获得对象

3 数据类型的判断

1）typeof

> typeof 是一元运算符，返回一个字符串，表示未经计算的操作数的类型
>
> 对于原始类型来说，除了 null 都可以返回正确的类型。对于对象来说，除了函数都会显示 object，所以说 typeof
> 并不能准确判断变量到底是什么类型。如果想判断一个对象的正确类型，这时候可以考虑使用 instanceof

| 类型                   | 结果           |
| ---------------------- | -------------- |
| Undefined              | “undefined”    |
| Null                   | “object”       |
| Boolean                | “boolean”      |
| Number                 | “number”       |
| BigInt                 | “bigInt”       |
| String                 | “string”       |
| Symbol                 | “symbol”       |
| 宿主对象(由JS环境提供) | 取决于具体实现 |
| Function对象           | “function”     |
| 其他任何对象           | “object”       |

2）instanceof 

> 返回一个布尔值，判断对象是否为某个构造函数的实例。instanceof的原理是检查右边构造函数的prototype属性，是否在左边对象的原型链上
>
> 注意点1：instanceof 可以正确的判断对象的类型，因为内部机制是通过判断对象的原型链中是不是能找到类型的 prototype
>
> 注意点2：instanceof可以精准判断引用数据类型（Array，Function，Object），而基本数据类型不能被instanceof精准判断
>
> 注意点3：instanceof判断对象是否是某一数据类型（如Array）的实例，请重点关注一下是判断一个对象是否是数据类型的实例。在这里字面量值，2， true ，'str'不是实例，所以判断值为false

3）constructor(需要修改)

> 这里有一个坑，如果我创建一个对象，更改它的原型，constructor就会变得不可靠了

4）Object.prototype.toString.call

> 返回[object Type] 的字符串。Object.prototype.toString方法是Object原型上面的方法，所有继承于Object的实例对象都有该方法，为了使Object.prototype.toString应用于任何值，需要使用call函数改变绑定的对象

| 类型       | 结果               |
| ---------- | ------------------ |
| 数值       | [object Number]    |
| 字符串     | [object String]    |
| 布尔值     | [object Boolean]   |
| Undefined  | [object Undefined] |
| Null       | [object Null]      |
| 数组       | [object Array]     |
| arguments  | [object Arguments] |
| 函数       | [object Function]  |
| Error对象  | [object Error]     |
| Date对象   | [object Date]      |
| RegExp对象 | [object RegExp]    |
| 其他对象   | [object Object]    |

5 undefined 与 undeclared 的区别？

> 已在作用域中**声明但还没有赋值**的变量，是 **undefined**。相反，还**没有**在作用域中**声明**过的变量，是 **undeclared** 的。
>
> 对于 undeclared 变量的引用，浏览器会报引用错误，如 ReferenceError: b is not defined 。但是我们可以使用 typeof 的安全防范机制来避免报错，因为对于 undeclared（或者 not defined ）变量，typeof 会返回 "undefined"。

#### 2.1.2 运算符

1 && 、 ||和!! 运算符区别

> && 叫逻辑与：在其操作数中找到第一个假值表达式并返回它，如果没有找到任何假值表达式，则返回最后一个真值表达式。它采用短路来防止不必要的工作
>
> || 叫逻辑或:：在其操作数中找到第一个真值表达式并返回它。这也使用了短路来防止不必要的工作。在支持 ES6
> 默认函数参数之前，它用于初始化函数中的默认参数值
>
> !! 运算符：可以将右侧的值强制转换为布尔值，这也是将值转换为布尔值的一种简单方法

