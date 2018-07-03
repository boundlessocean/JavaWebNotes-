> 优点：写得少，做得多，体积小，功能强，链式编程，隐式迭代，插件丰富

#### 一 、jQuery 选择器

```javascript
// 1.基本选择器
$("#id"); 			//ID选择器 
$(".class") 		//类选择器
$("div"); 			//标签选择器
$("p,.class,#id");  //并集选择器
$("div.class");		//交集选择器

// 2.层级选择器
$("#dv p") 			//获取div中的所有p标签 
$("#dv>p")			//获取div中的子p标签
$("#dv~p")			//获取div中的兄弟p标签 = $("#dv").siblings("p")
$("#dv+p")			//获取与div相邻的p标签

// 3.索引选择器
$("#dv>p:eq("+i+")")	//eq:index 代表获取所有p标签中第index个p标签
$("#dv>p:lt("+i+")")	//小于i的p标签
$("#dv>p:gt("+i+")")	//大于i的p标签
$("#dv>p:gt("+i+"):lt("+y+")") //大于i的p标签中挑选出小于y的p标签
// 4.过滤选择器
$("p").prev();		//当前元素的前一个兄弟元素
$("p").prevAll();	//当前元素的前面所有元素
$("p").next();		//当前元素的后一个元素
$("p").nextAll();	//当前元素的后面所有元素
$("p").parent()		//当前元素的父级元素

```

#### 二、常用方法

```javascript
/* 
.val(); 标签的value属性值
.text();标签文本内容（innerText）
.attr("id"); 获取对象指定属性
.css(); 标签css样式
.html();标签中的HTML内容
.show();标签显示，括号内数值代表毫秒
.hide();标签隐藏，括号内数值代表毫秒
.stop();停止当前动画
*/
```

#### 三、jQuery和DOM对象互转

```javascript
$("#btn")[0]  //dom对象
$("#btn") //jquery对象
$(document.getElementById("btn"))  //jquery对象
```

#### 四、jquery 中初次加载事件

```javascript
// jquery 中初次加载事件的3种方式
$(window).load(function(){
    console.log("初次加载1....");
});
$(document).ready(function(){
    console.log("初次加载2....");
})
$(function(){
    console.log("初次加载3....");
});
$("#dv").mouseenter(function(){
    console.log("鼠标进入....");
});
$("#dv").mouseleave(function(){
    console.log("鼠标离开....");
});
```

#### 五、jQuery中CSS样式

```javascript
// 1.普通方法
$("#dv").css("width","200px");
$("#dv").css("height","200px");
$("#dv").css("backgroundColor","red");
// 2.链式编程方法
$("#dv").css("width","200px").css("height","200px").css("backgroundColor","red");
// 3.json方法
$("#dv").css({"width":"200px","height":"300px","backgroundColor":"yellow"});
// 4.上左宽高操作
$("#dv").width(100).height(100).offset({"left":100,"top":100});
// 5.操作类
$("#dv").addClass() 	//添加类样式
$("#dv").toggleClass()	//切换类样式
$("#dv").hasClass()		//是否有类样式
$("#dv").removeClass()	//移除类样式
```

#### 六、jQuery中的动画

```javascript
$("#dv").show(200,function(){
    alert("显示完了");
});
$("#dv").slideDown(200,function(){
    alert("显示完了");
})
$("#dv").fadeIn(200,function(){
    alert("显示完了");
})


$("#dv").slideToggle(200,function(){
   alert("隐藏了");
});
$("#dv").fadeOut(200,function(){
    alert("显示完了");
});
$("#dv").fadeToggle(200,function(){
    alert("显示完了");
});
$("#dv").slideUp(200,function(){
    alert("显示完了");
});
$("#dv").hide(200,function(){
    alert("显示完了");
});

/**
 * animate(prop, speed, easing, callback)
 * prop css属性（必须）
 * speed 速度（可选）
 * easing 默认 swing(缓慢) linear(匀速)
 * callback 回调
 */ 
$("#dv").animate({"width":"100px","height":"100px"},300,function(){
    alert("执行完了");
});
```

#### 7、jQuery创建标签与移除

```javascript
// dv中添加元素
$("#dv").append($("<p>动态添加</p>"));
$("<p>动态添加</p>").appendTo( $("#dv"));
// dv中覆盖其他元素
$("#dv").html("<p>动态添加</p>");
// 在dv中第一个元素前面添加元素
$("#dv").prepend("<p>动态添加</p>");
$("<p>动态添加</p>").prependTo($("#dv"));
// dv标签后面添加元素作为兄弟元素
$("#dv").after("<p>动态添加</p>");
// dv前面添加元素
$("#dv").before("<p>动态添加</p>");

// 移除元素
$("#dv").html("");
$("#dv").remove();
$("#dv").empty();
```



#### 8、jQuery标签 绑定／解绑 事件

```javascript
// 绑定事件
$("#dv").click(function(){});
$("#dv").bind("click",function(){});
$("#dv").delegate("p","click",function(){});
$("#dv").on("click","p",function(){});

// 解绑事件
$("#dv").unbind(); // 解绑全部事件
$("#dv").unbind("click");
$("#dv").unbind("click mouseenter mouseleave");
$("#dv").undelegate("p","click");
$("#dv").off() //解绑所有父级子级事件
$("#dv").off("click");
$("#dv").off("click mouseenter mouseleave");
$("#dv").off("","p"); //解绑p的所有事件
$("#dv").off("click","p"); //解绑p的click事件
$("#dv").off("click mouseenter mouseleave","p");
$("#dv").off("click", "**"); //解绑div子元素的点击事件

```



#### 9、jQuery阻止事件冒泡

```javascript
$("#dv").click(function(){
    return false;
});
```

#### 10、事件触发

```javascript
$("#dv").focus();
$("#dv").trigger("focus");
// 只触发事件的处理，不触发事件默认行为
$("#dv").triggerHandler("focus");
```

#### 11、键盘输入

```javascript
$("document").keydown(function (e){
    console.log(e.keyCode);
})

$("document").mousedown(function (e){
    console.log(e.altKey);
    console.log(e.shiftKey);
    console.log(e.ctrlKey);
});
```

#### 12、数组遍历

```javascript
$("input").each(function(index,ele){
    console.log("index = "+index + "\n els=" +ele);
});
```

#### 13.让权

```javascript
//MY替代$
var MY = $.noConflict();
```

#### 14.宽高属性

```javascript
// 包含内边距的宽高
$("#dv").innerHeight();
$("#dv").innerWidth();
// 包含内边距、边框的宽高
$("#dv").outerHeight();
$("#dv").outerWidth();
// 包含内边距、边框、外边距的宽高
$("#dv").outerHeight(true);
$("#dv").outerWidth(true);
```

