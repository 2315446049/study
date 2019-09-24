# 第二章 JavaScript数据类型
### 2.1 数据类型的分类
2.1.1 基础数据类型
基础数据类型也可以叫做简单数据类型或原始数据类型，通常表示某种值，对值进行的比较。

2.1.2 引用数据类型
引用数据类型也可以叫做复杂数据类型，是以键值对形式出现的，以属性和属性值构成，无需列表集合，在内存中占据独立的空间，任何两个独立的对象都不相等.

###2.2 基本数据类型
2.2.1 数字类型
Number类型，这种类型使用IEEE754格式来表示整数和浮点数.数字类型包括：整数，浮点数，NaN（非数字），Infinity（无穷大）
数字范围：最大值5e-324，最大值2的53次方
isNaN（）方法来验证该值是否为非数字，非数字返回值为true，数字返回值为false.

       var a = 10;
       var b = '10';
       alert(isNaN(a + b));//flase
       alert(isNaN(a-b));  //flase
       alert(isNaN(a * b));//flase
       alert(isNaN(a / b));//flase
       alert(isNaN(NaN));//true

2.2.2 字符串类型
String类型是由引号括起来的一组16位Unicode字符组成的字符序列，字符串类型通常被用于表示文本数据。
 
        var a = '你好';
        var b = '你们好';
        var c = '你好我叫“tom”';

字符串中反斜线有着特殊的字符，反斜线后面加一个特殊字符，就变为了转义字符，具备一些特殊用途

2.2.3 布尔类型
Boolean类型，只有两个字面量值，分别是true和false，并且他们区分大小写，小写的是布尔类型的值
数据类型中有以下数据类型转换后为false：
(1)false
(2)''空字符串
(3)+0和-0
(4)NaN
(5)null
(6)undefined

2.2.4 null
Null类型代表空对象，是一个对象，函数的参数，表示该函数不是对象，也可以当做空对象用.
          console.log(null+1);
        //null数据类型转换为0；

2.2.5undefined
Undefined类型代表未定义，是变量的初始值，也是函数的默认返回值，undefined是关键字，不是对象.
         console.log(undefined+1);
        //undefined数据类型转换为NaN；

### 2.3 检验基础数据类型的方式
typeof 运算符吧信息当做‘字符串’返回，也就是说返回值都是字符串类型，
返回值的几种情况：number string Boolean object undefined function.null返回的是object，对于对象不能用typeof检测
       var  a = 10;//number
       var b='nihao';//string
       var c=true;//Boolean
       var d=false;//Boolean
       var e=null;//object
       var f=undefined;//undefined
       var g=['1',2];//object
       var h=function(){alert(1)};//function
注意事项：
typeof后面的括号，在有运算的时候一定要使用，否则返回值不可能不正确

### 2.4 数据类型的转换
2.4.1 强制转换
强制转换主要是指使用Number(),String(),Boolean()三个函数，手动将各种类型的值分别转为，数字类型，字符串类型，布尔类型.

Number()转换为数字类型
        console.log(Number('352'));//352
        console.log(Number('nihao'));//NaN
        console.log(Number(''));//0
        console.log(Number(true));//1
        console.log(Number(false));//0

String()转换为字符串类型
        console.log(String(222));//'222'
        console.log(String(true));//'true'
        console.log(String(false));//'false'

Boolean()转换为布尔类型
        console.log(Boolean(654));//true
        console.log(Boolean('nihao'));//true
        console.log(Boolean(''));//false
        console.log(Boolean(0));//false
        console.log(Boolean(NaN));//false

2.4.2 parseInt()和parseFlost()
parseInt()函数可以将数据转换成数字类型，并取整数部分，浮点部分不取，如先遇到非数字数据，显示为

          var a=10.67;
          var b='4.666';
          var c='12e';
          var d='nihao123';    
         console.log(parseInt(a));//10
         console.log(parseInt(b));//4
         console.log(parseInt(c));//12
         console.log(parseInt(d));//NaN
         /**************************/
parseFlost()函数可以将数据转换为数字类型，取整数和浮点数部分.
          var a=10.67;
          var b='4.666';
          var c='12.4e';
         console.log(parseFloat(a));//10.67
         console.log(parseFloat(b));//4.666
         console.log(parseFloat(c));//12.4

2.4.3 自动转换
变量的数据类型不确定，但运算符对数据类型是有要求的，如果运算符发现运算的数据类型与预期的不一样，就会进行自动转换.
