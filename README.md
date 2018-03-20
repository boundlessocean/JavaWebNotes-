# JavaWebNotes
### 一、HTML 超文本标记语言-网页语言
#### ——规范：
> 1.一个HTML文件要有开始和结束标签 <html> </html>

> 2.HTML包含两部分

    (1). <head> 设置相关信息</head>
    (2). <body> 页面内容</body>
    (3). 标签有开始要有结束
    (4). 不区分大小写
    (5). 有些标签没有结束标签，在标签内结束 <br/> <hr/>

#### ——标签
##### 1.标题标签
    //(范围1～6)
    <h1>标题标签</h1>

1).
##### 2.
    <hr size=“1” color=“red”/>   水平线标签
##### 3.列表标签
	<dl>
          <dt>成都</dt>
          <dd>武侯区</dd>
          <dd>高新区</dd>

          <dt>深圳</dt>
          <dd>宝安区</dd>
          <dd>南山区</dd>
        </dl>

##### 4.有序列表标签
        <ol type="a">
            <li>武侯区</li>
            <li>高新区</li>
            <li>天府新区</li>
        </ol>
##### 5.无序标签
       <ul type="square">
            <li>武侯区</li>
            <li>高新区</li>
        </ul>
##### 6.图像标签
	<img src="recativecocoa.png" width="1200" height="400" alt=“图片描述"/>
	路径：
	1.绝对路径
	2.相对路径
		<img/image.png>   文件夹下层的目录
		<../image.png> 文件夹上层目录
##### 7.链接标签
        <a href="资源路径" target="_blank" >百度一下</a>
	target：打开方式，默认当前页面
	— _blank: 新窗口打开
	— _self: 当前页打开，默认
	<a href=“#" target="_blank" >百度一下</a> #代表不需要连接到任何地址









##### 1.特殊字符处理
	* < &lt
	* > &gt
	* 空格 &nbsp
	* & &amp
