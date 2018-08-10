#### 一、新增语义化标签

```html
<header>头</header>
<nav>导航</nav>
<main>
    <article>左边</article>
    <aside>右边</aside>
</main>
<footer>底部</footer>
```



#### 二、input标签

```html
<!-- 1.Type新增 -->
<!-- tel -->
<input type="tel"/>
<!-- email -->
<input type="email"/>
<!-- url -->
<input type="url"/>
<!-- number -->
<input type="number" max="100" min="0" value="20"/>
<!-- range -->
<input type="range" max="100" min="0" value="40"/>
<!-- Date pickers (date, month, week, time, datetime, datetime-local) -->
<input type="datetime"/>
<!-- search -->
<input type="search"/>
<!-- color -->
<input type="color"/>

<!-- 2.属性新增 -->
<form id="applyForm">
    用户名：<input type="text" name="userName" placeholder="请输入用户名" autofocus autocomplete="on"> <br>
    手机号：<input type="tel" name="telephone" required pattern="^(\+86)?1\d{10}$"> <br>
</form>
<!--提交到指定表单-->
地址：<input type="text" name="address" form="applyForm">

<!-- 3.事件新增 -->
<script>
    document.getElementById("userName").oninput = function(){
        console.log(this.value);
    }
    document.getElementById("telephone").onkeyup = function(){
        console.log(this.value);
    }
    document.getElementById("telephone").oninvalid = function(){
        this.setCustomValidity("请输入正确的手机号");
    }
</script>
```

#### 三、音频视频

```html
<!-- 音频 -->
<audio controls="controls">
  <source src="/i/song.mp3" type="audio/mpeg">
</audio>

<!-- 视频 -->
<video id="video" width="420">
    <source src="/html5/mov_bbb.mp4" type="video/mp4" />
</video>

<script>
function playPause(){ 
	if (myVideo.paused) 
  		myVideo.play(); 
	else 
 		myVideo.pause(); 
} 
</script>
```

#### 四、元素获取

```javascript
document.querySelector("#userName");
document.querySelector("header");
document.querySelectorAll("header")[0];
```

#### 五、元素类样式操作

```javascript
// 添加类样式
document.querySelector("header").classList.add("red");
//删除类样式
document.querySelector("header").classList.remove("red");
//切换类样式
document.querySelector("header").classList.toggle("red");
//是否包含类样式
document.querySelector("header").classList.contains("red");
```

#### 六、自定义属性

```javascript
// 以data-开头
<p data-customName="pName"> 自定义属性 </p>
var p = document.querySelector("p").dataset["customname"];
```

#### 七、网络状态监听

```javascript
window.addEventListener("online",function(){
   alert("网络已链接");
});
window.addEventListener("offline",function(){
    alert("网络已断开");
});
```

#### 八、web存储

```javascript
// sessionStorage 可存储5M
sessionStorage.setItem("userName",name);
sessionStorage.getItem("userName");
sessionStorage.removeItem("userName");
sessionStorage.clear();

// localStorage 可存储20M
localStorage.setItem("userName",name);
localStorage.getItem("userName");
localStorage.removeItem("userName");
localStorage.clear();

// sessionStorage和localStorage区别
sessionStorage：
1、数据存储在当前页面当中，其他页面和浏览器无法获取
2、数据会随着页面关闭自动清除
localStorage：
1、数据存储在本地，统一浏览器可共享数据
2、数据不会随着页面关闭清除

// H5新增应用缓存 cache manifest
<html lang="en" manifest="cache.appcache"> <\html>
    
cache.appcache 文件内容
CACHE MANIFEST
#配置缓存文件清单
CACHE:
1.png

#配置每次都需要从服务器获取的文件清单
NETTWORK:
2.png

#配置无法获取则使用指定文件替换
FALLBACK:
3.png 4.png

```
