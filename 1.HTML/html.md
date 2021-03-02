# HTML 超文本传输协议
<br>

> ### 休对故人思故国，且将新火试新茶，诗酒趁年华。
>                                        ——苏轼 《望江南》

<br>
<br>

### 目录

P1： 学前准备

P2： 常用标签

p3:  表格和表单

<br>

#### P1： 学前准备

1. vscode/vscodium(全开源)

插件：

* Live server : 加载web页面(前端)

* Prettier : 代码格式化

* Browser preview : 在编辑器中打开一个用于调试的真正的浏览器预览

* Bracket pair colorizer : 颜色来标识匹配的括号

2. chrome/chromium(全开源)

`f12` ：开发者模式

<br>

#### P2： 常用标签

***html***:  （超文本标记语言 Hyper Text Markup Language）, 是一种用来描述网页的语言, 不是编程语言，而是一种`标记语言`（相似的还有MD语言，JSX语言，WXML语言，等等都是一种规则而已）

! + tab : html结构

1. 骨架：

```html

<!-- 根标签 -->
<!doctype html>
<html lang="en">
    <!-- 文档的头部 -->
    <head>
        <!-- 编码 -->
        <meat charset="utf-8">
        <!-- 文档的标题 -->
        <title></title>
    </head>
    <!-- 文档主体 -->
    <body>

    </body>
</html>

```
注意：doctype html 这个是**文档声明**，表示这个HTML文件的内容需要按照什么标准（规则）进行解析。

* doctype 是文档类型的意思，`主要告诉浏览器使用哪种解析规范`
* lang  指定HTML的语言种类，en 表示是英语，zh-CN 表示中文，还有其他语种
* utf-8 字符集（最常用），更多字符集可自行百度

2. 常用标签

* 注释：ctrl+/ 或者 \<!-- -->
```
<!-- 我是注释 -->
```

* 标题标签：h1~h6 大——小
```html
<h1> 一级标题 </h1>
<h2> 二级标题</h2>
    ......
```

* 段落：p
```
<p>我的文章。。。。。</p>
```

* 无序列表：ul li
```html
<ul>
    <li>苹果</li>
    <li>菠萝</li>
    <li>橘子</li>
</ul>
```

* 有序列表：ol li 
```html
<ol>
    <li>1.</li>
    <li>2.</li>
    <li>3.</li>
</ol>
```

* 链接： a
```html
<!-- href属性：跳转的地址 -->
<a href="www.baidu.com">百度</a>
<!-- 锚点 -->
<h1 id="aa">回到</h1>

<a href="aa"></a>
```

* 图片：img
```html
<!-- src属性：图片地址 alt属性：图片失效后显示的文字 -->
<img src="..." alt="图片加载失败">
```

* 无语义标签：div 和 span
```html
<div>块级</div>

<span> 行内块</span>
```

#### P3： 表格和表单

* 表格: table

其他表格标签： thead表头  tbody表体 th tr td

``` html
    <!-- 表格容器：table -->
    <table border="2">
        <!-- 表头 -->
        <thead>
            <th>序号</th>
            <th>姓名</th>
            <th>年龄</th>
        </thead>
        <!-- 表体 -->
        <tbody>
            <tr>
                <td colspan="4">学生信息</td>
            </tr>
            <tr>
                <td rowspan="3">一班</td>
                <td>1</td>
                <td>小米</td>
                <td>17</td>
            </tr>
            <tr>
                <td>2</td>
                <td>小名</td>
                <td>17</td>
            </tr>
            <tr>
                <td>3</td>
                <td>小明</td>
                <td>17</td>
            </tr>
        </tbody>
    </table>

```

合并单元格：横：colspan="占用的列"  纵：rowspan="列"

* 表单：form
> 后台提交数据  --  action---路径
>                  method -- 提交方式

lable 标签：属性：for = 获取焦点（id）

input 标签：属性：
value:控制文本
placeholder:提示信息
type:
1. text  文本
2. password 密码
3. submit 提交
4. button 按钮
5. radio 单选框 -- name属性一致
6. checbox 复选框 -- name属性一致

```html
    <form action=""> 
        <label for="username">用户名：</label>
        <input id="username" type="username">
        <label for="password">密码：</label>
        <input type="password" id="password">
    </form>
```

下拉框：
```html
        <select name="" id="">
            <option value="">男</option>
            <option value="">女</option>
        </select>
```

