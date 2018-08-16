#### 一、包

```javascript
<script src="https://cdn.bootcss.com/vue/2.2.2/vue.min.js"></script>
```

#### 二、语法

```html
<!-- 1.插值表达式 -->
<div id="vue_div_test">
	{{name+age+work()}}
</div>

<!-- 2.v-text -->
<!-- 3.v-cloak -->
<p v-text="name+age"></p>

<!-- 4.v-html -->
<p v-html="message"></p>

<!-- 5.v-bind 缩写 : -->
<!-- 6.v-on 缩写 @ -->
<input type="button" :value="value" id="app" @click="show">
```

```javascript
new Vue({
  	el: '#app',
  	data:{
		value:"提醒",
  	},
  	methods: {
  		show : function(){
  		alert('立即进入战备状态')
  	}}
});
```

