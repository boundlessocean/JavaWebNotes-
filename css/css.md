#  CSS

[TOC]



![css](css.png)

#### 1.css 与HTML结合方式
    css文件与HTML分离开，在HTML head 中导入css
    1.在标签中加入css
    2.在head中 <style type="text/css"> CSS </style>
    3.@import 方式，不推荐
    4.链接文件 <link rel="stylesheet" type="text/css" href="css文件路径">

#### 2.css基本选择器
     1.标签选择  标签 {css样式}
     div {
     background-color: aquamarine;
     }
     
     2.class选择器 标签.class {css样式}
     .aa {
     background-color: antiquewhite;
     }
     
     3.id选择器 标签#id {css样式}
     #dd {
     background-color: brown;
     }
    
     4.多类名选择器
     nameA 和 nameB以空格隔开
     <div class="nameA nameB">

#### 3.css扩展选择器
    1.关联选择器 标签中的标签 div中的p标签
    div p.p1{
    background-color: yellow;
    }
    
    2.组合选择器 标签组合 div和p都使用一种
    div,p{
    background-color: darkred;
    }
    
    3.伪累选择器
    * 超链接状态
    原始  :link
    悬停  :hover
    点击  :active
    点击之后    :visited

#### 4.盒子模型
```
1.边框 border:2px solid red;
border-top  border-bottom   border-left border-right

2.内边距 padding:20px
padding-top padding-bottom  padding-left padding-right

3.外边距 margin:20px
margin-top margin-bottom  margin-left margin-right

4.垂直居中
line-height: 与标签height相同时垂直居中;

5.连写
padding: 10px //上下左右都是10
padding: 10px 20px //上下10 左右20 
padding: 10px 20px 30px //上10 左右20 下30

6.盒子水平居中
margin: 0 auto;

7.清除标签默认内外边距
* {
    padding: 0;
    margin: 0;
}

8.两个问题
 外边距合并 ：使用margin定义块元素的垂直外边距时，可能会出现外边距的合并，无法避免。相邻的两个标签只取边距最大的值，不会叠加。
 嵌套标签垂直外边距合并：两个嵌套关系的标签，如果父标签没有上边距及边框，则父标签的上边距会与子标签的上边距发生合并，合并后的外边距为两者中较大者，即使父标签的上边距为0，也会发生合并。解决方案：
 1.为父标签定义1px的上边框或上内边距
 2.可以为父标签添加 overflow:hidden
 
9.圆角
 border-radius: 50%; // 
 border-radius: 10px 0px; // 上左，下右10px  上右，下左0px
 
10.阴影
 box-shadow: 水平阴影 垂直阴影 模糊距离 阴影尺寸 阴影颜色 内外阴影;
11.动画
 transition: all 0.5s
 
12.清除浮动
 // 其他浏览器
  .clearfix:after {
      content: "";
      display: block;
      height: 0;
      clear: both;
      visibility: hidden;
  }
  // ie6
  .clearfix {
      /*zoom 1 ie6清除浮动的方式 *ie7以下的版本才能识别*/
      *zoom: 1; 
  }
```

#### 5.布局漂浮
    float   left：后面的div到右边   right：后面的div到左边
    #aa {
    float: left;
    width: 13%;
    }

#### 6.布局定位（漂浮）
    position
    absolute   从文档流中拖出,以当前屏幕为基准点，上下左右对齐,如果父标签有漂浮，则以父元素边界对齐
    relative   不会从文档流中拖出
    
    #aa {
    position: absolute;
    left: 20px;
    top: 20px;
    }
    
    配合：子绝（absolute）父相（relative）
    
    优先级
    同级标签漂浮越靠后的标签优先级越高
    z-index: 1; 主动修改标签的优先级别，数值越大，优先级越高

#### 7.固定定位

```
固定屏幕位置不动
```





#### 8.标签显示模式转换

```
块砖行内 display:inline
行内转块 dispaly:block
块、行内转行内块 dispaly:inline-block
```



1. ##### 块标签

   ```
   独占一行
   常见的块标签：
   <h1>~<h6> <p> <div> <ul> <ol> <li>
   ```

2. ##### 行内标签

   ```
   不独占区域，仅仅靠自身的字体大小和图像尺寸支撑结构，一般不可以设置宽度、高度、尺寸、对齐等属性，常用于控制页面中文本样式
   常见的行内标签：
   <a> <strong> <b> <em> <i> <del> <s> <ins> <u> <span>
   ```

3. ##### 行内块

   ```
   特点：
   1.和相邻元素在一行，但是之间会有空白间隙
   2.默认宽度就是它本身内容的宽度
   3.高度、行高、外边距、内边距都可以控制

   <img/> <imput/> <td>
   ```

   ​

#### 9. CSS三大特性

> 层叠性
>
>  继承性
>
> 优先性



#### 10. 背景

```
// 1.background-repeat 显示模式
background-position: center;
// 2.background-position: x y;  x,y取值Top，left，right，bottom，center。也可以是具体的值，如 20px
background-repeat: no-repeat;
// 3.background-attachment: fixed固定 scroll滚动
background-attachment: fixed;
// 4.背景连写 background: 颜色 URL 显示模式 attahed 位置 
// 顺序无强制要求
background: orangered url(1.png) no-repeat fixed center top;
```



#### 11. 标签显示与隐藏

```
display: none; 隐藏后不占位置
visibility: hidden; 隐藏后占位置
visibility: visible; 显示标签
```



#### 12.overflow

```
溢出部分的处理
visible|hidden|scroll|inherit
visible : 显示
hidden  : 隐藏
scroll 	: 滚动显示
inherit : 继承父类

文字溢出部分：
clip|ellipsis
text-overflow: overflow;// 省略号
white-space: nowrap; // 配合单行显示使用
```



#### 13.鼠标样式

```
default|text|pointer|move
cursor: pointer; 小手样式
```



#### 14.文字对齐

```
baseline|top|baseline|bottom
vertical-align: middle;
```



#### 15.图标字体

```css
/* 准备工作
1.下载字体
2.font文件夹导入项目
*/

/* css文件中 */
 @font-face {
     font-family: 'icomoon';
     src:  url('../fonts/icomoon.eot?lmqzz3');
     src:  url('../fonts/icomoon.eot?lmqzz3#iefix') format('embedded-opentype'),
     url('../fonts/icomoon.ttf?lmqzz3') format('truetype'),
     url('../fonts/icomoon.woff?lmqzz3') format('woff'),
     url('../fonts/icomoon.svg?lmqzz3#icomoon') format('svg');
     font-weight: normal;
     font-style: normal;
 }

[class^="icon-"], [class*=" icon-"] {
     /* use !important to prevent issues with browser extensions that change fonts */
     font-family: 'icomoon' !important;
     speak: none;
     font-style: normal;
     font-weight: normal;
     font-variant: normal;
     text-transform: none;
     line-height: 1;
     /* Better Font Rendering =========== */
     -webkit-font-smoothing: antialiased;
     -moz-osx-font-smoothing: grayscale;
 }

 .icon-connection:before {
     content: "\e91b";
     font-size: 25px;   /* 调整大小 */
     color: #2288f6;	/* 调整颜色 */
 }
```



```html
<!-- HTML使用 -->
<span class="icon-connection"> </span>
```



#### 16. CSS Reset 类库，为跨浏览器兼容做准备

normalize.css 很小的css文件，在默认的HTML元素样式上提供了跨浏览器的高度一致

Normalize.css 是一种现代的、为HTML5准备的优质替代方案，现在已经被用于非常多的框架、网站、工具上。



#### 17.ico图标

```html
<link rel="shortcut icon" href="favicon.ico" type="image/x-icon"/>
```











