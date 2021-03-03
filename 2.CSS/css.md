# CSS 层叠样式表
<br>

> ### .老夫聊发少年狂，左牵黄，右擎苍，锦帽貂裘，千骑卷平冈。
>                                      ——苏轼《江城子·密州出猎》
<br>
<br>

### 目录

P1： 选择器和常用属性

P2： 选择器进阶

P3： 盒子模型

P4： 浮动布局

p5:  树形结构

#### P1： 选择器和常用属性

常用选择器：
1. 元素选择器：标签--  h1 p span div ...
2. 类选择器: class-- .className
3. id选择器（唯一性）： id-- #idName -- 少用
4. 通配符选择器：* -- 选中所以元素

常用属性：
* 字体大小：font-size
* 字体颜色：color
* 宽度：width
* 高度：height
* 背景色：background-color
* 文本水平居中：text-align
* 文本行高（垂直居中）：line-height

```html
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        p{
            /* chrome浏览器：font-size最小值12px */
            font-size: 20px;
            color: aqua;
            background-color: black;
        }
        /* 类选择器 */
        .text{
            text-align: center;
            line-height: 30px;
        }
        img{
            width: 400px;
            /* auto和不设高度都会自动适应 */
            height: auto;
        }
    </style>
</head>
<body>
    <p class="text">hello css && html</p>
    <img src="./back.jpg" alt="">
```

例子：[p1](code/p1.html)

#### P2： 选择器进阶

选择器进阶：
1. 层级选择器：selector1 selector2 (空格--后代选择器)
2. 组合选择器：selector1,selector2 (选中两个选择器)
3. 伪类选择器(添加行为)：:hover-鼠标移入
4. 伪元素选择器：-- ：：before  ::after  content:"内容"


选择器权重：
id(100) > class(10) > element元素(1)

* 相同权重：后面会覆盖前面的。

* 层级选择器：权重叠加。 

* 权重值最高：后面+!important ;

引入css方法:

内敛样式、行内样式:  -- 权重高，代码维护困难。

嵌入样式: head内部style -- 也是少用

外部样式：引入css文件   link标签(常用)

例子：[p1](code/p2.html)

#### P3： 盒子模型

讲html元素看做盒子： 外边距、边框、内边距、内容

* 边框： border-width;border-style(solid实线,dashed虚线);border-color.

* 外边距：margin(-top-right-bottom-left-) -上-右-下-左-

* 内边距：padding(-top-right-bottom-left-) -上-右-下-左-

设置`box-sizeing:border-box`; 元素的实际高度和宽度：height和width

设置`*`margin=0;padding:0 ; 元素初始化

设置 margin= 0 auto 上下为0 左右自动居中; 元素居中显示

列表属性：
list-style: inside/点在内部 --- none/取消样式

a:设置样式： text-decoration:none

例子：[p3](code/p3.html)

#### P4： 浮动布局

分类：display

1. 块元素（block）：可以设置宽高，独占一行。h1-h6 、 p 、 div 、ul 、ol 、 li 

2. 行内元素、行级元素（inline）：不可以设置宽高，不独立成行。 a 、 span

3. 行内块（inline-block）：可以设置宽高，不独立成行。img 、 input 、button

4. 隐藏元素（none）

浮动：float

将元素同一行显示。right/left

特性：脱离文档流。 --- 解决：清除浮动

* 浮动元素后  加盒子  设置样式：clear:both;

* (最好)用伪元素元素器 给浮动元素父级设置样式，前后都清除浮动 以后也不会有影响

```html
    <style>
        .clear::before, .clear::after{
            content:"";
            /* 设置成块元素 */
            display:block;
            clear:both;
        }
        .left{
            border:1px solid red;
            float:left;
        }
    </style>


    <body>
        <div class="clear">
            <div class="left">
                123
            </div>
            <div class="left">
                abc
            </div>
        </div>
    </body>
```

完成：
![课后练习](code/lianxi.png)
例子：[p4](code/p4/p4.html)