###  什么是自面量
 +  字面量的意思有两种 :一是数字 ,二是字符串.
 +  数值的字面量 直接写到里面就可以  也不需要任何符号,
 + 字符串的字面量也很简单,但一定要加上引号,可以是单词,句子等.
 + 100 是数字 "100"是字符串
 ###  变量的命名规范
 + 只能有英文 字母 下划线 和美元符号就可以 但是不能用数字开头 而且还不能用JS保留字 大小写严格区分  A 和 a 是两个变量.
 + var a =100   等于一个变量
 + var A =100   等于另一个变量
 ###  变量命名的规则 :
 + 变量名命名必须以字母或是下标符号"_"或者"$"为开头
 + 不能以数字开头
 + 不能是JS中的关键字和保留字
 + 严格区分大小写
 + 建议用驼峰命名规则
 + 见名如意
 ###  比较运算符
 + <> 大小于号
 + == 等于号
 + ===全等于
 + !=不等于
 + !==不全等于
 ##  date对象的用法
 ~~~ 
 var obj = {
        name:'张三',
        sex:'男',
        age:24, 
        say:function(){
            alert('你好')
        }
 }
 //获取对象的属性 对象名如
 console.log(obj.name);
 //获取obj里面的属性值 张三
 console.log(obj.sex);
 //获取obj里面的属性值 男
 comsole.log(obj.say);
 //获取obj里面的say函数
 ~~~
 + JS的内置对象 Date  Math
 + var date =new Date(); 这句话代码执行时:当前的时间对象
 + console.log(date);
 + var date1 =new Date(2017/09/06);给当前元素赋值时间  则显示的也是赋值的时间
 + console.log(date1) 
 + var year = date.getFullYear();获取年份
 + console.log(year);
 + var month = date.getMonth()+1;获取月份 0-11  0代表1月
 + console.log(month); 6代表7月
 + var day = date.getDate(); 获取日1-31日
 + console.log(day);
 + var weekDay = date.getDay();获取星期 0代表周日 1代表周1
 + console.log(weekDay);
 + var hour = date.getHours(); 获取小时0-23
 + var min =date.getMinytes(); 获取分钟0-59
 + var second =date.getSeconds(); 获取秒0-59
 + var mSecond = date.getMilliseconds();获取毫秒1s-1000ms;


  ##  Math对象的用法
 + Math abs() 返回绝对值
 + Math floor() 向下取整(向小取)
 + Math ceil() 向上取整(向大取)
 + Math round() 正数四舍五入 负数五舍六入
 + Math random() 生成0-1之间的随机数
 + Math max(x,y,z) 返回多个数中的最大值
 + Math min(x,y,z) 返回多个树种的最小值
 + Math pow(x,y)返回x的y次幂
 + Math sqrt() 对一个数进行开方运算
 ~~~
  console.log(Math.round(2.4)); // 2
        console.log(Math.round(2.9)); // 3
        console.log(Math.round(2.4999999999)); // 2
        console.log(Math.round(2.499999999999999999999999999999999999)); // 3
        // 存在误差
        console.log(2.499999999999999999999999999999999999); // 2.5
~~~
 
 + Math 和其他的对象不同,他不是一个构造函数,不需要创建对象

##  逻辑运算符
+ 逻辑运算符有三个:
+ && 与(且):两个都为真,结果才为真.
+ ||  或:只要一个是真,结果就是真.
+ ! 非:对一个布尔值进行取反.
##  if语句
+ if语句有以下三种
+ 条件判断语句:条件成立才执行, 如果条件不成立,那就什么都不做.
+ 条件分支语句: else if
+ 语句的跳楼现象
+ if语句的嵌套
~~~
 // 一个加油站为了鼓励车主多加油，所以加的多有优惠。
        // 92号汽油，每升6元；如果大于等于20升，那么每升5.9；
        // 97号汽油，每升7元；如果大于等于30升，那么每升6.95
        // 编写JS程序，用户输入自己的汽油编号，然后输入自己加多少升，弹出价格。
        var type = prompt('请输入汽油编号(92或者97):');
        var num = prompt('请输入加油的数量:');
        var price;
        if (type === '92') {
            if (num >= 20) {
                price = num * 5.9;
                alert(price);

            } else {
                price = num * 6;
                alert(price);
            }
        } else if (type === '97') {
            if (num >= 30) {
                price = num * 6.95;
                alert(price);
            } else {
                price = num * 7;
                alert(price);
            }
        } else {
            alert('请输入正确的汽油编号');
        }
~~~
##  三元运算符
+ 语法表达式:如果表达式结果为 true 执行这里的代码; 如果表达式结果为false 执行冒号后面的代码;
~~~
  var a =5 > 3 ? 5 :3;
  console.log(a);
  var mun = 30;
  var price = mun > 20 ? 5.9 : 6;
~~~
##  switch 语句(条件分支语句)
~~~
switch(表达式){
    case 值1:
            语句体1;
          break;
    case 值2:
             语句体2;
          break;
    default:
            语句体 n+1
            break;
}
~~~
+ 备注 1 :当所有的比较结果都为false时 则只执行 default里面的语句.
+ 备注 2 :break 可以省略,但一般不建议.否则结果可能不是你想要的
###  syitch 语句的执行流程
+ 首先 计算出表达式的值,和case依次比较 一旦有对应的值 就会执行相应的语句,在执行的过程中,遇到break就会结束.
+ 然后如果所有的case都和表达式的值不匹配,就会执行,就会执行 default 语句体部分,然后程序结束掉.
###  switch 语句的结束条件
+ 情况1: 遇到break就会结束,而不是遇到default就结束.(因为break在此处的作用就是退出switch语句)
+ 情况2: 执行到程序的末尾就结束.
~~~
var num = 4;

//switch判断语句
switch (num) {
	case 1:
		console.log("星期一");
		break;
	case 2:
		console.log("星期二");
		break;
	case 3:
		console.log("星期三");
		break;
	case 4:
		console.log("星期四");
	//break;
	case 5:
		console.log("星期五");
	//break;
	case 6:
		console.log("星期六");
		break;
	case 7:
		console.log("星期日");
		break;
	default:
		console.log("你输入的数据有误");
		break;
}
~~~
##  for 循环
+ for(var a=1; a<=100; a++){
    console.log(a);
}
###  while 循环
~~~
var mun =10;
while (num > 0){
    console.log(num);
    num--;
    if(num ===7){
        break;
    }
}
// 10 9 8 7 6 5 4 3 2 1
// 10 9 8
var count = 10;
do{
    console.log(count);
    count--;
} while(count > 0)
// 10 9 8 7 6 5 4 3 2 1
//这两个语句的功能类似,不同的是;
while 是先判断后执行 而 do...while 是先执行后判断
//也就是说, do...while 可以保证循环体至少执行一次,而while不可以
var a= -1;
//例如 do{
    console.log(a);
    a--;
}while(a > 0)
-1
while(a > 0){
    console.log(a);
    a--;
}
~~~
##创建数组对象
+ 方式一 字面量定义 举例: var arr=[1, 2, 3];
+ 方式二 对象定义(数组的构造函数).举例: var arr1 =new Array()
+ 数组通过索引(下标)获取元素
+ console.log(arr1)
+ console.log(arr[2]); 通过索引找到2;
+ 添加元素 通过下标
+ arr1[0] = 10;
+ arr1[1] = 20;
+ arr1[2] = 30;
+ arr1[4] = 50;
+ console.log(arr1);
+ 修改元素
+ arr[0] = 10;
+ console.log(arr);
+ length属性 数组元素的个数
+ var arr =[15, 25, 35];
+ console.log(arr.length)
+ //则这个数值个数为3 
+ var arr1 =[1, 2, 3, 4, 5,];
+ arr1.length = 4;
+ //如果 设置length为4 那这个数组元素的个数为4;
## 遍历数组元素
~~~
var arr = ["张三", "john", "李四", "王五"];
// 1. for循环
for (var i = 0; i < arr.length; i++) {
	console.log(arr[i]);
}
// 2. for in
for (var key in arr) {
	console.log(arr[key]);
}
~~~
##  数组的基本方法
### push
+ push():向数组的后面插入一个或者多个元素 来组成新的长度;
~~~
var arr = ["王一", "王二", "王三"];

var result1 = arr.push("王四"); // 末尾插入一个元素
var result2 = arr.push("王五", "王六"); // 末尾插入多个元素

console.log(result1); // 打印结果：4
console.log(result2); // 打印结果：6
console.log(arr); // 打印结果：["王一","王二","王三","王四","王五","王六"]
~~~
### pop
+ pop():删除一个数组中的最后一个元素,返回结果为被删除的元素.
~~~
var arr = ["王一", "王二", "王三"];

var result1 = arr.pop();

console.log(result1); // 打印结果：王三
console.log(arr); // 打印结果：["王一","王二"]
~~~
### unshift
+ unshift() :  在数组最前面插入一个或者多个元素, 返回结果为该数组新的长度,插入元素后其他元素会一次调成
~~~
var arr = ["王一", "王二", "王三"];

var result1 = arr.unshift("王四"); // 最前面插入一个元素
var result2 = arr.unshift("王五", "王六"); // 最前面插入多个元素

console.log(result1); // 打印结果：4
console.log(result2); // 打印结果：6
console.log(arr); // 打印结果：["王五","王六","王四","王一","王二","王三"]
~~~
### shift
+ shift():删除数组中的第一个元素 返回结果为被删除的元素.
~~~
var arr = ["王一", "王二", "王三"];

var result1 = arr.shift();

console.log(result1); // 打印结果：王一
console.log(arr); // 打印结果：["王二","王三"]
~~~
### concat()
+ concat(): 链接两个或多个数组, 返回结果为新的数组(不会改变原数组)
~~~
var nameArr1 = ["张三", "李四"];
var nameArr2 = ["王五", "赵六"];
var nameArr = nameArr1.concat(nameArr2);
console.log(nameArr); // ['张三','李四','王五','赵六']
console.log(nameArr1); // ['张三','李四']
console.log(nameArr2); // ['王五','赵六']
// 并未改变原数组，所以我要用一个新数组nameArr去接收合并后的数组，以便后续使用。
~~~
### join()
+ join():将数组转换为字符串, 返回结果为转换后的字符串(不会改变原来的数组)
~~~
var arr = [1, 2, 3];
var arrStr = arr.join("-");
console.log(arrStr); // 1-2-3
console.log(arr); // [1,2,3]
// 并未改变原数组
~~~
### split
+ split():通过指定分隔符,如果省略,默认以逗号分隔,讲字符串分割为字符串数组.
~~~
var email = "abc@163.com;cc@126.com;frg@qq.com";
var emailArr = email.split(";");
console.log(emailArr); // ["abc@163.com", "cc@126.com", "frg@qq.com"]
var emailArr2 = email.split(";", 2);
var emailArr = email.split(";"); // ["abc@163.com", "cc@126.com"]
~~~
##求数组的平均值
~~~
var arr = [32, 41, 1, 40, 12, 5];
// 计算数组元素的和,获取数组元素个数,求平均值
var sum = 0;
for (var i = 0; i < arr.length; i++) {
	// sum = sum + arr[i]
    //sum循环一次是32 循环第二次是32加41  依次循环等于他的和; 
	sum += arr[i];
}
var avg = sum / arr.length;
console.log(avg); // 21.833333333333332
~~~
##  数组排序
###  冒泡排序
 + 比较相邻的元素.如果第一个比第二个大,就叫唤他们两个.
 + 对每一对相邻的元素作同样的工作,从开始第一对到结尾的最后一对,在这一点,最后的元素应该会使最大的数.
 + 针对所有的元素重复以上的步骤,除了最后一个
 + 持续每次对越来越少的元素重复上面的步骤,知道没有任何一对数字需要比较.
 + 之所以叫冒泡排序 每一轮两个比较之后 都会冒出一个本轮最大的数 将其移动到本轮尾部.
~~~
  var arr= [12, 8, 4, 24, 10];
        for(var i = 0; i < arr.length -1; i++){
            if(arr[i] > arr[ i+ 1]){
                var temp = arr[i];
                arr[i] = arr[i + 1];
                arr[i + 1]= temp;
            }
        }
        console.log(arr);
        for(var i = 0; i < arr.length - 1; i++){
            if(arr[i] > arr[i + 1]){
                var temp =arr[i];
                arr[i] = arr[i + 1];
                arr[i + 1]=temp;
            }
        }
        console.log(arr);
        for(var i = 0; i < arr.length - 1; i++){
            if(arr[i] > arr[i + 1]){
                var temp = arr[i];
                arr[i] = arr[i + 1];
                arr[i + 1]= temp;
            }
        }
        console.log(arr);  
        for (var i = 0; i < arr.length - 1; i++){
            if(arr[i] >arr[i + 1]){
                var temp = arr[i];
                arr[i] = arr[i + 1];
                arr[i + 1]= temp;
            }
        }
        console.log(arr);
~~~
# 函数
+ 函数 : 就是将一些功能或语句进行封装,在需要的时候,通过调用的形式,执行这些语句.
+ 函数也是一个对象
+ 使用typeof 检查一个函数对象时, 会返回function
+ 函数的定义
+ function:是一个关键字 中文是 函数
+ 函数名字:命名规定和变量规定一样
+ 大括号里面 是这个函数的语句,
+ 使用函数表达式 来创建一个函数,语法:
+ var 函数名 = function([形参1,形参2 ...形参n]){语句...}
~~~ 
   var fun3 = function(){
       console.log("我是匿名函数中封装的代码");
   }
   从方式二的举例中可以看出:所谓的"函数的表达式",其实就是将匿名函数的赋值给一个变量. 当然,我们没有方式三: 使用构造函数来创建一个对象. 这种方式.用的少.
~~~
## 函数的调用
+ 函数调用的语法: 函数名();
## 函数的参数 :形参和实参
+ 函数的参数包括形参和实参.
###形参
+ 可以在函数的() 中来制定一个或多个形参.
+ 多个形参之间使用, 隔开,生命形参就相当于在函数内部生命了对应的变量 但是并不赋值
###实参
+ 在调用函数时, 可以在()中 指定实参.
+ 实参将会赋值给函数中对应的形象.
~~~
sum(3, 4);
sum("3", 4);
sum("Hello", "World");

//函数：求和
function sum(a, b) {
	console.log(a + b);
}
控制台输出结果 7 34 helloworid
~~~
### 实参类型
+ 函数的实参可以是任意的数据类型
+ 调用函数时解析器不会检查实参的类型,所以要注意, 是否有可能会接收到非法的参数,如果有可能则需要对参数进行类型的检查.
### 实参的数量
+ 多于实参不会被贬值
+ 如果实参的数量少于形参的数量 则没有对应实参的形参将是 undefined. 
## 函数的返回值
~~~
console.log (sum(3,4));
//函数求和
function sum(a,b){
    return a + b;
}
~~~
+ return 的作用是结束方法,
+ return 后的值将会作为函数的执行结果返回 可以定义一个变量 来接受该结果.
+ 在函数中 return 语句后不跟任何值,就相当于返回一个 undefined
+ 如果函数中不写 return,则也会返回 undefined
+ 返回值可以是任意的数据类型,可以是对象 也可以是函数
###fn()和 fn 的区别
+ fn() :调用函数. 相当于获取了函数的返回值
+ fn :函数的对象.相当于直接截取了函数对象
### 作用域(Scope)的概念
+ 作用域指一个变量的作用范围, 在js中 一共有两种作用域.
+ 全局作用域
+ 函数作用域
### 立即执行函数
+ 现有匿名函数如下:
~~~
function(a,b){
    console.log("a = " + a);
    console.log("b = " + b);
};
~~~
+ 立即执行函数如下:
~~~
(function(a,b){
    console.log("a = " + a);
    console.log("b = " + b);
})(123,456);
~~~
+ 立即执行函数: 函数定义完 立即被调用 这种函数叫做立即执行函数
+ 立即执行函数往往只会执行一次 因为没有保存它 执行完了以后 就找不到了 
## 参数的数据类型
### 基本数据类型作为参数
+ 基本数据类型作为参数传递, 函数内部会创建该数据的副本,一切修改不会影响传进来的数据本身
~~~
var num = 2;
function ins (x) {
    x++
}
ins (num);
console.log(num);
~~~
## 复杂数据类型作为参数
### 复杂数据类型作为参数传递, 在函数内部对该参数的修改, 会直接影响到函数外部的该参数,因为本质上他们是同一个对象
~~~
function add(arr,n){
    arr.push(n);
}
var arr =[2,3];
add(arr,4);
console.log(arr);
~~~
## 栈内存和堆内存
+ JS 中，所有的变量都是保存在栈内存中的。