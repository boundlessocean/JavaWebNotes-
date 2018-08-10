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

