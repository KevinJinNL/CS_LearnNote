

# WEB开发

# HTML

------

## 页面组成

​	一个html页面大体由一个又一个的嵌套模块组成，其中最大的模块为html模块，即

## html模块

```html
<html>
	.........
</html>
```

其中html模块中又分为两个主体,并且html标签下包含的东西是最多最广的

### head标签

```html
<head>
	.........
</head>
```

​	在head标签下，我们经常会保存如下标签的内容

- **title**

  ​	一般用于定义文档的的标题，显示在浏览器的标题栏或者标签页上，一般会完整地概括整个网页的内容

- **base**

  ​	给页面上所有相对URL的提供一个基础，一份文档中只能有一个**base**标签

- **link**

  ​	规定外部资源与当前文档的关系，常用于链接样式表，如

  ```html
  <link rel="stylesheet" href="xxx.css" type="text/css">
  ```

  ​	还有用于SEO，主要提供给搜索引擎，在网站中常有多个URL指向同一个页面的情况，此标签告知搜索引擎页面的主URL是什么，一边搜索引擎保留主要页面而去除其他重复页面

  ```html
  <link rel="canonical" href="...">
  ```

- **style**

  包含文档的样式信息

- **meta**

  一种通用的元数据信息表示标签，一般以键值对出现，如

  ```html
  <meta name="xxx" content="yyy">
  ```

#### charset属性

```html
<meta charset="UTF-8">
```

​	从 HTML5 开始，上述写法被推荐使用，用于声明当前文档所使用的字符编码，推荐放在 `<head>` 中的第一位。

### body标签

#### h标签

​	h标签全程head标签，与markdown中的语法相同，代表着标题等级，从h1到h6

#### p标签

​	p标签全程paragrah标签，顾名思义为纯文本代表的标签

![image-20220306132137781](C:\Users\kevin\AppData\Roaming\Typora\typora-user-images\image-20220306132137781.png)

### 块级元素

------

- 在页面以块的形式展现

- 出现在新的一行

- 占全部宽度

  ```text
  如<div>,<h1>-<h6>,<p>等等
  ```

### 内联元素

------

- 通常在块级元素内

- 不会导致文本换行

- 只占必要的部分宽度

  ```text
  如<a>,<img>,<em>,<strong>等等
  ```

#### a标签

```html
<a href="https://google.com">Google</a>
```

​	其中可以通过加上target属性决定跳转到新页面的方式

```html
<a href="https://google.com" target="_blank">Google</a> 这样会使链接在新的页面打开
```

##### **target**

该属性指定在何处显示链接的资源。 取值为标签（tab），窗口（window），或框架（iframe）等浏览上下文的名称或其他关键词。以下关键字具有特殊的意义：

- `_self`: 当前页面加载，即当前的响应到同一 HTML 4 frame（或 HTML5 浏览上下文）。此值是默认的，如果没有指定属性的话。
- `_blank`: 新窗口打开，即到一个新的未命名的 HTML4 窗口或 HTML5 浏览器上下文
- `_parent`: 加载响应到当前框架的 HTML4 父框架或当前的 HTML5 浏览上下文的父浏览上下文。如果没有 parent 框架或者浏览上下文，此选项的行为方式与 `_self` 相同。
- `_top`: IHTML4 中：加载的响应成完整的，原来的窗口，取消所有其它 frame。 HTML5 中：加载响应进入顶层浏览上下文（即，浏览上下文，它是当前的一个的祖先，并且没有 parent）。如果没有 parent 框架或者浏览上下文，此选项的行为方式相同_self

#### list标签

​	制表标签，且在文本前方会有一部分空白

![image-20220306133742799](C:\Users\kevin\AppData\Roaming\Typora\typora-user-images\image-20220306133742799.png)

此处是ul的属性，文本前是以点作为表示，而ol属性则是在文本前以数字排序

#### table标签

​	制表格标签

```html
<!--Table-->
     <table>table标签代表表格
         <!--tablehead-->
         <thead>thead代表表头
             <tr>tr是table row就是横行
                 <th>th中就可以填入我们的内容了
                 </th>
             </tr>
         </thead>
         
         <!--tablebody-->
         <tbody>
             <tr>tr意味着一行
                 <td></td>td全称table data即表格数据
             </tr>
         </tbody>
     </table>
```

效果展示

![image-20220306135018238](C:\Users\kevin\AppData\Roaming\Typora\typora-user-images\image-20220306135018238.png)

![image-20220306135103863](C:\Users\kevin\AppData\Roaming\Typora\typora-user-images\image-20220306135103863.png)



