# JavaScript课堂笔记
包含课所有笔记
# JavaScript设计交互页面基础知识

### 一、JS的简介

- 概念

  - JavaScript 是一种运行在客户端（浏览器）的编程语言

- 作用

  - 1. 网页特效 (监听用户的一些行为让网页作出对应的反馈)
  - 2. 表单验证 (针对表单数据的合法性进行判断)
  - 3. 数据交互 (获取后台的数据, 渲染到前端)
  - 4. 服务端编程 (node.js)

- 组成

  - ECMAscript
  - DOM
  - BOM

### 二、变量

- 概念和作用

  - 容器
- 声明赋值的几种写法

  - 先声明,再赋值
  - 声明并直接赋值
  - 同时声明多个变量
- 变量的本质

  - 在内存中开辟一个空间，会站用一部分存储空间
- 命名规则和规范

  - 规则

    - 由字母、数字、下划线、$符号组成，不能以数字开头
    - 不能是关键字和保留字，例如：var for while
    - 严格区分大小写

  - 规范

    - 变量名必须有意义
    - 

- var声明变量和let的区别

  - let为了解决var的一些问题
  - var声明:

    - 可以先使用 在声明 (不合理)
    - var声明过的变量可以重复声明(不合理)
    - 比如变量提升、全局变量、没有块级作用域等等
- 数组

  - 什么是数组? 为什么需要数组?

    - 存储班级所有人的姓名

  - 创建数组

    - 字面量

  - 取值

    - 数组[下标]

**变量命名规范**：

```javascript
 var namee;//只声明变量，没有给初始值
        var answer=null;//声明变量同时给变量赋空值
        var pricet=12.50;//声明变量同时给变量赋数值的值
        var str="Hello Word";//声明变量同时给变量赋字符串的值
        var a,b,c;//使用逗号同时声明多个变量，没有给初始值
        result=true;//省略var关键字来声明变量，赋布尔值
        /* 定义变量，可用逗号进行一次多个变量命名 */
        var name ="特步",
            moery=150.5,
            trim=2,
            price="否";
```

**获取变量的数据类型：**

```javascript
 /* 定义变量，可用逗号进行一次多个变量命名 */
            var salary=2000,
                name="布尔",
                price=2.5,
                isFamle=true,
                obj=null;
       		/*
             typeof() 获取变量的数据类型 获取规范 typeof(变量名)
             */
            document.write("你的薪水是："+salary+"元！ salary的类型是："+typeof(salary)+"<br/>")
            document.write("我的名字是："+name+"！ name的类型是："+typeof(name)+"<br/>")
            document.write("苹果价格是："+price+"元！price的类型是："+typeof(price)+"<br/>")
            document.write("isFamle的类型是："+typeof(isFamle)+"<br/>")
            document.write("obj的类型是："+typeof(obj)+"<br/>")
```

### 三、数据类型

- 概念和作用

  - 1. 更加充分和高效的利用内存
  - 2. 也更加方便程序员的使用数据
- 分类介绍

  - 基本数据类型

    - - number 数值型
    - - string 字符串
    - 单引号
      - 双引号
      - 反引号
      - 字符串拼接

      - '+ 变量名 +' 去替换需要替换的内容
        - 有拼接不方便引申出模板字符串

        - 模板字符串(ES6) 
    - - boolean 布尔型
    - - undefined 未定义
    - - null 空引用
  - 引用数据类型

    - - object  对象
    - - function  函数 
    - - array    数组

#### 数据类型的转换

- 为什么需要转换?

  - 从用户得到的数据都是字符串,而字符串和数字相加会变成相连
- 显示转换

  - 转换成数字

    - Number()
    - parse系列

      - 如果介绍parse系列就是介绍区别和使用场景
    - 三者的区别
  - 转换成字符串

    - String()
    - 变量.toString() 

      - 括号里面可以跟进制

    - 两者区别
- 隐式转换的小技巧

  - +号作为正号解析可以转换成Number
  - 任何数据和字符串相加结果都是字符串

**自动类型转换：**

| 变量原来的值 | string类型  | number类型  | boolean类型 | object类型  |
| :----------: | :---------: | :---------: | :---------: | :---------: |
|    var x;    |   string    |   number    |   boolben   |   object    |
|  未给初始值  | "undefined" |     NaN     |    false    |    错误     |
|     null     |   ”null“    |      0      |    false    |   object    |
|  非空字符串  | 字符串本身  | 字符串或NaN |    true     | 字符串对象  |
|      “”      |     ""      |      0      |    false    | 字符串对象  |
|      0       |     ”0“     |      0      |    false    |  数值对象   |
| 不为0的整数  | "数字本身"  |  数字本身   |    false    |  数值对象   |
|     NaN      |    "NaN"    |      /      |    false    |  数值对象   |
|     true     |   "true"    |      1      |    true     | boolean对象 |
|    false     |   "false"   |      0      |    false    | boolean对象 |

**自动类型转换案例：**

```javascript
        //自动类型转换
        document.write('自动转换类型：<br />');
        var intnum=1;
        var str='hello';
        var bool=true;
        var nul=null;
        document.write(intnum+'+'+str+'='+(intnum+str) +'&emsp;&emsp;整数+字符串的结果数据类型是：'+typeof(intnum+str)+'<br />')
        document.write(intnum+'+'+bool+'='+(intnum+bool) +'&emsp;&emsp;整数+布尔类型的结果数据类型是：'+typeof(intnum+bool)+'<br />')
        document.write(str+'+'+bool+'='+(str+bool) +'&emsp;&emsp;字符串+布尔类型的结果数据类型是：'+typeof(str+bool)+'<br />')
        document.write(bool+'+'+nul+'='+(bool+nul) +'&emsp;&emsp;布尔类型+空值的结果数据类型是：'+typeof(bool+nul)+'<br /><br /><br />')
```

**强制转换类型案例：**

```javascript
 //强制类型转换
        var address;
        //变量没有初始值的数据类型
        document.write('address的值是：'+address+'<br />');
        //变量空值的数据类型
        var phone =null;
        document.write('phone的值是：'+phone+'<br />');
        var sname='HOPE';
        //强制字符串类型转换为整数
        var snameResult=parseInt(sname);
        document.write('将姓名转换为数字的结果是：'+snameResult+'<br />');
          //强制数字字符串类型转换为整数
        var age ='20';
        var ageResult=parseInt(age);
        document.write('将年龄转换为数字的结果是：'+ageResult+'<br />');
```

**案例：**加法器：页面输入2个数，计算两者的和，打印到页面中

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>变量</title>
</head>
<body>
    <form name="myForm">
        <input type="text" name="first">
        <input type="text" name="second">
        <input type="text" name="result">
        <input type="button" onclick="sum()" value="sum">
    </form>
    <script>
        //定义一个求和函数，进行加法运算
        function sum(){
            //定义三个空变量来获取用户输入的值
            var firstValue,secondValue,resultValue;
            //获取用户输入的值
            firstValue = document.myForm.first.value;
            //获取用户输入的值
            secondValue = document.myForm.second.value;
            //parse()方法来将变量转换为浮点数来进行加法运算
            resultValue = parseFloat(firstValue)  + parseFloat(secondValue);
            //输出加法运算的值
            document.myForm.result.value = resultValue;
        }
    </script>
</body>
</html>
```

### 四、运算符

- 算术运算符

  - 加、减、乘、除、取模 (+, -, *, /, %)
  - 加号上下文

    - 如果+号左右只有一个值  解析的结果是正号 可用于隐式转换
    - 如果两边都是数值(Number)类型 则是+号运算符
    - +号的左右如果有一个数据是字符串数据类型的话  那么这个+号会被解析成连接符
  - 优先级

  **算术运算符案例：**

  ```javascript
   document.write('算数运算符：<br />');
          //定义两个变量来进行算术运算
          var nuber1=10,
              nuber2=20;
          
          var nuber3=nuber1++; //先赋值再加1
          var nuber4=++nuber2; //先加1再赋值
          //输出变量运算后的值
          
          document.write('nuber1=' + nuber1 + '<br>');
          document.write('nuber2=' + nuber2 + '<br>');//输出变量运算后的值
          document.write('nuber3=' + nuber3 + '<br>');//输出变量运算后的值
          document.write('nuber4=' + nuber4 + '<br>');//输出变量运算后的值
          document.write('5+2='+parseFloat(5+2)+'<br />');  //+ 进行加法运算
          document.write('5-2='+parseFloat(5-2)+'<br />');    // / 进行减法运算
          document.write('5*2='+5*2+'<br />');    // / 进行乘法运算
          document.write('5/2='+5/2+'<br />');    // / 进行除法运算
          document.write( '5%2='+5%2+'<br /><br/>');// % 进行取余运算
  ```

  

- 赋值运算符 (=)

  - 将等号右边的值赋予给左边, 要求左边必须是一个容器
  - 累加 +=

  **赋值运算符案例：**

  ```javascript
   document.write('赋值运算符：<br/>');
          var str ='我是字符串',
              a=1;
              a+=1; //a=1+2
          document.write('a='+ a +'<br />'); //输出a =1+2 的值
          var x=5,
              y=7;
              x+=y;//x=x+y
              y-=x;//y=y-x
          document.write('x='+ x +'<br />'); //输出//x=x+y 的值
          document.write('y='+ y +'<br /><br />');//y=y-x 的值
  ```

  

- 一元运算符

  - 一元运算符: 仅操作一个操作数. 比如: 正负号等 
  - 自增自减运算符 

    - 相同点

      - 不管是++或者-- 是在前还是在后,都是在原来的取值上自行增1或减1  类似于 => a += 1

    - 不同点

      - 符号前置 => 先加1 再使用 (快捷记忆: ++在前 先加)
      - 符号后置 => 先使用 再加1 (快捷记忆: ++在后, 后加)

    - 面试题

- 逻辑运算符

  - 逻辑与

    ```javascript
    var box={} && (5>4);     //true,第一个为对象,返回第二个操作数
    var box=(5>4) &&{};            //[object Object],第二个操作数是对象,则第一个操作数返回true,才返回第二个操作数,否则返回false
    var box=(3>4) &&{};            //false
    var box=(5>4) && null       //null,有一个操作数为null,返回null
    var box=(5>4) && undefined  //undefined
    ```

    

  - 逻辑或

    ```javascript
    var box={}||(5>3);   　　　　//[object Object],第一个操作数为对象,返回第一个
    var box=(5>3)||{};  　　　　 //true
    var box={}||{};     　　　　//[object Object],如果两个都是对象,返回第一个对象
    var box=null||null         //null,两个为null,返回null
    var box=NaN || NaN         //NaN,两个都是NaN,返回NaN
    var box=undefined || undefined //undefined,两个为undefined,返回undefined
    var box=true||age          //true,age未定义,第一个为真,返回真
    var box=false ||age        //出错,age未定义
    ```

    

  - 逻辑非

    ```javascript
    var box=!(5>4)    //false
    var box=!{}            //false,操作数是一个对象返回false
    var box=!''            //true,操作数为空字符串返回true
    var box=!'lee';        //false,非空字符串返回false
    var box=!0;            //true,为0时返回true
    var box=!8;            //false,非0数值包括Infinity,返回false
    var box=!null       //true,null返回true
    var box=!NaN;        //true
    var box=!undefined;    //true
    ```

    

**逻辑运算符案例：**

```javascript
document.write('逻辑运算符：<br />');
        document.write('true && true='+ (true && true) +'<br />');
        document.write('true && false=' +(true && false) +'<br />');
        document.write('false && false=' +(false && false) +'<br />');

        document.write('true || true='+ (true || true) +'<br />');
        document.write('true || false=' +(true || false) +'<br />');
        document.write('false | false=' +(false || false) +'<br />');

        document.write('! true =' +(! true) +'<br />');
        document.write('! false =' +(! false) +'<br />');

        var str ="text";
        var num4=12;
        document.write( 'str && true 的结果是：'+(str && true ) +'<br />');
        document.write('str || true 的结果是：'+ (str || true ) +'<br />');
        document.write( 'num4 && true 的结果是：'+(num4 && true ) +'<br />');
        document.write('num4 || true 的结果是：'+ (num4 || true ) +'<br /><br />');
```



- 比较运算符

  - > , < , >= , <= , == , === , != , !==

  - 重点介绍 等于和全等的区别, 推荐使用全等

  - 特殊说明

    - 如果是数字和"其他值"的比较 则其他值会自动转换成数字去比较
    - 涉及到"NAN"都是false （NaN）
    - 如果是"字符串"和"字符串"比较 则会比较每一个字符的ASCII码,同时是按位进行比较 
    - 如果是布尔值参与比较 布尔值会转换成数字0和1

  **比较运算符案例：**

  ```javascript
     document.write('比较运算符：<br />');
          var num1=1;
          var num2=2;
          var num3="1";
          //num1 num2 进行比较  比较返回值只有 true false
          document.write( (num1 > num2) +'<br />');
          document.write( (num1 < num2 )+'<br />');
          document.write( (num1 >= num2) +'<br />');
          document.write( (num1 <= num2 )+'<br />');
          document.write( (num1 != num2) +'<br />');
          document.write( (num1 == num2 )+'<br />');
          document.write( (num1 == num3 )+'<br />');//结果是true，若类型不同，==尝试做自动转换 而===不会
          document.write( (num1 === num3 )+'<br />');//结果false
  
          document.write( ("a" > "b" )+'<br />');//ASCII字符代码表，A-Z(65-90)  a-z(97-122)
          document.write( ("a" > "A" )+'<br />');
          document.write( ("bbb" == "bbbb" )+'<br />');
  ```

- 字符串运算符

  - 在 JS 中没有专门用于字符串连接的运算符，使用算数运算符的 **+** 来进行字符串连接操作
  - 将字符串和数值进行 + 号运算时，优先进行字符串连接运算，将数值类型转换为字符串类型之后再操作.
  - 如果要进行数学运算，需要手动将字符串类型强制转换为 number 类型。

​	**字符串运算符案例：**

```javascript
document.write('字符串运算符：<br />');
        var str2 ="张三",
            str3="法外狂徒";
 document.write('str2 + str3=' +(str2 + str3) +'<br />');
```

- 条件运算符

```javascript
  document.write('条件运算符：<br />');
        var age= 10;
        var strr;
       
        strr=(age >= 10)? "成年" : "未成年"+'<br /><br />';
        document.write(strr);
        var st=14;
        var stex;
        stex =(st % 2 == 0 ) ? "偶数 " : "奇数";
        document.write(stex);

```



- 运算符优先级	

| 优先级 |                    运算符                     |
| :----: | :-------------------------------------------: |
|   1    |       .   [ ]   ( )  ++  -- !   typeof        |
|   2    |               *   /   %   +   -               |
|   3    | <    <=    >    >=     ==    !=    ===   !=== |
|   4    | &&    \|\|    ?:    =    *=   /=  %=  +=   -= |

### 五、语句

- 表达式和语句

  - 表达式

    - 表达式是一组代码的集合，JavaScript解释器会将其计算出一个结果

      - x = 7
      - 3 + 4
      - num++

  - 语句

    - js 整句或命令，js 语句是以分号结束（可以省略）

      - if 条件语句
      - for 循环语句

  - 区别

    - 达式计算出一个值，但语句用来自行以使某件事发生。

      - 表达式  3 + 4 
      - 语句  alert()  弹出对话框

- 语句分类

  - 顺序语句
  - 分支语句
  - 循环语句

- 分支语句

  - if分支

    - 单条分支

    - 双分支

    - 多条分支

    **if案例：**

    ```javascript
       var score=prompt("请输入你的成绩：");
            if(score >= 90 && score <= 100){
               document.write('优秀');
            }
            if(score >= 80 && score <= 89){
                document.write('良好');
            }
            if(score >= 60 && score <= 79){
                document.write('合格');
            }
            if(score <= 59 && score >= 0){
                document.write('不合格');
            }
            if(score >= 101){
                document.write('输入的分值超出范围');
                }
            if(score < 0){
                document.write('输入的分值超出范围');
               
            }
    ```

    

  - 三元运算符

    - 条件 ? 表达式1 : 表达式2
    - 对比if两条分支的区别

  - switch case

    - 出现定值判断使用
    - 特点说明

      - 1. switch case语句一般用于等值判断,不适合于区间判断
      - 2. switch case比较的值全等 ===
      - 3. switch case一般需要配合break关键字使用 没有break会造成case穿透

  - 分支语句的综合

    - if 分支

      -  使用的最多的分支语句  任何情况下都可以通用

    - 三元运算

      - 可以简单理解为两条分支的简写形式,一些简单的两条分支可以使用三元运算符代替
      - 相较正常的两条分支语句来说多了一个返回值

    - switch case语句

      - 当出现了定值判断的时候可以使用

    - 多分支语句和switch的区别

      - 如果值比较精确用switch ，效率更高
      - 如果有范围的判断，用多分支语句

- 断点调试

  - 是为了演示循环语句的过程

- 循环语句

  - while循环

    - 语法

  - while的使用场景介绍

    - 更适合使用在循环的次数不确定时候使用

  - do while 循环

    

### 六、函数

#### 什么是函数?为什么需要函数?

- 函数可以理解为一个 特定的代码块 容器 ，它可以完成特定的需求, 并且可以 重复 使用

#### 函数声明和函数调用

- 函数默认不会主动执行,必须通过函数名() 调用才会执行. 
- 函数一次声明可以多次调用,每一次函数调用函数体里面的代码会重新执行一次.
- 我们曾经使用的 alert() , parseInt() 这种名字后面跟小括号的本质都是函数的调用 

#### 函数传参

- 根据上面练习的缺陷引出函数传参

  - 把函数在复用过程中会改变的值提取出来, 作为参数传递进去.这样可以极大提高函数的灵活性
- 需求: 封装一个可以跟任何人打招呼的函数
- 函数传参的语法

  - 完成上述需求
- 细节说明

  - 1. 术语1: 在声明函数的小括号里面写的数值我们称之为形式参数
  - 2. 术语2: 在调用函数的小括号里面写的数值我们称之为实际参数
  - 3. 形参作用: 本质上就是在函数内部声明变量
  - 4. 实参作用: 给形参赋值
  - 5. 曾经使用过的 alert('打印'), parseInt('11'), Number('11') 本质上都是函数调用的传参

#### 函数的返回值



#### 内置函数

- parselnt（）函数
  - parselnt（）函数将一个字符串按指定的进制转换为一个整数。
- parseFloat（）函数
  - parseFloat（）函数将一个字符串转换为对应的浮点数
- IsNaN（）函数
  - isNaN函数用于检测一个变量或一个字符串是否为NaN。如果是，则返回true，如果不是返回false。
- eval（）函数
  - eval（）函数将一个字符串做作为一段JavaScript表达式执行，并返回执行的结果。

### 七、对象

#### 什么是对象? 为什么需要对象?

- 何为对象：万物皆对象,对现实事物的描述。客观世界中的具体的实体都是对象 如一个人,一个气球,一辆汽车,咱们的 班主任等.
- 需求: 如何在JS中存储班主任这个对象的信息 ?

  - - 静态特征 (姓名, 年龄, 身高, 性别, 爱好) => 可以使用数字, 字符串, 数组, 布尔类型等表示
  - - 动态行为 (点名, 唱, 跳, rap) => 使用函数表示

#### 对象的基本语法介绍

- 在Js中, 对象就是一组无序的键值对的集合
- 说明

  - 1. 我们把冒号左边的内容称之为属性, 右边称之为值, 成对出现, 故称之为键值对
  - 2. 当右边的值为函数的时候, 我们更喜欢将这个属性称之为方法
  - 3. 对象本质上也是一种数据集合, 对比数组来说它里面装的都是不同类型的数据, 并且有对应的属性提示数据的含义
  - 提问: 上述信息是否可以使用数组存储

#### 对象的基本使用

- 对象本质上也是数据集合,使用无外乎增删改查
- 查语法: 对象名.属性
- 改语法: 对象名.属性 = 新值
- 增语法: 对象名.新属性名 = 新值
- 删语法（一嘴带过）

  - delete 对象名.属性名

#### 对象遍历

- 引入[]语法操作对象属性

  - 对比点语法的相同点和不同点

    - 1. 都可以访问对象的属性 对象名.属性名 === 对象名['属性名']
    - 2. []语法里面的值如果不添加引号 默认会当成变量解析
    - 3. 没有必要的时候直接使用点语法, 在需要解析变量的时候使用 [] 语法

- 遍历对象

  - for 遍历对象的问题：

    - 对象没有像数组一样的length属性,所以无法确定长度
    - 对象里面是无序的键值对, 没有规律. 不像数组里面有规律的下标

  - 通过for in 语法

    - 1. for in语法中的 attr 是一个变量, 在循环的过程中依次代表对象的属性名
    - 2. 由于attr是变量, 所以必须使用 [ ] 语法解析 

- 综合案例

#### 内置对象

- 什么是内置对象？ 为什么要学习内置对象
- Math

  -   Math.PI
  -   最大值/最小值
  -   绝对值
  -   取整
  -   随机数

      - 求 0 -n之间的随机数
      - 求m-n之间的随机数
      - 练习： 随机抽奖 / 猜数字游戏

#### 综合案例

- 学成在线页面渲染案例

#### 简单类型和复杂类型

- 堆和栈
- 简单数据类型传参
- 复杂数据类型传参

### 八、数组

#### 什么是数组? 为什么需要数组?

- 存储班级所有人的姓名

#### 创建数组

- 字面量
- 构造函数

#### 数组的使用

- 数组本质是数据集合,使用无非就是增删改查
- 查

  - 数组[下标]

- 改

  - 数组[下标] = 新值

- 增

  - arr.push(新增的内容)

    - push可以实现一次性添加多个的效果, 推荐使用

  - arr.unshift(新增的内容)

- 删

  - arr.pop()
  - arr.shift()
  - arr.splice(操作的下标,删除的个数)

#### 遍历数组

- 访问数组里面的每一个数据 
- 依次访问
- 循环访问
- 提取公式

#### 数组的冒泡排序

```javascript
  // 编写方法，实现冒泡
    var arr = [29,45,51,68,72,97];
    //外层循环，控制趟数，每一次找到一个最大值
    for (var i = 0; i < arr.length - 1; i++) {
        // 内层循环,控制比较的次数，并且判断两个数的大小
        for (var j = 0; j < arr.length - 1 - i; j++) {
            //如果前面的数大，放到后面(当然是从小到大的冒泡排序)
            if (arr[j] > arr[j + 1]) {
                var temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
 	}
```

#### 数组的常用方法

|    方法     |                             说明                             |
| :---------: | :----------------------------------------------------------: |
| concat（）  |    返回一个新数组，这个新数组是由两个或更多新数组组合而成    |
|  join（）   | 返回字符串值，其中包含连接到一起的数组的所有元素，元素由指定的分隔符分隔开来 |
|   pop（）   |             移除数组中的最后一个元素并返回该元素             |
|  push（）   |        将新元素添加到一个数组中，并返回数组的新长度值        |
| reverse（） |              返回一个元素顺序被反转的Array对象               |
|  shift（）  |              移除数组中的第一个元素并返回该元素              |
|  slice（）  |                      返回一个数组的一段                      |
| splice（）  | 从一个数组中移除一个或多个元素，如果必要，在所移除元素的位置上插入新元素，返回所移除的元素 |
|  sort（）   |            返回一个元素已经进行了排序的Array对象             |



#### 数组实现二级联动

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="IE=edge">
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<title>Document</title>
	</head>
	<body>

		居住地址：
		<select id="selProvice" onchange="changeCity()">
			<option value="">--请选择省份--</option>
		</select>
		<select id="selcity">
			<option value="">--请选择城市--</option>
		</select>
	</body>
	<script>
		var cityList = new Array();
		//存储数组省份城市信息
		cityList["江苏省"] = ["南京市", "无锡市", "徐州市", "常州市", "苏州市", "南通市"];
		cityList["浙江省"] = ["杭州市", "宁波市", "金华市", "温州市", "绍兴市", "湖州市"];
		cityList["湖南省"] = ["长沙市", "湘潭市", "岳阳市", "张家界市", "邵阳市", "常德市", "永州市", "益阳市", "怀化市"];
		cityList["广西省"] = ["南宁市", "桂林市", "柳州市", "梧州市", "贵港市", "玉林市", "钦州市", "北海市", "防城港市", "崇左市", "百色市", "河池市", "来宾市", "贺州市"];
		cityList["广东省"] = ["广州市", "深圳市", "清远市", "韶关市", "河源市", "梅州市", "潮州市", "汕头市", "揭阳市", "汕尾市", "惠州市", "东莞市", "珠海市", "中山市","江门市", "佛山市", "肇庆市", "云浮市", "阳江市", "茂名市", "湛江市"];

		function allProvice() {
			var province = document.getElementById("selProvice");
			for (var i in cityList) {
				province.add(new Option(i, i), null)
			}
		}
		window.onload = allProvice();

		function changeCity() {
			var provinceValue = document.getElementById("selProvice").value;
			//获取城市的信息
			var city = document.getElementById("selcity");
			//每一次循环将删除上一次城市的信息  清楚作用
			city.options.length = 0;
			for (var i in cityList) {
				if (i == provinceValue) {
					for (var j in cityList[i]) {
						city.add(new Option(cityList[i][j], cityList[i][j]), null)
					}
				}
			}

		}
	</script>
</html>
```

方法2：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
		<!--创建下拉省份列表 进行二级联查-->
		    <select name="" id="provinces">
		        <option value="请选择省份">--请选择省份--</option>
		    </select>
			<!--创建下拉市列表 进行二级联查-->
		    <select name="" id="cities">
		        <option value="请选择城市">--请选择城市--</option>
		    </select>
			<script type="text/javascript">
				//创建二维数组对象存放省份 城市信息
				 var province=new Array();
				 //存储数组省份城市信息
				    province["江苏省"]=["南京市", "无锡市", "徐州市", "常州市", "苏州市", "南通市"];
				    province["浙江省"]=["杭州市", "宁波市", "金华市", "温州市", "绍兴市", "湖州市"];
					province["湖南省"]=["长沙市","湘潭市","岳阳市","张家界市","邵阳市","常德市","永州市","益阳市","怀化市"];
					province["广西省"]=["南宁市","桂林市","柳州市","梧州市","贵港市","玉林市","钦州市","北海市","防城港市","崇左市","百色市","河池市","来宾市","贺州市"];
					province["广东省"]=["广州市","深圳市","清远市","韶关市","河源市","梅州市","潮州市","汕头市","揭阳市","汕尾市","惠州市","东莞市","珠海市","中山市","江门市","佛山市","肇庆市","云浮市","阳江市","茂名市","湛江市"];
				    // 获取  省下拉菜单
				    var oProvince=document.getElementById("provinces");
					 // 获取  市下拉菜单
				    var oCity=document.getElementById("cities");
				    // 2.利用for循环将省市内容 添加到select下拉菜单
				    for(var i in province){
				      //循环出省份信息
				        // new Option(i,i);//创建下拉选项
				        oProvince.add(new Option(i,i),null)
				    }
				    // 3.添加onchange事件获取到用户匹配的省份城市信息内容
				    oProvince.onchange=function(){
				        // console.log(oProvince.value);
				        // 清空 市级下拉列表
				        oCity.length=0;
				        var oSelect=oProvince.value;//获取选中的省份值
				        for(var j in province[oSelect]){
							//循环出省份对应的城市信息
							//将省份对应城市信息循环输出的城市下拉菜单中
				            oCity.add(new Option(province[oSelect][j],province[oSelect][j]),null)
				        }
				    }
				
			</script>
	</body>
</html>
```



### 九、正则表达式

#### 常规正则达式模式

|  正则模式  |      含义       |
| :--------: | :-------------: |
| ?^[0-9]*$/ |  只能输入数字   |
| /^\d{n}$/  | 只能输入n位数字 |
| /^(0\|[-]) |                 |
|            |                 |
|            |                 |
|            |                 |
|            |                 |
|            |                 |
|            |                 |
|            |                 |
|            |                 |
|            |                 |
|            |                 |
|            |                 |
|            |                 |

### 十、事件以及应用场景

#### 事件注册

在JavaScript中注册事件通常使用下面两种方法

- 将事件绑定到页面元素的属性

  - ```html
    <!--元素 事件='javascrript代码'>-->
    <!--示例：-->
    <html>
        <head>
    		<meta charset="utf-8">
    		<title></title>
    	</head>
        <body>
            
        </body>
    </html>
    ```

  示例：

  ```html
  <!DOCTYPE html>
  <html>
  	<head>
  		<meta charset="utf-8">
  		<title>事件注册：绑定到页面元素属性-this=关键字</title>
  	</head>
      <script type="text/javascript">
  		function conToUp(textbox){
  			document.form1.upper.value=textbox.value.toUpperCase();//this表示文本框
  		}
  	</script>
  	<body>
  		<form name="form1"  method="post"action="">
  			小写：<input type="text" name="lower" onblur="conToUp(this)">
  			大写：<input name="upper" type="text"/>
  		</form>
  	</body>
  </html>
  ```

  

- 将事件绑定到对象的属性

  ```html
  <!DOCTYPE html>
  <html>
  	<head>
  		<meta charset="utf-8">
  		<title>事件注册：绑定到页面对象属性</title>
  	</head>
  	<body>
  		<script type="text/javascript">
  			// function down(){
  			// 	alert("你点击了鼠标");
  			// }
  			// document.onmousedown=down;
  			//匿名函数
  			document.onmousedown=function(){
  				alert("你点击了鼠标！");
  			}
  		</script>
  	</body>
  </html>
  ```

- 事件处理函数的返回值

  ```html
  <!DOCTYPE html>
  <html>
  	<head>
  		<meta charset="utf-8">
  		<title>事件处理函数的返回值</title>
  	</head>
  	<body>
  		<form name="form1"  method="post"action="#">
  			姓名<input type="text" name="lower">
  			<input name="upper" type="submit" value="提交" onclick="return false"/>
  		</form>
  	</body>
  </html>
  ```


#### JavaScript事件属性

##### 鼠标事件

|   鼠标事件    |     触发条件     |
| :-----------: | :--------------: |
|    onclick    | 鼠标点击左键触发 |
| oncontextmenu | 鼠标点击右键触发 |
|  ondblclick   |   鼠标双击触发   |
|  onmouseover  |   鼠标经过触发   |
|  onmouseout   |   鼠标离开触发   |
|    onfocus    | 获得鼠标焦点触发 |
|    onblur     | 失去鼠标焦点触发 |
|  onmousemove  |   鼠标移动触发   |
|   onmouseup   |   鼠标弹起触发   |
|  onmousedown  |   鼠标按下触发   |

给btn按钮添加点击事件，点击弹出 你好！

```javascript
let btn = document.querySelector('button')
btn.onclick = function() {
    alert('你好！')
}
```

##### 键盘事件

|  键盘事件  |                      触发条件                      |
| :--------: | :------------------------------------------------: |
|  onkeyup   |              某个键盘按键被松开时触发              |
| onkeydown  |              某个键盘按键被按下时触发              |
| onkeypress | 某个键盘按键被按下时触发 不识别功能键 比如 ctrl 等 |

  键盘按键被松开时触发，弹出 你好 ！

```javascript
 window.onkeyup = function() {
      alert('你好！')
  }
```

##### 触摸事件

| 触摸touch事件 |              说明               |
| :-----------: | :-----------------------------: |
|  touchstart   |  手指触摸到一个 DOM 元素时触发  |
|   touchmove   | 手指在一个 DOM 元素上滑动时触发 |
|   touchend    | 手指从一个 DOM 元素上移开时触发 |

手指触摸盒子触发

```javascript
let div = document.querySelector('div')
 div.ontouchstart = function() {
      alert('您触摸了盒子')
  }
```

##### 表单事件

| 表单事件 | 触发条件               |
| :------- | :--------------------- |
| onfocus  | 表单获得焦点触发       |
| onblur   | 表单失去焦点触发       |
| oninput  | 表单每次输入触发       |
| onchange | 表单内容发生改变时触发 |
| onselect | 表单文本被选取时触发   |
| onreset  | 表单重置时触发         |
| onsubmit | 表单提交时触发         |

将表单内每次输入的内容打印到控制台 

```JavaScript
let input = document.querySelector('input')
input.oninput = function() {
    console.log(this.value);
```

##### 过渡事件

| 过渡事件        | 触发条件         |
| :-------------- | :--------------- |
| ontransitionend | 在过渡完成时触发 |

##### 动画事件

| 动画事件             | 触发条件             |
| :------------------- | :------------------- |
| onanimationend       | 在动画结束播放时触发 |
| onanimationiteration | 在动画重复播放时触发 |
| onanimationstart     | 在动画开始播放时触发 |

##### 事件对象

| **事件对象属性方法** | **说明**                                  |
| :------------------- | :---------------------------------------- |
| e.target             | 返回触发事件的对象                        |
| e.type               | 返回事件的类型 比如click mouseover 不带on |
| e.preventDefault()   | 该方法阻止默认事件 比如禁止页面右键       |
| e.stopPropagation()  | 阻止事件冒泡                              |

点击按钮后打印出触发事件的对象

```javascript
let btn = document.querySelector('button')
btn.onclick = function(e) {
    console.log(e.target);
}
```

![img](https://img-blog.csdnimg.cn/20210827163315465.png)

###### 鼠标事件对象

| 鼠标事件对象 |                   说明                    |
| :----------: | :---------------------------------------: |
|  e.clientX   |  返回鼠标相对于浏览器窗口可视区的 X 坐标  |
|  e.clientY   |  返回鼠标相对于浏览器窗口可视区的 Y 坐标  |
|   e.pageX    | 返回鼠标相对于文档页面的 X 坐标  IE9+支持 |
|   e.pageY    | 返回鼠标相对于文档页面的 Y 坐标  IE9+支持 |
|  e.screenX   |      返回鼠标相对于电脑屏幕的 X 坐标      |
|  e.screenY   |      返回鼠标相对于电脑屏幕的 Y 坐标      |

###### 键盘事件对象

| 键盘事件对象 | 说明                       |
| :----------- | :------------------------- |
| e.key        | 返回用户按下的物理按键的值 |

 在页面按下 A 键后，弹出按下的物理按键的值

```javascript
window.addEventListener('keyup', function(e) {
    alert(e.key)
})
```

###### 触摸事件对象

| 触摸列表      | 说明                                             |
| :------------ | :----------------------------------------------- |
| touches       | 正在触摸屏幕的所有手指的一个列表                 |
| targetTouches | 正在触摸当前 DOM 元素上的一个手指的一个列表      |
| changeTouches | 手指状态发生了改变的列表，从无到有，从有到无变化 |

### 十一、作用域

> 一套设计好的规则来存储变量, 并在之后能够方便的找到这些变量, 这套规则被称之为作用域

#### Javascript 引擎

`JavaScript` 在处理代码时, 会与以下三个角色进行协同工作:

- **JavaScript 引擎** 从头到尾负责整个 `JavaScript` 程序的编译以及**执行**过程

- 编译器

  负责语法分析及代码生成, 每个程序源代码在

  (引擎)

  执行之前, 都会经历以下三个步骤:

  1. **分词/词法分析** *(Tokenizing/Lexing)* 这个过程将由字符组成的字符串分解为(对编程语言来说)有意义的代码块, 这些代码块被称为**词法单元**. 如, `var a = 2;`, 将被分解为 `var、a、=、2、;`
  2. **语法分析** *(Parsing)* 这个过程将 **词法单元流(数组)** 转换成一个由元素逐级嵌套组成的**抽象语法树** *(AST, Abstract Syntax Tree)*
  3. **代码生成** 将 `AST` 转换为可执行的代码, 简单的说就是有某种方法可以将 `var a = 2` 的 `AST` 转换为一组**机器指令**, 用来创建一个叫做 `a` 的变量(包括分配内存), 并将一个值储存在 `a` 中.

- **作用域** 负责收集并维护所有声明的标识符 *(变量)* 组成的一系列查询.

> 我们来看这段程序, `JavaScript` 是如何处理的:

```javascript
var a = 2;
```

#### 引擎与编译器

引擎会认为这是两个完全不同的声明, 一个 `var a` 由**编译器**在编译时处理, 一个 `a = 2` 由**引擎**在运行(执行)时处理:

- 编译器首先会将这段程序分解为 `词法单元`, 然后将词法单元解析成 `抽象语法树(AST)`;
- 编译过程中(三个步骤), 遇到 `var a`, 编译器会询问**作用域**是否已经有一个该名称的变量存在于同一个作用域的集合中, 有, 则忽略声明, 继续编译, 没有, 则声明一个新的变量 *(此时变量在执行代码之前已经存在, 这也是接下来要讲的**变量提升**的原理)*;
- 到编译的第三部(代码生成), 编译器为**引擎**生成了运行时所需的代码, 这些代码用来处理 `a = 2` 这个赋值操作; 引擎会询问**作用域**是否存在 `a` 变量, 如果存在, 则将值赋值给它, 否则抛出异常.

#### 引擎与作用域

我们知道, 当编译器完成了编译, 并返回给引擎代码后, 引擎需要协同作用域, 对生成的变量进行**查询**和**赋值**;

如果目的是对变量进行赋值, 引擎使用 `LHS` 查询; 如果目的是获取变量的值, 引擎使用 `RHS` 查询;

如, `var a = 2`, `var a` 会在编译过程中声明, `a = 2` 是赋值操作, 我们需要为 `= 2` 找到一个目标, 所以使用了 `LHS` 查询;

如, `console.log(a)`, 在这里我们向作用域询问 `a` 的值, 所以使用了 `RHS` 查询.

#### 作用域嵌套

> 作用域是根据名称查找变量的一套规则, 实际情况中, 通常需要同时顾及几个作用域

```javascript
function foo(a) {
    console.log(a + b)
}

var b = 2
foo(2) // 4
```

- `foo(2)` 传参的操作, 实际上为参数 `a` 进行了隐式的赋值操作 `a = 2`
- 变量 `a` 存在于 `foo` 的函数作用域中, 外部无法访问
- `foo` 函数中引用了 `b` 变量, 引擎会先尝试在 `foo` 函数作用域中查找(RHS)该变量, 如果找不到, 就会往上一级作用域查找, 以此类推, 直到找到为止, 而这里的 `b` 变量, 存在于 **全局作用域** 中.

根据以上示例, 我们可以把作用域比作一个建筑, 这个建筑代表程序中的嵌套作用域链, 第一层代表当前的执行作用域, 建筑的顶层代表全局作用域

LHS 和 RHS 引用都会在当前楼层进行查找, 如果没找到, 就会坐电梯上一层, 以此类推, 最后到达顶楼(全局作用域), 无论程序是否已经找到你所需的变量, 都为到此为止.

#### 作用域的异常

##### ReferenceError

`ReferenceError` 同作用域判别失败相关

```javascript
> const a = 1
> b

< Uncaught ReferenceError: b is not defined
```

##### TypeError

`TypeError` 则代表作用域判别成功了, 但是对结果的操作是非法或不合理的:

- 引用 null 或 undefined 类型值中的属性

```javascript
> null.a
< Uncaught TypeError: Cannot read property 'a' of null
```

- 对一个非函数类型的值进行函数调用

```javascript
> const a = 1
> a()
< Uncaught TypeError: a is not a function
```

------

#### 词法作用域

> 词法, 指的书写代码的阶段, 就是说, 你写代码的时候将变量和块作用域写在哪里, 将决定 **词法作用域**

```javascript
function foo(a) {
    var b = a * 2

    function bar(c) {
        console.log(a, b, c)
    }

    bar(b * 3)
}

foo(2) // 2, 4, 12
```

#### 遮蔽效应

> 在多层的嵌套作用域中可以定义同名的标识符, 这叫"遮蔽效应"(内部的标识符"遮蔽"了外部的标识符)

```javascript
var a = 1
function foo() {
    var a = 2
    console.log(a)
}

foo()         // 2
console.log(a) // 1
```

> 我们再来看一个容易混淆的例子:

```javascript
var a = 1

function foo() {
    console.log(a)
}

function bar() {
    var a = 2
    foo()
}

bar()
```

这个例子, 你可能以为最终会输出 `2`, 因为在 `bar` 函数内部我们又声明了一次 `var a = 2`, 但事实上输出的是 `1`;

我们要牢牢记住, **词法作用域**只关注函数在何处被声明, 而不是在何处被调用, 以上例子, `foo` 函数位于全局作用域被声明, 所以它对 `a` 变量的 RHS 查找当然是在 **全局作用域** 中.

#### 欺骗词法

理解**欺骗词法**很简单, 即我们定义作用域时, 并不是通过书写代码的阶段定义的, 而是在运行的阶段定义, 如下示例:

```javascript
function foo(str, a) {
    eval(str)
    console.log(a + b)
}

foo('var b = 2', 3)  // 5
```

该示例, `foo` 函数内部作用域中在书写代码时没有定义变量 `b`, 而是在运行过程中, 执行了 `eval` 函数, 通过解析传入字符串 `var b = 2` 得到了这一变量

------

#### 函数作用域

> 函数内部的全部变量都可以在整个函数范围内使用和复用, 函数外部无法访问到这些变量

```javascript
function bar() {
    var a = 1
    function foo(b) {
        console.log(a + b)
    }

    foo(3)
}

bar() // 4

// 外部访问这些变量, 会抛出异常
> console.log(a)
< ReferenceError: a is not defined
> foo(3)
< ReferenceError: b is not defined
```

------

#### 块作用域

> ES6 以前, Javascript 并不存在块作用域

```javascript
for (var i = 0; i < 10; i ++) {
    console.log(i)
}

> window.i
< 10
```

我们预期只想在循环中使用变量 `i`, 但它却被声明为一个全局变量

```javascript
if (true) {
    var a = 1
}

> window.a
< 1
```

同样的情况也出现在 `if` 代码块中

> ES5 以下如何实现块作用域?

我们知道, ES3 的 `try/catch` 的 `catch` 语句中会形成一个天然的 **块作用域**, 但这样的写法不仅丑陋, 而且让人难以理解:

```javascript
try { throw undefined } catch(a) {
    a = 2
    console.log(a) // 2
}
```

#### let/const

> 为了解决这个问题, ES6 引入了 `let/const` 关键字, 他们可以将变量绑定到所在的任意作用域中, 通常是`{...}`内部, 换句话说, `let` 为其声明的变量隐式劫持了所在的块作用域

```javascript
// for 循环头部的 let 不仅将 i 绑定到了 for 循环中, 事实上它将其重新绑定到了循环的每一个迭代中, 确保使用上一个循环迭代结束时的值重新进行赋值
for (let i = 0; i < 10; i ++) {
    console.log(i)
}

> window.i
< ReferenceError: i is not defined
if (true) {
    const a = 1
}

> window.a
< ReferenceError: a is not defined
{
    const a = 1
    const b = 2
}

let c = a + b

< ReferenceError: a is not defined
```

------

#### 提升

##### 变量提升

> 我们都认为, `Javascript` 会从上到下一行一行地执行, 但实际上并不完全正确

看以下两个示例:

```javascript
a = 1
console.log(a)
var a

< 1
console.log(a)
var a = 1

< undefined
```

> 为何第一个示例会出现如此匪夷所思的结果?

当我们在代码中看到 `var a = 1` 时, `Javascript` 实际上会将其看成两个声明 `var a`; `a = 1`;

- `var a` 是在编译阶段进行的;
- `a = 1` 赋值声明会在**原地**等待**执行**阶段, 才进行处理

所以, 就算 `var a` 放在了代码最后, 它在浏览器解析过程中, 仍会比**赋值或其他运行逻辑**快一步, *被放在了代码的最前面*, 也就是**变量提升**, 所以第一个示例输出了正确的值;(无论作用域中的声明出现在什么地方, 都将在代码本身被执行前首先进行处理)

而第二个示例, 虽然 `var a` 被**提升**了, 但查询 `a` 比赋值 `a` 早了一步, 所以输出是 `undefined`.

##### 函数提升

同样的, 函数声明也会被**提升**.

```javascript
foo()
function foo() {
    console.log(1)
}

< 1
```

结合前面**变量提升**的知识, 我们可以看到, 通过 `var` 声明的函数, 同样适用变量提升的原则:

```javascript
foo()
var foo = function() {
    console.log(1)
}

< TypeError
```

> 但为什么是 `TypeError` 而不是 `ReferenceError` ?

- `var foo` 因为**变量提升**, 已经被分配到了其所在的全局作用域, 作用域中已经存在 `foo` 变量了, 所以不会导致 `ReferenceError`;
- 但执行 `foo()` 的时候, 赋值操作并未执行, 实际上我们执行的是一个 `undefined`, 浏览器当然会抛出 `TypeError`

##### 函数优先

> 函数声明和变量声明都会被提升, 但函数会首先被提升, 然后才是变量

```javascript
foo()

var foo

foo = function() {
  console.log('Var')
}

function foo() {
  console.log('Function')
}

< Function
```

当然, 后面的函数声明是可以覆盖前面的:

```javascript
foo()

function foo() {
    console.log(1)
}

function foo() {
    console.log(2)
}

< 2
```

------

#### 闭包

##### 基本概念

> 当函数可以记住并访问所在的词法作用域时, 就产生了闭包, 即使函数是在当前词法作用域之外执行(你不知道的 JavaScript 上)

> 闭包就是能够读取其他函数内部变量的函数(百度百科)

我们知道, **函数作用域**中的变量, 我们在外部是无法访问到的, 如以下示例, 常规手段, 我们永远无法在外部访问 `foo` 函数内部的*计算结果(res 变量)*

```javascript
function foo() {
    const res = 1 + 1
}

console.log(res)

< ReferenceError
```

但我们知道, 通过回调函数可以做到这一点:

```javascript
function foo(callback) {
    const res = 1 + 1
    callback(res)
}

foo(function(res) {
    result = res
})

console.log(result)

// 还记得变量提升么?
var result

< 2
```

当执行函数 `foo` 时, 实际上我们隐式为 `callback` 参数赋值了一个方法, 该方法不属于 `foo` 函数的作用域, 但它却能访问到 `foo` 函数内部的变量, 所以这就是一个**闭包**!

我们知道 `Javascript` 存在**垃圾回收**机制, 原本 `foo` 函数执行完毕后, 整个内部作用域应该被销毁掉, 但由于 `callback` 函数拥有涵盖 `foo` 函数内部作用域的闭包, 所以内部作用域被神奇的保存了下来, 并为 `callback` 所用

#### 闭包的形式

- 分配给全局变量

```javascript
var fn
function foo() {
  var a = 1
  function bar() {
    console.log(a)
  }

  fn = bar
}

foo()

fn() // 1
```

- 通过内部返回函数方法

```javascript
function foo() {
    var a = 2
    function bar() {
        console.log(a)
    }

    return bar
}

var baz = foo()

baz() // 2
```

- 回调函数

```javascript
function foo(callback) {
    var a = 3
    callback(a)
}

foo(function (p) {
    console.log(p)
})  // 3
```

#### 循环和闭包

看如下示例代码:

```javascript
for (var i = 0; i <= 5; i++) {
    setTimeout(function() {
        console.log(i)
    }, i * 1000)
}
```

正常情况下, 我们对这段代码行为的预期是分别输出 1~5, 每秒一次, 每次一个;

但实际上这段代码在运行时会以每秒一次的频率输出五次6;

> 是什么导致了如此它的行为同语义暗示的不一致呢?

- 首先, 我们知道, `var` 的声明下, `for` 循环没有自己的块作用域, 也就是说, `i` 位于全局作用域中, 整段程序只有唯一一个 `i`;
- `setTimeout` 作为异步函数, 在程序执行过程中, 会被推到**任务队列**中, 等待所有同步函数执行完毕后再执行, 所以, 当 `for` 完成循环后, 全局变量 `i` 已经变成了 6, 自然在执行异步函数时输出的都是6了.

> 如何使用**闭包**解决这个问题?

`LIFE` 函数会通过声明立即执行一个函数来创建**函数作用域**, 通过这个特性, 我们可以在每次循环时, 将当前状态的 `i` 传递到 `LIFE` 函数中, 在内部为 `setTimeout` 创建一个新的作用域;

以下代码能够获得我们预期的结果:

```javascript
for (var i = 0; i <= 5; i++) {
    (function(j) {
        setTimeout(function() {
            console.log(j)
        }, j * 1000)
    })(i)
}
```

> 有更简单的解决方案么?

答案是肯定的! 前面我们说到过 `let` 声明, 它可以用来劫持块作用域;

for 循环头部的 let 不仅将 i 绑定到了 for 循环中, 事实上它将其重新绑定到了循环的每一个迭代中, 确保使用上一个循环迭代结束时的值重新进行赋值;

以下代码能够获得我们预期的结果:

```javascript
for (var i = 0; i <= 5; i++) {
    // i 被劫持了, 现在每次循环都形成一个封闭的块作用域
    let j = i

    setTimeout(function() {
        console.log(j)
    }, j * 1000)
}
```

#### 模块

> 我们平时所使用的**第三方框架**, 为了使自身的变量不会污染到全局中, 都会将所有方法封闭到一个内部私有的作用域中, `LIFE` 函数就能提供这样的一个作用域, 来实现框架的**模块化**

```javascript
var _ = (function() {
    var a = 1
    var b = 2

    function add() {
        console.log(a + b)
    }

    function decrease() {
        console.log(a - b)
    }

    return {
        add: add,
        decrease: decrease
    }
}())

_.add() // 3
_.decrease() // -1
```

这也是一个典型的**闭包**, `_.add()` 在全局作用域下执行, 但它却能够访问到 `LIFE` 函数内部的变量.

### 小结

> 作用域嵌套

我们可以把作用域比作一个建筑, 这个建筑代表程序中的嵌套作用域链, 第一层代表当前的执行作用域, 建筑的顶层代表全局作用域;

LHS 和 RHS 引用都会在当前楼层进行查找, 如果没找到, 就会坐电梯上一层, 以此类推, 最后到达顶楼(全局作用域), 无论程序是否已经找到你所需的变量, 都为到此为止.

> 作用域异常

`ReferenceError`: 作用域判别失败时抛出, 如查询一个不存在的变量

`TypeError`: 作用域判别成功了, 但对结果的操作非法, 如将一个字符串变量当做函数来执行

> 词法作用域

当我们书写代码的时候, 就已经决定了函数的作用域在哪里, 而不是在我们执行函数之后

> 函数作用域

函数内部的作用域是私有的, 外部无法访问到它们

> 块作用域

ES6 之前, 并不存在生成 **块作用域** 的直接方法, 我们使用 `try/catch` 来代替;

ES6 之后, 有了 `let/const`, 这两个关键字事实上并没有生成真正的块作用域, 而是隐式的劫持了关键字所在的快作用域

> 变量提升

`var a = 1`, 会被引擎解析为 `var a;a = 1` 两条语句, 而 `var a` 会在编译时执行, 而 `a = 1` 则会在执行阶段才被处理, 这就造成了变量的提升;

同样, 函数声明也会被提升, 它的优先级甚至还高于变量;

> 闭包

我们知道, **函数作用域** 是不能被外界所访问到的, 但我们可以通过*回调函数* 或 *全局变量* 等方法, 在函数外部访问到函数内部的变量, 这就是**闭包**;

我们经常使用的 `$.ajax`, 就是典型的闭包, 甚至整个 `jQuery` 包或其他第三方包的编写, 为了避免污染全局变量, 都会使用 `LIFE` 函数创建一个闭包, 并返回包含插件所有方法的 `$` (每个框架变量名不同) 对象.

### 十二、this指向

#### this基本概念

`this` 是个很特别的关键字, 被自动定义在所有函数的作用域中;

`this` 关键字并不会像它的字面意思那样, 指向函数自身; 相对**词法作用域**(只关注函数在何处声明), 它的行为更像**动态作用域**(只关注函数从何处调用);

> 下面一个简单例子, 解释**词法作用域**和**动态作用域**的区别:

```javascript
function foo() {
    console.log(a)
}

function bar() {
    var a = 2
    foo()
}

var a = 1

bar()
```

运用**词法作用域**:

- `foo` 函数在全局作用域下声明, 所以其**作用域内部**可以访问到全局作用域的 `a`, 但它访问不到 `bar` 函数内部的 `a`;
- 输出结果 `1`

运用**动态作用域**:

- `foo` 函数在 `bar` 函数内部调用, 第一个查找到的 `a` 变量是 `bar` 函数作用域内部的 `a`;
- 输出结果 `2`

------

#### 绑定的四大规则

> `this` 的指向, 是根据函数`调用的位置` 决定的, 我们必须先找到调用位置, 然后判断其适用以下四条规则的哪一条

##### 默认绑定

我们可以把这条规则看做无法使用其他规则时的默认规则;

**直接使用不带任何修饰的函数引用**, 在调用时, 只能使用 `默认绑定`;

`默认绑定` 会将 `this` 绑定到 `window` 对象上;(`this === window`)

```javascript
function foo() {
  console.log(this === window)

  bar() // true
}

function bar() {
  console.log(this === window)
}

foo() // true
```

> 但在严格模式下, **默认绑定**会绑定一个 `undefined`:

```javascript
"use strict"

function foo() {
  console.log(this)
}

foo() // undefined
```

##### 隐式绑定

通过考虑 **调用位置**是否具有**上下文对象**, 或者说是否被某个对象拥有包含, 来判断是否运用这条规则:

> 如下示例, 我们声明一个 `foo` 函数, 并将其赋值给 `obj` 对象的 `foo` 属性:

```javascript
function foo() {
    console.log(this.a)
}

var obj = {
    a: 1,
    foo: foo
}

obj.foo() // 1
foo()     // undefined
```

> 对象属性引用链中只有最后一层在调用位置中起作用, 如下:

```javascript
function fn() {
    console.log(this.msg)
}

var child = {
    msg: 'child',
    fn: fn
}

var parent = {
    msg: 'parent',
    child: child
}

parent.child.fn() // child
```

##### 隐式丢失

如下示例, `o.foo` 的 `this` 隐式绑定在了 `o` 对象上, 而 `bar` 引用了 `o.foo` 函数本身, 所以此时的 `bar()` 其实是一个不带任何修饰的函数调用, 因此使用了 **默认绑定** 规则:

```javascript
var o = {
    a: 1,
    foo() {
        console.log(this.a)
    }
}

var bar = o.foo

o.foo() // 1
bar()   // undefined
```

另一个很出乎意料的例子, 示例中, `bar(o.foo)` 实际上采用了**隐式赋值**: `callback = o.foo`, 事实上跟上面的例子一样, 都是直接引用了 `o.foo` 函数本身, 所以造成了 **隐式丢失**:

```javascript
function bar(callback) {
    callback()
}

var o = {
    a: 1,
    foo() {
        console.log(this.a)
    }
}

bar(o.foo) // undefined
```

##### 显式绑定

现在, 我们并不想通过 **隐式** 或者 **默认** 的方式来间接绑定 `this` 的指向, 我们需要强制的为函数指定一个绑定对象!

我们可以通过使用 `call()` 和 `apply()` 方法来实现;

`JavaScript` 提供的大多数函数以及**我们自己创建的所有函数**都可以使用这两个方法;

```javascript
fn.call(obj Object [, ...arguments])
```

第一个参数接收一个对象, 作为 `this` 关键字绑定的对象, 第二个参数是该函数传递的参数;

```javascript
function foo(a, b) {
    console.log((a + b) * this.c)
}

var obj = {
    c: 2
}

foo.call(obj, 1, 2) // 6

// foo.apply(obj, [1, 2])
// call() 与 apply() 的效果完全一致, 唯一不同的只是传递参数的格式不同
```

##### 硬绑定

使用**显示绑定**时, 我们重复进行绑定, 仍然会让之前的绑定值丢失:

```javascript
var obj = { name: 'muzi' }

function foo() {
    console.log(this.name)
}

foo.call(obj)  // muzi

setTimeout(() => (
    foo.call({ name: 'yaya' } // yaya
)), 100)
```

如果我们想避免这种情况, 就需要使用 **硬绑定**;

硬绑定的典型应用场景就是创建一个**包裹函数**, 传入所有的参数并返回接收到的所有值:

```javascript
var obj = {
    name: 'muzi'
}v

function foo() {
    console.log(this.name)
}

function wrapper() {
    foo.call(obj)
}

wrapper()  // muzi
wrapper.call({ name: 'yaya' })  // muzi
```

虽然 `wrapper` 绑定了一个新的对象, 但当 `wrapper` 每次被调用时, `foo` 都会显示绑定 `obj` 对象;

所以无论 `wrapper` 如何调用, `foo` 函数的绑定值都不会被改变.

> 我们可以根据这个特性, 创建一个**辅助绑定函数**:

```javascript
function bind(fn, obj) {
  return function() {
    return fn.apply(obj, arguments)
  }
}
function foo(b, c) {
    return this.a + b + c
}

var bar = bind(foo, { a: 1 })

bar(2, 3) // 6
bar.call({ a: 10 }, 2, 3) // 6
```

> 事实上, 早在 `ES5` 就提供了原生的**硬绑定**方法: `Function.prototype.bind`

```javascript
var bar = foo.bind({ a: 1 })

bar(2, 3)  // 6
bar.call({ a: 10 }, 2, 3)  // 6
```

> `Function.prototype.bind` 的实现:

```javascript
Function.prototype._bind = function(obj) {
  var self = this
  return function() {
    return self.apply(obj, arguments)
  }
}
```

#### new 绑定

> 构造函数只是一些使用 `new` 操作符时被调用的函数, 它们并不会属于某个类, 也不会实例化一个类, 它们只是被 `new` 操作符调用的普通函数而已

#### 普通函数

以下示例, `Person` 是一个所谓的构造函数, 根据**默认绑定**的规则, `Person` 被调用时, 内部的 `this` 应当指向**全局作用域**;

因此, 当我们访问 `person.name` 时, 会得到 `TypeError` 的结果, 因为 `Person()` 没有返回任何东西, 是个 `undefined`

```javascript
function Person() {
  this.name = 'muzi'
}

const person = Person()

console.log(window.name) // muzi
console.log(person.name) // TypeError
```

可以看到, 没有被 `new` 操作符调用的所谓构造函数, 仅仅是普通函数而已

#### 构造函数

```javascript
const person = new Person()

console.log(window.name)  // undefined
console.log(person.name)  // muzi
```

我们会得到截然不同的结果, 这是因为 `new` 操作符做了以下四件事情:

- 创建或构造了一个全新的对象
- 这个新对象会被执行[[原型]]连接
- 函数中的 `this` 会指向这个新对象
- 如果被调用的函数没有返回(return), 则 `new` 表达式中的函数调用会自动返回这个新对象 *(对没错, 就是普通的对象, 带花括号的那种!)*

#### 优先级

```javascript
new` > `显式绑定` > `隐式绑定` > `默认绑定
```

##### ES6 箭头函数

> 箭头函数不使用 `this` 的四种标准规则, 而是根据**词法作用域**来决定 `this`

```javascript
var obj = { a: 1 }

// 1
function fn() {
    setTimeout(function() {
        console.log(this.a)
    }, 1000)
}

fn.call(obj)  // undefined

// 2
function arrow() {
    setTimeout(() => {
        console.log(this.a)
    }, 1000)
}

arrow.call(obj) // 1
```

##### 代码片段1:

`fn` 的 `this` 指向 `obj`, `setTimeout` 的回调函数是个普通函数, 并且在没有任何修饰的情况下引用, 执行 `默认绑定` 规则, 其 `this` 指向全局作用域

> 这种情况下, 通常有两种方法, 可以让回调函数绑定到父级的 `this`

```javascript
var obj = { a: 1 }

function fn() {
    var self = this
    setTimeout(function() {
        console.log(self.a)
    }, 1000)
}

fn.call(obj) // 1
var obj = { a: 1 }

function fn() {
    setTimeout(function() {
        console.log(this.a)
    }.bind(this), 1000)
}

fn.call(obj) // 1
```

##### 代码片段2:

```javascript
arrow` 的 `this` 指向 `obj`, `setTimeout` 的回调函数是个箭头函数, 根据 **词法作用域**, 该箭头函数的 `this` 也指向 `obj
```

### 小结

如果要判断一个运行中函数的 `this` 绑定, 就需要找到这个函数的直接调用位置. 找到之后 就可以顺序应用下面这四条规则来判断 `this` 的绑定对象:

- 由 `new` 调用? 绑定到新创建的对象
- 由 `call` `apply`(或 bind) 调用? 绑定到指定对象
- 由 上下文对象(context) 对象调用? 绑定到那个上下文对象
- 默认: 在严格模式下绑定到 `undefined`, 否则绑定到全局对象
