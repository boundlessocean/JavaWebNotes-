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



