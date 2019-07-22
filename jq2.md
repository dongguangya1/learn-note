###jQuery其他选择器
###层级选择器
+ $("div span").css('bgc','red');
// 后代选择器 选择所有的后代选择器
+ $('div>span').css('bgc','red');
// 子代选择器 选择所有的子代元素
+ $('div+p').css('bgc','red');
// 紧邻选择器 选择紧挨着的下一个元素
+ $('div~p').css('bgc','red');
// 兄弟选择器 选择后面的所有的兄弟元素
###过滤选择器
+ $(“li:eq(1)”). css(“background”,”red”)
// index是从0开始的一个数字，选择序号为index的元素。选择第一个匹配的元素。
+ $(“li:gt(2)”). css(“background”,”red”)
// Index 是从0开始的一个数字，选择序号大于index的元素
+ $(“li:lt(2)”). css(“background”,”red”)
// Index是从0开始的一个数字，选择小于index 的元素
+ $(“li:odd”). css(“background”,”red”)
// 选择所有序号为奇数行的元素
+ $(“li:even”). css(“background”,”red”)
// 选择所有序号为偶数的元素
+ $(“li:first”). css(“background”,”red”)
// 选择匹配第一个元素
+ $(“li:last”). css(“background”,”red”)
// 选择匹配的最后一个元素
###属性选择器
+ $('a[href]').css('bgc','red');
// 选择所有包含href属性的元素
+ $("a[href='baidu']").css('bgc','red');
// 选择href属性值为baidu的所有a标签
+ $("a[href!='baidu"]').css('bgc','red');
// 选择所有href属性不等baidu的所有元素 包括没有href的元素
+ $("a[href^='wed']").css*('bgc','red');
// 选择所有以wed开头的元素
+ $("a[hrefS='cn']").css('bgc','red');
// 选择所有以cn结尾的元素
+ $("a[href*='i']").css('bgc','red');
// 选择所有包含i这个字符的元素 可以是中英文
+ $("a[href][titde='内容']").css('bgc','red');
// 选择所有符合指定属性规则的元素 都符合才会被选中
### 筛选选择器
+ $(“#j_wrap”).find(“li”).css(“color”, “red”);
// 选择id为j_wrap的所有后代元素li
+ $(“#j_wrap”).children(“ul”).css(“color”, “red”);
// 选择id为j_wrap的所有子代元素ul
+ $(“#j_liItem”).siblings().css(“color”, “red”);
// 选择id为j_liItem的所有兄弟元素
+ $(“#j_liItem”).parent(“ul”).css(“color”, “red”);
// 选择id为j_liItem的父元素
+ $(“li”).eq(2).css(“color”, “red”);
// 选择所有li元素中的第二个
+ mouseover :鼠标经过的时候会触发多次
+ mouseenter :鼠标经过的时候只会触发一次                       
### jQuery动画
#### 隐藏显示动画
##### show方法
+ $(xx).show(2000)
+ $(xx).show() slow:600ms.normal:400ms.fast:200ms
+ $(xx).show(2000,function(){})
+ $(xx).show()
##### hide方法
+ 作用:让匹配元素隐藏掉
+ 用法参考show方法
#### 滑入滑动动画
+ $(xx).slideDown(speed,callback);
// 滑入动画效果
+ $(xx).slideToggle(speed,callback);
// 滑入滑出切换动画效果
#### 淡入淡出动画
+ $(xx).fadeIn(speed, callback);
// 淡入动画效果
+ $(xx).fadeOut(1000);
// 淡出动画效果
+ $(xx).fadeToggle('fast',function(){});
// 淡入淡出切换动画效果
+ $(xx).fadeTo(1000, .5); //  0全透，1全不透
// 改变透明度到某个值
#### 自定义动画
+ 语法：$(selector).animate(styles,speed,easing,callback)
+ 第一个参数表示：要执行动画的CSS属性（必选）
+ 第二个参数表示：执行动画时长（可选）
+ 第三个参数表示：动画执行完后立即执行的回调函数（可选）
#### 停止动画
+ stop(): 停止当前正在执行的动画
+ stopAll: 是否全部停止,默认false 停止队列中所有的动画
+ goToEnd: 是否将停止的动画 停止在当前动画的最后一个状态
