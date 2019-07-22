### JavaScript组成
+ 由三部分组成 
1. ECMAScript
2. DOM
3. BOM
### 事件三要素
+ 事件源 事件 事件驱动程序
+ 事件源 :引发后续事件的html标签.
+ 事件 :js已经定义好了
+ 事件驱动程序 :对样式和html的操作,也就是DOM
###代码书写步骤
+ 获取事件源:document getElementByld('box');
+ 绑定事件:事件源box 事件onclick=function(){事件驱动程序};
+ 书写 事件驱动程序 : 关于DOM的操作

简单的代码举例:(点击box,然后弹框)
~~~
<body>
    <div id='box'></div>
    // 建立一个div id属性等于box
    <script type='text/javascript>
    // 获取事件源
        var div = document.getElementById('box');
        div.onclick = function(){
        //书写驱动程序
            alert('我是弹出的内容');
        };
    </script>
</body>
~~~
### 获取事件源的方式
+ var div1 = document.getElementById('box1');
// 通过id获取单个标签
+ var arr1 = docment.getElementsByTagName('div')
// 通过标签名获得标签数组 所以有s
+ var arr2 = document.getElementsByClassName('he')
// 通过 类名获得标签数组 所以有s

### 绑定事件的方式
~~~
<div id = 'box'>
<script type='text/javaascript'>
var div = document.getElementById('box');
div.onclick = function(){
// 鼠标点击    封装函数
    alert('我是弹出的内容)
};
</script>
~~~
### 事件驱动程序
+ 鼠标点击时 原本粉色div变大 背景变红
~~~
<script type='text/javascript'>
    var div1 = document.getElementById('box1');
    div1.onclick = function(){
        div1.style.vidth = '200px';
        div1.style.height = '200px';
        div.style.backgroundColor = 'red';
    鼠标点击时 宽变成200px;高变成200px; 背景颜色改为红色    }
    </script>
~~~
+ onload 所有页面加载完毕的时候 在执行onload事件
### JQ基础
+ ">" 子代选择器 选择所有子代
+ "+" 紧邻选择器 下一个元素
+ "~" 兄弟选择器 后面所有元素
+ (index) 是序号 索引
+ 标签名: eq 选择器第一个元素索引[0,1,2,3,4,5]
+ 标签名: gt 选择大于索引的所有元素[3]>[4,5]
+ 标签名: lt 选择小于索引的元素[3]<[0,1,2]
+ 标签名: odd 选择序号为基数的元素[1,3,5]
+ 标签名:even 选择序号为偶数的元素[2,4]
+ "first" 选择第一个元素
+ "last" 选择最后一个元素
### 选择器
+ class选择器
+ id选择器
+ 标签选择器
+ 并集选择器
+ 交集选择器
### 使用方法
+ $('.box').css('color','red');
// 选择.box标签 属性 修改他的颜色
+ $('.box.inner-box').css('color','red');
// 选择.box下面的.inner-box标签 属性 修改他的颜色
+ $('.box.active').css('bgc','red');
// 既有.box 也有.active 属性 修改他的颜色
+ $('.box>.w').css('bgc','red')
// .box下的所有子代 属性 修改颜色
+ $('.li3+li').css('color','red');
// li3下一个元素 属性 修改颜色
+ $('.li3~li').css('color','red');
// li3下的所有元素 属性 修改颜色
+ $('li:eq(4)').css('color','red');
// eq索引第4位 属性 修改颜色
+ $('li:gt(2)').css('color','red');
// gt索引比第2个大的值 属性 修改颜色
+ $('li:lt(2)').css('color','red');
// lt索引比第二个小的值 属性 修改颜色
+ $('li:odd').css('color','red');
// 为奇数的值  属性 修改颜色
+ $('li:even').css('color','red');
// 为偶数的值 属性 修改颜色
+ $('li:first').css('color','red');
// 第一个值  属性 修改颜色
+ $('li:last').css('color','red');
// 最后一个值  属性 修改颜色
### DOM的介绍
+ DOM 都是由节点组成
+ 元素节点:html标签
+ 文本节点:标签中的文字(比如标签之间的空格,换行)
+ 属性节点:标签的属性
+ 整个html 文档就是一个文档节点,所有的节点都是Object.
###DOM创建节点
+ 新的标签(元素节点) = document.createElement('标签名');
+ 比如 如果我们想创建一个 li标签,或者是创建一个不存在的adbc标签,可以这样做:
~~~
<script type="text/javascript">
	var a1 = document.createElement("li"); //创建一个li标签
	var a2 = document.createElement("adbc"); //创建一个不存在的标签

	console.log(a1);
	console.log(a2);

	console.log(typeof a1);
	console.log(typeof a2);
</script>
~~~
### 插入节点
 + 父节点.appendChild(新的子节点);
 // 解释:父节点的最后插入一个新的子节点
 //在参考节点前插入一个新的节点
 //如果参考节点为null,那么他将在节点里面的最后插入一个子节点
 ~~~
 btn.onclick = function() {
	box.appendChild(imgEl);
	// 同一个节点 只能 添加一次
	// box.appendChild(imgEl);
	// box.appendChild(pEl);
	// 使用方法：父节点.insertBefore(要插入的节点，参考节点)；
	box.insertBefore(pEl, imgEl);
	// 如果参考节点为null，那么他将在节点最后插入一个节点。
};
~~~
###删除节点
+ 要复制的节点.cloneNode();
//括号里不带参数和参数false,效果是一样的
//不带参数/带参数false:只复制节点本身,不复制子节点.
+ 要复制的节点.cloneNode(true);
//带参数true:即复制节点本身,也复制其所有的子节点.
###设置节点的属性
+ 我们可以获取节点的属性值 设置节点的属性值 删除节点的属性
~~~
<img src="images/1.jpg" class="image-box" title="美女图片" alt="地铁一瞥" id="a1" />
~~~
//添加图片 添加class类名 添加鼠标放上去显示美女图片 添加alt如果无法显示图像，浏览器将显示替代文本，添加id属性类名
### jQuery节点操作
##### 创建元素
+ var node = $(“#box1”).html（“<li>我是li</li>”）；
##### 添加元素
+ 在元素的最后一个子元素后面追加元素
+ append():在被选元素内部的后面一个子元素后面插入内容
+ appendTo():把$(selector)追加到node中去 $(selector).appendTo(node);
+ prepend():在元素的第一个子元素前面追加内容或节点$(selector).prepend(node);
+ after():在备选元素之后,作为兄弟元素插入内容或节点$(selector).after(node);
+ before():在被选元素之前,作为兄弟元素插入内容或节点 $(selector).before(node);
##### 清空元素
+ $(selector).empty(); 
+ $(selector).html(“”);
+ $(selector).remove(); 把自己也给删掉
##### 复制元素
+ $(selector).clone();
// 复制 selector元素里面的

