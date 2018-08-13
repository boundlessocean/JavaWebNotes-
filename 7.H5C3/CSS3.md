#### 一、属性选择器操作

```css
/* 相同 */
li[class=a]{
    font-size: 40px;
}
/* 包含 */
li[class*=ound]{
    color: #2288f6;
}
/* 开头 */
li[class^=c]{
    color: aqua;
}
/* 结尾 */
li[class$=f]{
    color: aquamarine;
}
```

####  二、阴影

```css
/* 语法 */
box-shadow: h v blur spread color inset,h v blur spread color inset...
text-shadow: h v blur color
h:水平阴影偏移值
v:垂直阴影偏移值
blur:模糊尺寸（可选）
spread:阴影尺寸（可选）
color:颜色
inset:内阴影／外阴影（可选）
box-shadow: 5px 5px 5px 0px grey;
```



#### 三、渐变色

```css
/* 线性渐变 */
background: linear-gradient(to right,yellow,red);
/* 径向渐变 */
background: radial-gradient(at center,red,yellow);
```



#### 四、图片处理

```css
/* 设置100px 默认宽度为100px，高度自适应 */
background-size: 100px;	
/* contain 图片会根据容器宽高中比例最小的自适应 */
background-size: contain;
/* cover 图片会根据容器宽高中比例最大的自适应 配合center显示浏览器效果*/
background-size: cover;
background-position: center;
/*
content-box : 从内容位置开始填充
border-box  : 从边框位置开始填充
padding-box : 从间距位置开始填充
用于图片裁剪，扩充事件区域
*/
background-origin: border-box;
background-clip: content-box;

/*  边框图片（点九图） */
/*
border-image: source slice / width / outset repeat
border-image-source: url(1.jpg); 地址
border-image-slice: 27 fill;	 设置四个方向裁剪距离。fill：内容内部填充
border-image-width: 27px;		 边框图片宽度，默认为原始边框宽度，可不设置
border-image-outset: 0px;		 扩展边框
border-image-repeat: stretch;	 平铺方式
*/
border: 27px solid red;
border-image: url(1.jpg) 27 fill / 27px / 0px round;

```



#### 五、tranlate、tranform2d

```css
/* 动画 */
transition: left 10s linear 0s;
/* 时长 */
transition: transform 2s;
/* 旋转锚点 */
transform-origin: bottom right;
/* 平移 */
transform: translate(500px,500px) 
/* 缩放 */
transform: scale(2.0)
/* 旋转 */
transform: rotate(90deg);
/* 斜切 */
transform: skew(90deg);
/* 元素居中 */
transform: translate(-50%,-50%);
```

