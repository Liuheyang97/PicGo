# JAVA

SE（基础、算法）      Java Web（内容很多）        单体架构、算法         Spring、spring Boot

需要学习的内容：

## 一、Java编程基础

​		环境搭建

​		IDEA 开发工具

​				新建项目

​				运行调试

​				界面配置

​				插件管理

​		Java 基础语法

​				数据类型

​				流程控制

​		数组

​		面向对象

​				方法

​				重载

​				封装

​				继承

​				多态

​		抽象类

​		接口

​		枚举

​		常用类

​				String

​				日期时间

​		集合类

​		泛型

​		注解

​		异常处理

​		多线程

​		IO 流

​		反射

## 二、Java 8 （3天）

​		Stream API

​		Lambda 表达式

​		新日期时间 API

​		接口默认方法



IO   集合   SSM框架   JavaWeb   集群    数据库    分布式    ElasticeSearch     微服务   面向对象    API



# CDM

| CMD命令            |                                                              |
| ------------------ | ------------------------------------------------------------ |
| 盘符名称+冒号      | 磁盘切换，Eg：E:回车  （英文状态下的）                       |
| dir                | 查看当前路径下的内容（同时包括隐藏的文件夹）                 |
| cd+目录            | 进入单级目录    Eg：cd QQ  （如果目录（文件名）过长，可以只打出前几个字母，然后按Tab键自动关联）         注：cd **  打开的是文件夹，如果需要打开某个程序（如QQ.exe），则需要到存有QQ.exe的文件夹目录下，直接输入QQ.exe，回车即可！ |
| cd ..              | 回退到上一级目录                                             |
| cd 目录1\目录2\... | 进入多级目录                                                 |
| cd \               | 回退到盘符根目录                                             |
| cls                | 清屏                                                         |
| exit               | 推出命令提示符窗口                                           |
|                    |                                                              |

为什么要配置系统环境变量？

​	想要在$\textcolor{red}{任意的目录下}$都可以打开指定的软件。就可以把软件的路径配置到环境变量中。（这样在使用cmd打开某个软件时，就不需要再到该软件（exe）的文件目录下）。

在安装完JDK后系统会帮我们在Path里面自动配置好环境变量，但是这样的配置只有四个功能：

C:\Program Files\Common Files\Oracle\Java\javapath （系统自动配置的path变量）

![](../../typora/Photo File/photo202403271816933.png)

那么要想使用其他更多的功能，则$\textcolor{red}{用下面的配置方法}$：

①首先新建一个系统变量，变量值为JDK的文件路径；这样配置的JAVA_HOME也可以为其他软件服务！

![](../../typora/Photo File/photo202403271817945.png)

②然后去path里面将JAVA_HOME引用一下，如下图所示：

![](../../typora/Photo File/photo202403271818937.png)





​	后缀为java的是java语言未编译的代码； 在cmd中是通过javac来对其进行编译；编译完会形成新的后缀为class的文件。

​	后缀为class的是已经编码的，可供操作系统执行的代码文件！通过java来运行编译后的代码！（运行时不加class后缀名）

​	$\textcolor{red}{javac 和 java}$都是JDK提供的一个工具！

​	$\textcolor{red}{Java中需要注意大小写区分}$，同时所有的标点符号都需要是英文标点符号。



![](../../typora/Photo File/photo202403271818623.png)

![](../../typora/Photo File/photo202403271818904.png)





# 01 Java基础语法

Java中有两种比较对象的方法：====运算符和equals方法。==

==运算符用于$\color{red}{比较两个对象的引用}$，如果它们指向的是同一个对象，则返回true；

而equals方法用于==比较两个对象的内容是否相等==，当它们的内容相等时，则返回true。

（使用方式：a.equals(b);    对比 a 和 b 指向的内容是否一致！）

因此，equals方法可以用于比较两个值相同的字符串、整型等基本数据类型，或需要通过内容比较才能确定相等的自定义类对象等。



class文件是放在out里面！

![](../../typora/Photo File/photo202403271819105.png)



## 一、字面量

字符必须单引号围起来，有且仅能一个字符。   Eg：’A’

字符串必须用双引号围起来，字符数量不限。   Eg：”啊啊啊啊啊啊啊啊”

布尔类型只有2个值：true、false



## 二、变量

​		变量就是用来存储一个数据的内存区域（可以理解成盒子），且里面存储的数据可以变化。  Eg：微信钱包中的金额。

### 		格式：

 数据类型 变量名称 = 初始值；      Eg：int age = 24；

```
//综合在一起输出， 用+号； 在c中使用，逗号！
System.out.println("还有"+age+"年30岁！");
```

这里有一个重点：

​    $\textcolor{blue}{String code = “” ;} $定义一个字符串变量记录生成的随机字符

​    那么此时如果有 $\textcolor{blue}{code += ch;}$  ch为生成的字符或数子

​    $\color{red}{但是由于code为String类型，所以他们不是相加，而是combine（组合）。}$

①  什么类型的变量一定是存放什么类型的数据

②  同一数据内（同一个main内）不能定义重名的变量

③  变量定义的时候可以不给初始值，但是使用的时候必须有初始值

④  变量存在访问范围

```
//4、变量存在访问范围
{
    int A = 24;
}
System.out.println(A);  //报错，无法解析A

```



## 三、数据类型

基本数据类型

​	整数：byte < short < int（默认） < long

​	浮点数：float < double（默认）

​	字符：char

​	布尔：boolean

引用数据类型

​       String

## 四、类型转换

Why?    存在不同类型的变量赋值给其它类型的变量

①  自动类型转换

$\textcolor{red}{类型范围小的变量，可以直接赋值给类型范围大的变量。}$

byte →  short → int → long → float → double

char →  int

②  表达式的自动类型转换

在表达式中，$\color{red}{小范围类型}$的变量会$\color{red}{自动转换成当前较大范围的类型再运算。}$

byte、short、char  →  int  →  long  →  float  →  double

Eg：byte类型的数和int类型的数进行计算时，会先将byte类型转换为int，再进行计算。

注意：

- 表达式的最终结果类型由表达式中的$\color{red}{最高类型决定}$。

- 在表达式中，byte、short、char是$\color{red}{直接转换成int类型参与运算的。}$

③  强制类型转换 

场景

```
            int a = 功能1();          功能2(byte b);  
            
            int a = 20;              byte b = a; //报错
```

 

问题：$\color{red}{类型范围大}$的数据或者变量，$\color{red}{不能直接赋值给类型范围小的变量}$，会报错。



$\color{red}{可以强行将类型范围大的变量、数据赋值给类型范围小的变量。}$

​       $\color{red}{数据类型}$   变量2 = $\color{red}{（数据类型）}$变量1、数据;

​       Eg： int a = 20;

​          byte b = (byte)a;

 

注意：

==在进行强制类型转换时，大类型变量的数值必须在小类型变量的数值范围内，否则会发生错误;==

==即强制类型转换可能造成数据（丢失）溢出；==

浮点型强转成整形，直接丢掉小数部分，保留整数部分返回！

​           Eg： int a = 1000;

​                   byte b = (byte)a;

​                   System.out.println(b); //输出-24

## 五、运算符（Scanner键盘录入技术）

1、基本运算符：\+   -   *   /   %

```
int a = 10;
int b = 3;
System.out.println(a + b);
System.out.println(a - b);
System.out.println(a * b);
System.out.println(a / b);   //3.3333 ==> 3
//下面乘1.0的先后顺序要注意
System.out.println(a * 1.0 / b); //3.333333
System.out.println(a / b * 1.0); //3.0
```

注意运算的先后顺序！

==如果两个整数做除法，其结果一定是整数，因为最高类型是整数。如果需要结果为小数，则在第一个数（变量）后面乘1.0。==

2、连接符

​    “+“符号与字符串运算的时候是用作连接符的，其结果依然是一个字符串。

​    （能算就算，不能算就在一起！）

```
 int a = 5;
 System.out.println("abc" + 'a'); //abca
 System.out.println("abc" + a);  //abc5
 System.out.println(a + 5);  //10
 System.out.println("adc" + 5 + 'a');  //abc5a

 System.out.println(a + 'a');  //102    字符a在底层中是当二进制进行存储的，字符a=97！
 System.out.println(a + "" + 'a');  //5""a   因为字符a前面有一个字符串，因此不能进行计算！
 System.out.println(a + '' + 'a');  //报错，因为单引号里面有且仅能有一个字符，必须有一个字符！

 System.out.println(a + 'a' + " Liu");  //102 Liu
 System.out.println("Liu" + ( a + 'a'));  //Liu102

```



3、自增、自减运算符

​	++   自增    变量自身的值加1

​	--     自减    变量自身的值减1

注意：

-   ++ 和 -- 既可以放在变量的后边，也可以放在变量的前边。

- $\color{red}{  ++ 、 -- 只能操作变量，不能操作字面量（字符）。}$

 

++ 、-- 如果不是单独使用（如在表达式中、或者同时有其他操作），放在变量前后会存在明显区别

-  放在变量的==前面==，==先对变量进行+1，-1，==再拿变量的值进行运算

​           int a = 10; 

​           int rs = ++a;        // rs = 11  a = 11

-  放在变量的==后面==，先拿变量的值进行运算，==再对变量的值进行+1，-1==

​          int b = 10;

​          int rs = b++;         // rs =10  b = 11

 

Test：

```
int c = 10;
int b = 5;
// rs = 10  +  12  -  4  +  4  -12  +  4  + 2 = 16
// 从左至右依次计算，由于c和b各仅占一个盒子，因此在计算rs时，c、b也依次进行改变；因此rs表达式中的c、b各不相同
int rs = c++ + ++c - --b + b-- -c-- + ++b +2;
// c = 10 + 1 + 1 - 1 = 11
// b = 5 -1 -1 + 1 = 4

System.out.println(c);
System.out.println(b);
System.out.println(rs);
```

 

4、赋值运算符

①  基本赋值运算符

就是  ==“=”==

int a =10;     //先看“=”右边，把数值10赋值给左边的变量a存储

② 扩展赋值运算符

![](../../typora/Photo File/photo202403271820123.png)

5、关系运算符

​    是对数据进行条件判断的符号，最终会返回一个比较的布尔结果（true、false）。

![](../../typora/Photo File/photo202403271821484.png)

 

#### 6、逻辑运算符

​    可以把多个条件的==布尔结果放在一起进行运算，==最终返回一个布尔结果

![](../../typora/Photo File/photo202403271821368.png)

短路逻辑运算符

![](../../typora/Photo File/photo202403271821343.png)

#### 7、三元运算符

​    ==格式： 条件表达式？ 值1 : 值2;==

​    执行流程：首先计算==关系表达式的值==，如果值为==true==，返回==值1==，如果为==false==，返回==值2==。

```
double score = 98;
String rs = score >= 60 ? "考试通过" : "挂科";
System.out.println(rs);   //考试通过
```

 

#### 8、运算符优先级

​    在没有括号的情况下，“ * 、/  ”的优先级高于“ + 、- ”。

![](../../typora/Photo File/photo202403271822793.png)

 

#### 9、案例知识：键盘录入技术（即输入技术！）

![](../../typora/Photo File/photo202403271822406.png)



## 六、程序流程控制（Random随机数）

1、 顺序结构

​		程序中没有写其他结构，那么则按照代码的先后顺序，依次执行代码！

 

2、 分支结构 If、switch

​		根据判定的结果（真或假）决定执行某个分支的代码

①  if分支有三种格式

 

```
if（条件表达式）{          if（条件表达式）{               if（条件表达式1）{

    语句体；                  语句体1；                    语句体1；

}                        } else {                     } else if（条件表达式2）{

                             语句体2；                    语句体2；
                          }                           } else if（条件表达式3）{

                                                         语句体3；
                                                      }
                                                        ………

                                                      else {

                                                             语句体n+1；
                                                      }
```



 

②  switch分支

也是匹配条件去执行分支，==适合做$\color{green}{值（字符）匹配}$的分支选择，结构清晰，格式良好。==

  执行流程：

​    1）先执行表达式的值，拿着这个值去与case后的值进行匹配。

​    2）匹配哪个case的值为true就执行哪个case，==遇到break就跳出switch分支。==

​    3）如果case后的值都不匹配则执行default代码。

​     switch（表达式）{

​      case 值1：

​          执行代码……；

​          break；

​      case 值2：

​          执行代码……；

​          break；

​      …

​      case 值n-1：

​          执行代码……；

​          break；

​      default：

​          执行代码n；

}



switch案例：周一 ----周日的备忘录

switch分支注意事项：

​    1）表达式类型==只能是byte、short、int、char，==JDK5开始支持枚举，JDK7开始支持String、==不支持double、float、long。==（小数类型的数值，进行计算时，不精确；可以看SwitchDemo3.java代码）

​    2）==case给出的值不允许重复，==且只能是字面量，不能是变量。

​    3）==不要忘记写break，==否则会出现穿透现象！==（有好有坏）==

 

switch的穿透性==（有好有坏）==

   ==如果代码执行到没有写break的case块==，执行完后将直接进入下一个case块执行代码==（而且不会进行任何匹配）==，直到遇到break才跳出分支，这就是switch的穿透性。

![](../../typora/Photo File/photo202403271823336.png)

```
//使用switch的穿透性解决此问题
switch (month){
    case 1:
    case 3:
    case 5:
    case 7:
    case 8:
    case 10:
    case 12:
        System.out.println(month + "月是31天");
        break;

    case 2:
        System.out.println(month + "月闰年为29天、非闰年为28天");
        break;

    case 4:
    case 6:
    case 9:
    case 11:
        System.out.println(month + "月是30天");
        break;
}
```

==适用于很多case输出结果一致的情况！可以用穿透性把流程集中到同一处处理，可以简化代码！==

 

3、 循环结构 for、while、do...while

①  for 循环

格式：

​       for（初始化语句；循环条件；迭代语句）{

​              循环体语句（需要重复执行的代码）；

​       }

​    

②  while 循环

==先判断，再执行！==

格式：

​       初始化语句；

​        while（循环条件）{

​             循环体语句（被重复执行的代码）；

​            迭代语句；

​       }

 

 ==什么时候用for循环，什么时候用while循环?==

 ==1、功能上是完全一样，for能解决的while也能解决，反之亦然==

 ==2、使用规范是：知道循环几次：使用for；不知道循环几次建议使用：while==

 

③  do...while循环

==先执行再判断循环条件==

初始化语句；

 

do{

​      循环体语句;

​      迭代语句;

}while（循环条件/判断条件）;

​       

​       ==do-while循环的特点：一定会先执行一次循环体。==

![](../../typora/Photo File/photo202403271823877.png)

 

 

④  死循环

一直循环的执行下去，如果没有干预不会停止下来。

```
for (; ; ) {
    System.out.println("Hello World!");
}

//经典写法
while (true){
    System.out.println("Hello World!");
}

do{
    System.out.println("Hello World!");
}while(true);
```

 

⑤  循环嵌套

​         循环中又包含循环！

​         ==特点：外部循环每循环一次，内部循环全部执行完一次==

4、 跳转关键字 break、continue

==break：跳出并结束当前所在循环的执行。==

==continue：用于跳出当前循环的当次执行，进入下一次循环。==

 

注意：

​    ==break：只能用于结束所在循环，或者结束所在switch分支的执行。==

​    ==continue：只能在循环中进行使用。==

 

###### ==注意==

==while上面加一个OUT：（大写的）；然后在需要结束整个死循环的地方写上break OUT； 当执行到 break OUT时，会直接跳出while循环。详细请看Javase – Array—Traverse—ArrayTest3.java==

 

 

#### 5、 案例技术：随机数Random类

①  Random的使用

![](../../typora/Photo File/photo202403271824792.png)

Random生成区间随机数的技巧：减加法

![](../../typora/Photo File/photo202403271824482.png)

```
//1、导包
//2、创建随机数对象
Random random = new Random();
//3、调用nextInt功能（方法）可以返回一个整数的随机数给你
for (int i = 1; i <= 20; i++) {
    int data = random.nextInt(10); //0 - 9 不包含10，包前不包后！
    System.out.println(data);
}

System.out.println("-------------------------");

// 1  -   10  ==>  -1 ==> (0 - 9) + 1
int data = random.nextInt(10) + 1;
System.out.println(data);

// 3  -   17  ==>  -3 ==> (0 - 14) + 3
int data1 = random.nextInt(15) + 3;
System.out.println(data1);
```



## 七、数组、Debug

1、 数组

数组就是用来存储==一批同种类型数据==的==内存区域（可以理解成容器）==。

==数组适合做一批同种类型数据的存储！==

例子：

​		int[] arr = {1, 2, 3, 4, 5, 6, 7, 8, 9};

​		string[] names = {“张三”, ”李四”, ”王五” };

 

![](../../typora/Photo File/photo202403271825451.png)

==注意：数组变量名中存储的是数组在内存中的地址，数组是引用类型！即数组名称所代表（所存储）的是元素的初始地址！==

 

2、 数组的定义

①  静态初始化数组

​     定义数据的时候直接给数组赋值。

​	 格式：数组类型[ ] 数组名 = new 数据类型[ ]{……};

​    			简化写法：数组类型[ ] 数组名 = {……};

 

数组的访问：==数组名称[索引]== 

Eg：System.out.println(arr[0])；

​        System.out.println(==arr.length==); //获取数组长度   

​		==赋值：数据名称[索引] = 数据；==



数组的最大索引可以怎么表示？  ==数组名.length – 1==； 因为数组是从0开始。前提：元素个数大于0。

数组一旦定义出来，==程序执行的过程中，长度、类型就固定了！==

 

②  动态初始化数组

​		定义数组的时候==只确定元素的类型和数组的长度，之后再存入具体数据。==

​		格式： 数据类型[ ] 数组名 = new 数据类型[长度];

​      			   int[ ] arr = new int[20];

 

区别：

​    1、当前已经知道存入的元素值，用静态初始化。

​    2、当前还不清楚要存入哪些数据，用动态初始化。

 

动态初始化数组的默认值：

![](../../typora/Photo File/photo202403271825977.png)

​    两种初始化的使用场景总结、注意事项说明：

​    1、动态初始化：只指定数组长度，后期赋值，适合开始知道数据的数量，但是不确定具体元素值的业务场景。

​    2、静态初始化：开始就存入元素值，适合一开始就能确定元素值的业务场景。

​    3、两种合适的写法是独立的，不可以混用。

​        ==Eg： int[ ] arr = new int[4]{1, 2, 3, 4} ;     这是错误的==

 

3、 数组的遍历

遍历：就是一个一个数据的访问。  ==遍历数组的快捷方式：数组名.fori==

 

4、 数组的案例

①  数组元素求和

②  数组求最值

在进行编码的时候，需要定义一个变量用于记录最大值，并且这个变量建议默认存储第一个元素值作为参照（此时，可以直接从第二个元素开始比较）。因为如果你定义这个变量为0，那么如果数组中全是负数/正数，那么0就成为了最大值/最小值，显然是错误的！

③  猜数字游戏

```
OUT:

while(true) {
    System.out.print("请您输入1-20之间的整数进行猜测：");
    int cai = scanner.nextInt();
    for (int i = 0; i < number.length; i++) {
        if (cai == number[i]) {
            System.out.println("运气不错，猜中了！您猜中的数据索引是： " + i);
            
            break OUT;    //结束了整个死循环
            
        }
    }
            System.out.println("未命中，请继续猜测！");

}

```

 

###### ==注意==

==while上面加一个OUT：（大写的）；然后在需要结束整个死循环的地方写上break OUT； 当执行到 break OUT时，会直接跳出while循环。详细请看Javase – Array—Traverse—ArrayTest3.java==

 

 

④  随即排名

需求：某公司开发部5名开发人员，要进行项目进展汇报演讲，现在采取随机排名后进行汇报。请先依次录入5名员工的工号，然后展示出一组随机的排名顺序

![](../../typora/Photo File/photo202403271825894.png)

```
//1、动态初始化一个数组，存储5个工号
int[] codes = new int[5];
Scanner scanner = new Scanner(System.in);

//2、定义一个循环，循环5次，依次录入一个工号存入对应的位置
for (int i = 0; i < codes.length; i++) {
    System.out.println("请您输入第" + (i + 1) + "个员工的工号：");
    int code = scanner.nextInt();
    //存入到数组中去
    codes[i] = code;
}

//3、遍历数组中的每个元素，然后随机一个索引出来，让该元素与随机索引位置处的元素值进行交换（重点）
Random r = new Random();
for (int i = 0; i < codes.length; i++) {
    //随机一个索引位置出来；
    int index = r.nextInt(codes.length);
    int replace = codes[i];
    codes[i] = codes[index];
    codes[index] = replace;
}
for (int i = 0; i < codes.length; i++) {
    System.out.print(codes[i] + "\t");
}

```

详细请看Javase – Array—Traverse—ArrayTest4.java

 

⑤  数组排序

对数组中的元素，进行升序（由小到大）或者降序的操作。

排序技术：冒泡排序、选择排序、快速排序、插入排序；

搜索技术：二分搜索、分块查找、哈希表查找



5、 数组的内存图

​    ①  Java内存分配介绍

  	  栈：==方法（main）运行时所进入的内存，变量也是在这里！==
  	
  	 堆：new出来的东西会在这块内存中开辟空间并产生地址。（new出来的东西叫对象）
  	
  	  方法区：字节码文件加载时进入的内存，==class文件和main放在方法区。==
  	
  					 ==new出来的东西是在堆内存中==

​				      ==但是 arr这个变量名是在栈内存中，存储的是arr所指向的数组的地址==

 

​    本地方法栈

​    寄存器

 

②  两个变量指向同一个数组

 

 

6、 数组使用的常见问题

问题1：如果访问的元素位置超过最大索引，执行时会出现ArrayIndexOutOfBoundsException（数组索引越界异常）！

问题2：如果数组变量中没有存储数组的地址，而是null，在访问数组信息时会出现NullPointerException（空指针异常）。（将arr赋值为null； 即 arr = null；）

==此时访问arr是没有问题的，会返回null；但是如果访问原来arr指向的数组，则会发生错误。==

 

7、 Debug工具的使用

IDEA自带的断点调试（排错）工具，可以控制代码从断电开始一行一行的执行，然后详细观看程序执行的情况。

## 八、方法（return关键字）

==**在任何方法中，只要执行到return，就把该方法直接结束。不管return是在循环，判断等条件语句中，都直接结束当前方法！**==



方法是一种语法结构，它可以把一段代码封装成一个功能，以方便重复调用！

提高了代码的复用性。让程序的逻辑更清晰！ 

```
int c = sum(10 , 20);
public static int sum(int a, int b){
    int c = a + b;
    return c;
}

```

 

==怎么定义方法—怎么调用方法—方法的内存图---方法的参数传递机制---方法其他常见形式、技术==

1、 方法定义、调用

①  方法完整的定义形式、调用

形参列表：==用于接收数据==

==方法定义的完整格式：==

​    修饰符 返回值类型 方法名（形参列表）{  // 修饰符暂时用public static

​       方法体代码（==需要执行的功能代码==）

​        return 返回值；

​    }

![](../../typora/Photo File/photo202403271827808.png)

 

调用格式：方法名（…）；“…“为我们要在“方法”中输入的内容（数值）

​    Eg：int c = ==add(10, 20)==;

​    

注意点：

1）方法的修饰符：暂时都使用public static 修饰。

2）==方法申明了具体的返回值类型，内部必须使用return返回对应类型的数据。==

3）形参列表可以有多个，甚至可以没有；如果有多个形参，多个形参必须用“，“隔开，且不能给初始化值。

 

②  方法的其他定义形式、调用

方法定义时：==返回值类型、形参列表==可以按照需求进行填写。

Eg：打印3行Hello World（使用方法）

```
public static void print() {   //形参列表里面可以什么都不写
	System.out.println(“Hello World!”);
	System.out.println(“Hello World!”);
	System.out.println(“Hello World!”);
}

```



注意事项：

1） 如果方法不需要返回结果，返回值类型必须申明成==void（无返回值）==，此时方法内部==不可以使用return返回数据==。

 

==2、 方法使用的常见问题==

①  方法的编写顺序无所谓

②  方法与方法之间是平级关系，不能嵌套定义，但是可以互相调用！

③  方法的返回值类型为==void（无返回值）==，方法内==则不能使用return返回数据==，如果方法的返回值类型写了$\color{red}{具体类型}$，方法内部则$\color{red}{必须使用return返回}$对应类型的数据。

④  return语句下面，不能编写代码，因为永远执行不到，属于无效的代码。

⑤  方法不调用就不执行，调用时必须严格匹配方法的参数情况。

⑥  有返回值的方法调用时可以选择$\color{blue}{定义变量接收结果}$，或者直接$\color{blue}{输出调用}$，甚至$\color{blue}{直接调用}$；==无返回值方法的调用只能直接调用一下。==

```
//输出调用
System.out.println(sum(100,101));

//直接调用(只是调用方法，让方法跑一下，但是方法返回的结果它不要了)
sum(100, 102);
```

 

3、 方法案例

①  定义方法的技巧，计算1-n的和并返回

在使用方法是真正需要关注的就两点：

​    1、分析方法==是否需要申明返回值类型==

​    2、分析方法==是否需要接收参数==

 详细见Javase\javase\method-app\Demo\Test1

 

②  判断整数是奇数还是偶数

详细见Javase\javase\method-app\Demo\Test2

 

③  数组求最值案例改为方法实现

在方法中，number数组可以传给arr数组；同类型变量可以传输！

详细见Javase\javase\method-app\Demo\Test3

 

 

4、 方法调用的内存图

方法==没有被调用==的时候，在$\color{blue}{方法区}$中的字节码文件中存放。

方法==被调用==的时候，需要进入到$\color{blue}{栈内存}$中运行。

 

 

==5、 方法的参数传递机制==

①  基本类型的参数传递

值传递：在传输实参给方法的形参的时候，并不是传输实参变量本身，而是传输实参变量中存储的值，这就是==值传递==。

 

实参：如在方法内部定义的变量。

形参：如在==定义方法==是，“（）“中所声明的参数

```
public class MethodDemo1 {
    public static void main(String[] args) {
        //目标：理解Java的基本类型的参数传递：值传递。
        int a = 10;
        change(a);
        /*change对a进行改变，但是不影响main中a的值
         因为方法中的a为形参，形参在方法内部的改变与实参（main中的参数）无关
         即实参只是把数字传给形参，而不是把实参本身传给实参
         */
        System.out.println(a);
    }

    public static void change(int a){
        System.out.println(a);
        a = 20;
        System.out.println(a);
    }
}
```

运行结果为：10     20     10 

 

②  引用类型的参数传递

传输存储的地址值。（比如下面代码中的 数组传递）

引用类型的参数传递，是将实参本身（数组地址）传递给形参，因此在形参中对数组进行改变时，实参中的数组也会发生改变！

```
public class MethodDemo2 {
    public static void main(String[] args) {
        //目标：理解引用类型的参数传递机制： 值传递，区分其不同点
        int[] arrs = {11, 22, 33};
        change(arrs);
        System.out.println(arrs[1]);  // 100
    }

    //这里形参接受的是实参的地址，因为是数组引用
    public static void change(int[] arrs){
        System.out.println(arrs[1]);  // 22
        arrs[1] = 100;
        System.out.println(arrs[1]);  // 100

    }
}

```

 

 

==6、 方法的参数传递案例==

①  打印整形数组内容

​		设计一个方法用于输出任意整形数组的内容，要求输出成如下格式：

​		“该数组内容为：[11, 22, 33, 44 , 55]”

分析：

 1）、定义一个方法，要求该方法能够接收数组，并输出数组内容。 需要参数吗？需要返回值类型申			明吗？ 需要，不需要！

2）定义一个静态初始化的数组，调用该方法，并传入该数组。

```
for (int i = 0; i < arr.length; i++) {
    if( i == arr.length - 1) {
        System.out.print(arr[i]);
    }else {
        System.out.print(arr[i] + ",");
    }
    System.out.print(i == arr.length - 1? arr[i] : arr[i] + ",");  //三元运算符
}

```



②  从数组中查询指定元素的索引

设计一个方法可以接收整型数组，和要查询的元素值；最终要返回元素在该数值中的索引，如果数组中不存在该元素则返回-1。

分析：

1） 定义方法，接收整形数组，查询的元素值，在方法体中完成元素查询的功能。==是否需要参数、返回值类型？需要、需要。==

2） 定义数组，调用该方法，并指定要搜索的元素值，得到返回的结果输出。

 

==③  比较两个数组内容是否一样（简单版）==

如果两个数组的类型，元素个数，元素顺序的内容是一样的我们就认为这两个数组是一模一样的。使用方法完成：能够判断任意两个整型数组是否一样，并返回true或者false。

分析：

1） 定义方法，接收两个整型数组；是否需要参数、返回值类型？需要，需要（boolean）。

2） 在方法内部完成判断的逻辑，并返回布尔结果。

 

 

7、 方法重载

①  方法重载的形式、作用

==同一个类==中，出现==多个方法名称相同，==但是==形参列表是不同的==，那么这些方法就是重载方法。

![](../../typora/Photo File/photo202403271828762.png)

这种==不会发生误调用==的情况：因为在调用方法的时候，会==通过参数的不同来区分调用的是哪个方法。==

 

方法重载的作用：

可读性好，方法名称相同提示是同一类型的功能，==通过形参不同实现功能差异化的选择，==这是一种专业的代码设计。

 

==②  方法重载的识别技巧==

只要是==同一个类中，方法名称相同、形参列表不同==，那么他们就是重载的方法，其他都不管！（如：修饰符，返回值类型都无所谓！）

形参列别不同指的是：形参的==个数、类型、顺序==不同，不关心形参的名称。

 

 

8、 单独使用return关键字

return；--->  可以立即==跳出并结束当前**$\color{blue}{方法}$**的执行==；return关键字单独使用可以放在任何方法中。

break；跳出并结束当前所在循环的执行。

continue；结束当前所在循环的当初，继续进行下一次循环执行。





# 02 编程思维课

### 一、   编程思维训练

目的：复习前半段课程学习的Java编程知识，能够使用所学的知识解决问题，提升同学们的编程能力。

​    使用所学的Java技术解决问题的思维方式和编写代码实现出来的能力。

建议：

①  编程思维和编程能力不是一朝一夕形成的，需要时间的沉淀和大量练习。

②  具体措施：勤于联系代码，勤于思考，熟能生巧。

③  前期：先模仿，后期：再创新。

### 二、   案例一：买飞机票

需求：

①  机票价格按照淡季旺季、头等舱和经济舱收费、输入机票原价、月份和头等舱或经济舱。

②  按照如下规则计算机票价格：旺季（5-10月）头等舱9折，经济舱8.5折，淡季（11月到来年4月）头等舱7折，经济舱6.54折。

分析：

①  键盘录入机票原价、月份和机舱类型。

②  使用if判断月份是旺季还是淡季，使用switch分支判断是头等舱还是经济舱。

③  选择对应的折扣进行计算并返回计算的结果

E:\IDEA\IDEAcode\Javase\Javase\practic-app\src\Case\Test1

 

### 三、   案例二：找素数

需求：判断101-200之间有多少个素数，并输出所有素数。（除了1和它本身之外，不能被其他正整数整除）！



分析：

①  101-200之间的数据可以采用循环一次拿到；每拿到一个数，判断该数是否是素数。

②  判断规则是：从2开始遍历到该数的一半数据，看是否有数据可以整除它，有则不是素数，没有则是素数。

```
public static void main(String[] args){
    //1、定义一个循环，找到101-200之间的全部数据
    for (int i = 101; i <= 200; i++){

        //信号位：标记
        boolean flag = true;  //一开始认为当前数据是素数。

        //2、判断当前遍历的这个数据是否是素数
        for (int j = 2;j < i / 2 ;j++ ){
            if(i % j == 0){
                flag = false;
                break;
            }
        }
        //3、根据判定的结果选择是否输出这个数据，是素数就输出
        if(flag){
            System.out.print(i + "\t");
        }
    }
}
```

 

### 四、   案例三：开发验证码

需求：定义方法实现随机产生一个5位的验证码，每位可能是数字、大写字母、小写字母。（类型随机，字符随机）（A-Z：65-90）（a-z：97-122）



分析：

①  定义一个方法，生成验证码返回：方法参数是位数、方法的返回值类型是String。

②  在方法内部使用for循环生成指定位数的随机字符，并连接起来。

③  把连接好的随机字符作为一组验证码进行返回。

##### ==这里有一个重点：==

​    String code = “” ;  定义一个字符串变量记录生成的随机字符

​    那么此时如果有 code += ch；  ch为生成的字符或数子

​    但是由于code为String类型，因为他们不是相加，而是combine（组合）。

 

### 五、   案例四：数组元素的复制

需求：把一个数组的元素复制到另一个新的数组中去。

分析：

①  需要动态初始化一个数组，长度与原数组一样。

②  遍历原数组的每个元素，依次赋值给新数组。

③  输出两个数组的内容。

 

### 六、   案例五：评委打分

需求：在唱歌比赛中，有6名评委给选手打分，分数范围是[0-100]之间的整数。选手的最后得分为：去掉最高分、最低分后的4个评委的平均分，请完成上述过程并计算出选手的得分。

分析：

①  把6个评委的分数录入到程序中去à使用数组。

②  遍历数组中每个数据，进行累加求和，并找出最高分、最低分。

③  按照分数的计算规则算出平均分。

 

### 七、   案例六：数字加密

需求：某系统的数字密码，比如1983，采用加密方式进行传输，规则如下：先得到每位数，然后每位数都加上5，再对10求余，最后将所有数字反转，得到一串新数。

分析：

①  将每位数据存入到数组中去，遍历数组每位数据按照规则进行更改，把更改后的数据重新存入到数组中。

②  将数组的前后元素进行交换，数组中的最终元素就是加密后的结果。



### 八、   案例七：模拟双色球

投注号码由6个红色球号码和一个蓝色球号码组成。红色球号码从1-33中选择；蓝色球号码从1-16中选择。

​    可以创建三个方法：随机生成一组中奖号码方法==（6个红球要求不能重复）==，用户输入一组号码，对比用户号码和中奖号码，看用户是否中奖。

1、 本次案例中是如何去统计红球的命中数量的？

①  遍历用户的每个选好，然后遍历中奖号码组。

②  看当前选好是否在中奖号码中存在，存在则命中数量+1

```
//1、定义2个变量分别存储红球命中个数，以及篮球命中个数。
int redHitNumbers = 0;
int blueHitNumbers = 0;

for (int i = 0; i < luckNumbers.length - 1; i++) {
    for (int j = 0; j < userNumebrs.length; j++) {
        if(luckNumbers[i] == userNumebrs[j]){
            redHitNumbers++;
            break;
        }
    }
}
if(userNumebrs[userNumebrs.length -1] == luckNumbers[luckNumbers.length - 1]){
    blueHitNumbers ++;
}

```

 

 

==重点：定义一个标记为flag，用来执行是否将随机生成的数字存如数组中==

```
//定义一个标记为 flag,默认值位data没有出现过
boolean flag = true;
for (int j = 0; j < i; j++) {
    if(numbers[j] == data){
        //data数值重复，不能使用
        flag = false;
        break;
    }
}
if(flag){
    //data这个数据之前没有使用过，可以装入numbers数组中
    numbers[i] = data;
    break;
}

```

 

例如这里的 flag；就是判断如果随机生成的数字与数组中有重复，则执行if语句，将flag设为flase，此时不会执行第二个if语句；当flag为true时，则执行第二个if语句，将当前生成的随机数存入到数组中。

 

# 03 面向对象基础

### 一、面向对象概述

啥是面向对象编程？

- 面向就是拿或找的意思。
- 对象就是东西的意思。
- 面向对象编程就是拿或找东西过来编程。

学习重点：

- 学习Java提供的对象并使用

- 学习如何自己设计对象并使用（课程重点）

- 面向对象的语法知识（课程重点）

### 二、设计对象并使用

1、设计类，创建对象并使用

​		==在Java中，必须先设计类，才能获得对象。==      

​		$\color{red}{类（设计图）}$：是对象共同特征的描述；         $\color{red}{对象}$：是真实存在的具体实例。

![](../../typora/Photo File/photo202403271829157.png)

拿到对象后怎么使用？

- 对象.成员变量；

- 对象.成员方法（...）；

```
    public static void main(String[] args){
        //目标：自己设计对象并使用
        //类名  对象名  =  new  类名（）；
        Car c = new Car();
        c.name = "奔驰GLC";
        c.price = 39.78;
        System.out.println(c.name);
        System.out.println(c.price);
        c.start();
        c.run();
        }
```



2、定义类的几个补充注意事项

- 成员变量的完整定义格式是： ==修饰符   数据类型  变量名称  = 初始化值；==一般无需指定初始化值，存在默认值。
- 类名首字母建议大写，且有意义，满足“驼峰模式”。
- 一个Java文件中可以定义多个class类，且只能一个类是public修饰，==而且public修饰的类名必须成为代码文件名。==**==实际开发中建议还是一个文件定义一个class类。==**

​		如下所示：

​		

```
package createObject;

public class Student {    //整个java文件中只有一个类是由public修饰的    其他的不可以再使用public
    // 修饰符 数据类型 变量名称 = 初始值；
    String name;
    int ages;
}
class animal{    //如果在这里再使用public来修饰  则会发生错误

}

class tree{
    
}
```



### 三、对象内存图

1、多个对象的内存图

![](../../typora/Photo File/photo202403271735681.png)

对象放在==堆内存中。==

Car c = new Car（）；c变量名中存储的是什么？  ==存储的是对象在堆内存中的地址。==

成员变量（name、price）的数据放在哪里？存在于哪个位置？

==数据放在对象中，存在于堆内存中。==



2、两个变量指向同一个对象内存图

![](../../typora/Photo File/photo202403271740547.png)

==垃圾回收==

注意：当堆内存中的==类对象或数组对象，没有被任何变量引用（指向）时==，就会被判断为内存中的**”垃圾“**。

==Java存在自动垃圾回收期，会定期进行清理。==



### 四、面向对象编程训练：模拟购物车模块

1、需求分析、架构搭建

​	需求：模拟购物车模块的功能，需要实现添加商品到购物车中去，同时需要提供修改商品的购买数量，结算商品价格功能（请使用面向对象编程来解决）。

​	分析：

​				购物车中的每个商品都是一个对象，需要定义一个商品类。

​				购物车本身也是一个对象：可以使用数组对象代表它。

​				完成界面架构，让用户选择操作的功能



2、添加商品到购物车、查看购物车信息

​	需求：让用户输入商品信息，并加入到购物车中去，且可立即查看购物车信息。

​	分析：

​				需要让用户录入商品信息，创建商品对象封装商品信息。

​				并把商品对象加入到购物车数组中去。

​				查询购物车信息，就是遍历购物车数组中的每个商品对象。

①如何完成的添加商品功能？

- 创建Goods类的对象代表商品对象，封装用户输入的商品信息。
- 把商品对象存入到表示购物车的数组中去。此数组中存放的是商品对象的地址

②如何查看购物车信息？

- 遍历表示购物车的数组，每遍历到一个商品对象输出其信息展示。



3、修改购买数量

需求：让用户输入商品id，找出对应的商品修改其购买数量

分析：

​			定义方法能够根据用户输入的id去购物车数组中查看是否存在该商品对象。

​			存在返回该商品对象的地址，不存在返回null。

​			判断返回的对象地址是否存在，存在修改其购买数量，不存在就继续。



4、结算金额

需求：当用户输入了pay命令后，需要展示全部购买的商品信息和总金额。

分析：

​			定义求和变量，遍历购物车数组中的全部商品，累加其单价*购买数量



### 五、构造器

1、构造器的作用

​		用于初始化一个类的对象，并返回对象的地址。   Car  c  =  new  ==Car（）==；

​																							类型 变量名称 = new 构造器；

2、构造器的定义格式

​		修饰符  类名（形参列表）{

​				......	

​		}

==注意：这里的无参数/有参数构造器的名称与类名一样==

```
public class Car{
	...
	//无参数构造器（需要写出来）
	public Car(){
		...
	}
	//有参数构造器
	public Car(String n, String b){
		...
	}
}
```

无参数构造器==（默认存在的，写不写都有）==：初始化的对象时，成员变量的数据均采用默认值。

有参数构造器：在初始化对象的时候，同时可以为对象进行赋值。

==注意：一旦定义了有参数构造器，无参数构造器就没有了，此时就需要自己写一个无参数构造器了。==





### 六、this关键字

作用：出现在成员方法、构造器中==代表当前对象的地址==，用于访问==当前对象==的成员变量、成员方法。

![](../../typora/Photo File/photo202403271830590.png)

![](../../typora/Photo File/photo202403271830527.png)

![](../../typora/Photo File/photo202403271831074.png)





### ==七、封装（重点）==

面向对象的三大特征：**$\color{red}{封装、继承、多态。}$**

什么是封装？隐藏实现细节，暴露出合适的访问方式。==（合理隐藏、合理暴露）==

![](../../typora/Photo File/photo202403271831529.png)

可以发现如果没有讲Student进行封装，那么我们就可以随意访问age并且给其赋值，而在这里这个 -23的赋值是错误的。

1、封装的实现步骤：

- 一般对成员变量使用==**private**（私有）关键字==修饰进行隐藏，private修饰后该成员变量就只能在当前类中访问。

  ![](../../typora/Photo File/photo202403271831388.png)

- ==提供public修饰的公开的**getter、setter**方法暴露其取值和赋值。==（可以用此来设置一个对象来判断取值、赋值是否满足要求，对其进行一定的限制条件）

  注意：由于getter和setter是公认的封装的规范，全球统一的，因此系统会提供给我们一个工具自动生成这些getter和setter；   

  ==在空白处 **右键选择Generate/生成**   - -> **选择Getter and setter**  - ->  ***按住shift选择自己想要为那个变量生成Getter and Setter**==

  ![](../../typora/Photo File/photo202403271831487.png)



2、封装的好处

- 加强了程序代码的安全性。
- 适当的封装可以提升开发效率，同时可以让程序更容易理解与维护。



### 八、标准JavaBean

JavaBean也可以理解成实体类，其对象可以用于在程序中封装数据。

标准JavaBean必须满足如下要求：

- 成员变量使用==**private**==修饰。
- 提供每一个成员变量对应的==**setXxx() / getXxx()**==。
- ==必须==提供一个==无参数构造器==。（有参可有可无）



### 九、使用标准JavaBean改造购物车案例

将不规范的面向对象编程，改造为规范的面向对象编程；使用private来对各个变量进行封装；同时增加构造器和getter和setter。

![](../../typora/Photo File/photo202403271831112.png)





### 十、补充知识：成员变量、局部变量区别

![](../../typora/Photo File/photo202403271832235.png)





# 04 常用API

API：应用程序编程接口；是一些预先定义的函数，目的是提供应用程序与开发人员基于某软件或硬件的以访问一组例程的能力，而又无需访问源码，或理解内部工作机制的细节。

例如System.out.println();打印函数，就是Java自己实现的方法，你只管调用就可以。

- Java写好的技术（功能代码），咱们可以直接调用
- Oracle也为Java提供的这些功能代码提供了相应的API文档（技术使用说明书）

### 一、String

1、String类概述、简单介绍

==String类==定义的变量可以用于存储字符串，同时String类提供了很多==操作字符串的功能==，我们可以直接使用。（例如：跟正确的用户名和密码进行比较。）

- java.lang.String类代表字符串，String类定义的变量可以==用于指向字符串对象==，然后操作该字符串。
- Java程序中的所有字符串文字（例如“abc”）都为此类的对象。

String类的特点详解

- ==String其实常被称为不可变字符串类型，它的对象在创建后不能被更改。==

  ```
  //但是这里有一个疑问，请看下面
  public static void main(String[] args){
  	String name = "杨克";
  	name += "是";
  	name += "懒虫";
  	System.out.println(name); // 输出：杨克是懒虫  很明显最初定义的name对象发生了改变
  }
  ```

  那我们怎么去理解上面所说的那句话呢？请继续看下面

  ![](../../typora/Photo File/photo202403271832408.png)

可以看到，String所创建的每个对象都是没有改变的，都放在==字符串常量池==中；而我们一步步的改变name值的原因，其实是将String name指向运算后的地方。

- ==String变量每次的修改其实都是产生并指向了新的字符串对象==。
- ==原来的字符串对象都是没有改变的，所以称为不可变字符串。==



2、String类创建对象的2种方式

- 方式一：直接使用==“ ”==定义。$\color{red}{（推荐方式）}$

- 方式二：通过String类的构造器创建对象。

  ![](../../typora/Photo File/photo202403271832638.png)



###### ==重点：有什么区别吗？（面试常考）==

- 以 “ ” 方式给出的字符串对象，在字符串常量池中存储，而且==相同内容只会在其中存储一份。==

- 通过构造器new对象，==每new一个都会产生一个新对象，放在堆内存中==。

  ==(比较的是 s1 和 s2 的地址；因为ss1和ss2本身存储的就是"abc"的地址；只是由于特殊原因导致输出s1/2时直接输出abc，而不是地址！)==

```
String s1 = "abc";
String s2 = "abc";
System.out.println(s1 == s2);   //true

char[] chs = {'a', 'b', 'c'};
String s3 = new String(chs);
String s4 = new String(chs);
System.out.println(s3 == s4);   //false
```

Java中有两种比较对象的方法：====运算符和equals方法。==

==运算符用于$\color{red}{比较两个对象的引用}$，如果它们指向的是同一个对象，则返回true；

而equals方法用于==比较两个对象的内容是否相等==，当它们的内容相等时，则返回true。

（使用方式：a.equals(b);    对比 a 和 b 指向的内容是否一致！）

因此，equals方法可以用于比较两个值相同的字符串、整型等基本数据类型，或需要通过内容比较才能确定相等的自定义类对象等。

![](../../typora/Photo File/photo202403271832070.png)

![](../../typora/Photo File/photo202403271832698.png)





###### ==3、String类常见面试题==

①、问题：下列代码的运行结果是？

```
public class Test1{
	public static void main(String[] args){
		
		//这句代码实际上创建了两个对象；一个在堆内存中的字符串变量中，一个在堆内存中
		String s2 = new String("abc"); 
		
		String s1 = "abc";   //这行代码创建了0 个对象；因为abc已经在常量池中
		System.out.println(s1 == s2);   //false

	}
}
```

![](../../typora/Photo File/photo202403271833700.png)



②、问题：下列代码的运行结果是？

```
public class Test2{
	public static void main(String[] args){
	
		String s1 = "abc";   //abc在字符串常量池中
		String s2 = "ab";	 //ab在字符串常量池中
		String s3 = s2 + "c";   //创建两个对象：一个是c在字符串常量池中；一个是运算后的abc，在堆内存中，不在字符串常量池中
		System.out.println(s1 == s3);   //false
	
	}
	
}
```

可以参考下图来理解此问题！

![](../../typora/Photo File/photo202403271832408.png)



③、问题：下列代码的运行结果是？

==Java存在编译优化机制，程序在编译时："a" + "b" + "c" 会直接转成"abc"==

因为"a" + "b" + "c" 是字面量/值。

```
public class Test3{
	public static void main(String[] args){
	
		//创建一个对象abc，在字符串常量池中
		String s1 = "abc";  
		
		//Java存在编译优化机制，程序在编译时："a" + "b" + "c" 会直接转成"abc"
		String s2 = "a" + "b" + "c";
		
		System.out.println(s1 == s2);  //true
	
	}
}
```





4、String类常用Api—==字符串内容比较==

Java中有两种比较对象的方法：====运算符和equals方法。==

==运算符用于$\color{red}{比较两个对象的引用}$，如果它们指向的是同一个对象，则返回true；即比较对象地址

而equals方法用于==比较两个对象的内容是否相等==，当它们的内容相等时，则返回true。

（使用方式：a.equals(b);    对比 a 和 b 所指向的内容是否一致！）

因此，equals方法可以用于比较两个值相同的字符串、整型等基本数据类型，或需要通过内容比较才能确定相等的自定义类对象等。

**结论：字符串的内容比较不适合用”==“比较！**

字符串的内容比较：

- 推荐使用String类提供的”equals“比较：只关心内容一样即可！

  ![](../../typora/Photo File/photo202403271834894.png)

使用方法

```
String a = "abc";  //创建一个对象，在字符串常量池中保存abc
String b = new String("abc");   //创建一个对象，因为abc已经在常量池中；因此只需要在堆内存中创建一个对象，保存abc

System.out.println(a.equals(b));  // ture


//equalsIgnoreCase
String sysCode = "23AdFh";
String code = "23aDfH";
System.out.println(sysCode.equalsIgnoreCase(code));   //ture

```



5、String类常用API—遍历、替换、截取、分割操作

![](../../typora/Photo File/photo202403271834223.png)

```
package string;

/**
 * 目标：掌握String常用的其他API
 */

public class StringAPIOtherDemo5 {
    public static void main(String[] args){
        //1、public int length():  获取字符串的长度
        String name = "我爱你中国！";
        System.out.println(name.length());



        //2、public char charAt(int index): 获取某个索引位置处的字符
        System.out.println(name.charAt(1));    //将字符串name中的索引1的爱字提取出来

        System.out.println("----------------遍历字符串中的每个字符------------------");
        for (int i = 0; i < name.length(); i++) {
            char ch = name.charAt(i);
            System.out.print(ch + "\t");
        }
        System.out.println();


        //3、public char[] toCharArray(): 把字符串转换成字符数组
        char[] chars = name.toCharArray();
        for (int i = 0; i < chars.length; i++) {
            char ch = chars[i];
            System.out.print(ch + "\t");
        }
        System.out.println();


        //4、public String substring(int beginIndex, int endIndex): 截取内容(包前不包后的)
        String name2 = "Java是最厉害的编程语言！";
        String rs = name2.substring(0,9);
        System.out.println(rs);

        //5、public String substring(int beginIndex)：从当前索引一直截取到末尾
        String rs1 = name2.substring(4);
        System.out.println(rs1);


        //6、public String replace(CharSequence target, CharSequence replacement)
        String name3 = "cnm！你个大傻子，该死了！";
        String rs2 = name3.replace("cnm","***");
        String rs3 = rs2.replace("死","*");
        System.out.println(rs2);
        System.out.println(rs3);


        //7、public boolean contains(CharSequence s)：判断是否包含关键字
        boolean bl = name3.contains("cnm");
        System.out.println(bl);
        boolean bl1 = name3.contains("杨克");
        System.out.println(bl1);
        System.out.println("-----------------------------");

        //8、public boolean startsWiths(String prefix)：判断是否以（）中的字符开始
        System.out.println(name3.startsWith("大傻子"));
        System.out.println(name3.startsWith("cnm"));
        System.out.println(name3.startsWith("cnm/"));


        //9、public String[] split(String s): 按照某个内容把字符串分割成字符串数组返回
        String name4 = "杨克、王博宇、周知、赵旭、姜淼" ;
        String[] names = name4.split("、");
        for (int i = 0; i < names.length; i++) {
            System.out.print(names[i] + " ");
        }


    }
}

```



6、String类案例实战

==①、String类开发验证码功能==

​	需求：随机产生一个5位的验证码，每位可能是数字、大写字母、小写字母。

分析：

- 定义一个String类型的变量存储验证码a-z，A-Z，0-9之间的全部字符
- 循环五次，随机一个范围内的索引，获取对象字符连接起来即可。

```
package string;
/*
    练习题：使用String完成随机生成5位的验证码。
 */

import java.util.Random;

public class StringExec {
    public static void main(String[] args){
        //1、定义一个字符，用于存储a-z，A-Z，0-9之间的全部字符
        String datas = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789";  //62个

        //定义一个字符串，用于存储验证码
        String codes = "" ;

        //随机生成数
        Random random = new Random();

        //初始化一个变量，用于控制while的循环次数；即验证码的个数
        int i = 0;
        while(i < 5){
            //获取一个0-62之间的随机数
            int number = random.nextInt(datas.length());
            //使用StringAPI来得到索引处的字符！使用charAt（）；
            char data = datas.charAt(number);
            codes += data;
            i++;
        }

        System.out.println(codes);

    }
}
```

==②、模拟用户登录功能==

需求：模拟用户登录功能，最多给三次机会。

分析：

- 系统后台定义好正确的登录名称、密码。
- 使用循环控制三次，让用户输入正确的登录名和密码，判断是否登陆成功，登陆成功则不再进行登录；登陆失败给出提示，并让用户继续登录。

```
package string;
/*
     练习题：模拟用户登录
 */

import java.util.Scanner;

public class StringExec2 {
    public static void main(String[] args){
        //定义出正确的用户名和密码
        String okName = "donglin";
        String okPassword = "123456";

        //创建一个扫描仪器，用来接收用户输入的信息
        Scanner scanner = new Scanner(System.in);

        OUT:
        for (int j = 0; j < 1; j++) {
            for (int i = 0; i < 3; i++) {
                System.out.println("请输入您的用户名：");
                String name = scanner.next();
                System.out.println("请输入您的密码：");
                String password = scanner.next();
                //判断登录名是否正确
                if(okName.equals(name)){
                    //判断密码是否正确
                    if(okPassword.equals(password)){
                        System.out.println("登陆成功！");
                        break OUT;
                    }else{
                        System.out.println("密码错误！");
                    }
                }else{
                    System.out.println("登录名错误！");
                }

                System.out.println("请注意：您已经错误" + (i + 1) + "次！您还剩余"+ (3 - (i + 1))+ "次机会！" + "\n");
            }
            System.out.println("对不起！您的三次机会已使用完！");
        }
    }
}
```

==③、手机号码屏蔽==

需求：以字符串的形式从键盘接收一个手机号，将中间四位号码屏蔽，最总结果为：132****4565

分析：

- 键盘录入一个字符串，用Scanner实现。
- 截取字符串前三位，截取字符串后四位。
- 将截取后的两个字符串，中间加上****进行拼接，输出结果即可。

```
package string;
/*
     联系题：手机号码屏蔽
 */

import java.util.Scanner;

public class StringExec3 {
    public static void main(String[] args){
        Scanner scanner = new Scanner(System.in);
        System.out.println("请输入一个手机号：");
        String tel = scanner.next();

        String before = tel.substring(0,3);
        String after = tel.substring(7);  //截取7到末尾的手机号

        String shield = before + "****" + after;
        System.out.println(shield);

    }
}
```



### 二、ArrayList

##### ==集合中存放的是对象地址！！！==

1、集合概述

- ArrayList代表的是集合类，集合是一种容器，与数组类似，不同的是==集合的大小是不固定的==。

- 通过创建ArrayList的对象表示得到一个集合容器，同时ArrayList提供了比数组更好用，更丰富的API（功能）给程序员使用。

集合特点：

- 集合的大小不固定，启动后可以动态变化，==类型也可以选择不固定==。
- ==集合非常适合做元素个数不确定，且要进行增删操作的业务场景。==
- 集合提供了许多丰富、好用的功能，而数组的功能很单一。






2、ArrayList集合快速入门

ArrayList是集合中的一种，它支持索引。

![](../../typora/Photo File/photo202403271835035.png)

```
        //1、创建ArrayList集合的对象
        ArrayList list = new ArrayList();

        //2、添加数据
        list.add("Java");
        list.add("Java");
        
        //3、给指定索引位置插入元素
        list.add(1,88);     // list=[Java，88，Java]
```





3、ArrayList对泛型的支持（规范）

- ==ArrayList<E>==：其实就是一个泛型类，可以在编译阶段约束集合对象只能操作某种数据类型。

举例：

- ArrayList<==String==>：此集合==只能操作字符串类型的元素==。
- ArrayList<==Integer==>：此集合==只能操作整数类型的元素==。

==注意：集合中只能存储引用类型，不支持基本数据类型。==  也就是和上面似的，不可以用Int，要用Integer。   当然：也可以在<>中填入类，Eg：Array List<==Student==>

```
    public static void main(String[] args){
        //1、创建ArrayList集合的对象
        ArrayList list = new ArrayList();
        list.add("Java");
        list.add("MySql");
        list.add(66);
        list.add(88);

        //只允许字符串类型存入集合list1
//      ArrayList<String> list1 = new ArrayList<String>();
        ArrayList<String> list1 = new ArrayList<>();    //泛型后面的类型申明可以不写
        list1.add(88);    //报错，因为88为整数型，无法存入
        list1.add("Java");
        list1.add("东林");


    }
```



4、ArrayList常用API、遍历

![](../../typora/Photo File/photo202403271835027.png)

```
     public static void main(String[] args){
        ArrayList<String> list = new ArrayList<>();
        list.add("Java");
        list.add("Java");
        list.add("MySql");
        list.add("MyBatis");
        list.add("HTML");
        //1、public E get(int index)  获取某个索引位置处的元素值
        System.out.println(list.get(2));

        //2、public in size(): 获取集合的大小（元素个数）
        System.out.println(list.size());

        //3、完成集合的遍历
        for (int i = 0; i < list.size(); i++) {
            System.out.print(list.get(i) + "\t");
        }
        System.out.println();

        //4、public E remove(int index)：删除某个索引位置处的元素值，并返回被删除的元素值
        String delete = list.remove(4);
        System.out.println(delete);
        System.out.println(list);

        //5、public boolean remove(Object o)：直接删除元素值，删除成功返回true，删除失败返回false
        boolean bl = list.remove("MySql");
        System.out.println(bl);
        System.out.println(list);

        //注意：当删除某一个值时，而集合中有多个该值，remove会默认删除第一个出现的值/前面的值
        ArrayList<String> list1 = new ArrayList<>();
        list1.add("Java");
        list1.add("杨克");
        list1.add("Java");
        list1.remove("Java");
        System.out.println(list1);

        //6、public E set(int index, E element)：修改某个索引位置处的元素值，并返回原来值。
        String e3 = list.set(1,"SpringBoot");     
        System.out.println(e3);    //输出Java
        System.out.println(list);

    }
```

==注意：当使用remove删除某一个值时，而集合中有多个该值；remove会默认删除第一个出现的值/前面的值。==



5、ArrayList集合案例：遍历并删除元素

需求：

- 某个班级的考试在系统上进行，成绩大致为：98， 77， 66， 89， 79， 50， 100
- 现在需要先把成绩低于80分以下的数据去掉。

分析：

- 定义ArrayList集合存储多名学员的成绩。
- 遍历集合每个元素，如果元素值低于80分，去掉它。

```
    public static void main(String[] args){
        //1、定义一个集合用于存储成绩
        ArrayList<Integer> list = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);

        //用于表示第几个学生的成绩
        int i = 1;
        OUT:
        while(true){
            System.out.println("请您输入第"+ i + "个学生的成绩！结束请输入-1！");
            int grade = scanner.nextInt();
            if(grade == -1){
                System.out.println("录入信息结束！");
                break OUT;
            }else if( grade <= 100 && grade >= 0){
                list.add(grade);
                System.out.println( grade + "录入成功！");
                i++;
            }else{
                System.out.println("对不起，您输入的信息有误！");
            }
        }

        //重点在于如何动态的删除

//        //对于动态集合，边遍历边删除元素，会出现bug
//        for (int j = 0; j < list.size(); j++) {
//            int score = list.get(i);
//            //2、判断分数是否低于80分，如果低于则从集合中删除它
//            if(score < 80){
//                list.remove(i);
//            }
//        }

        //可以尝试从后面开始删除
        for (int j = list.size() - 1; j >= 0 ; j--) {
            int score = list.get(j);
            //2、判断分数是否低于80分，如果低于则从集合中删除它
            if(score < 80){
                list.remove(j);
                System.out.println(score + "已被删除！");
            }
        }

        System.out.println(list);

    }
```

###### ==集合遍历并删除的注意事项：==

这里如果不注意会有一个bug。当我们从前往后，边遍历边删除动态集合元素，就会产生bug，因为在删除后，集合的长度也发生了变化，而 i 是一直递进增加的，这样会出现漏删元素的情况发生。

因此在后面的代码中，使用了==从后面往前面删除的方法，这样就可以克服上面所说的bug，避免漏掉元素。==





###### ==6、ArrayList集合案例：存储自定义类型的对象(重点)==

==集合中存放的是对象地址，而不是对象本身！==

需求：某影院系统需要在后台存储上述三部电影，然后依次展示出来。

分析：

- 三部电影是3个对象，定义一个电影类，定义一个集合存储电影对象。
- 创建3个电影对象，封装相关数据，把3个对象存入到集合中去。

```
    public static void main(String[] args){
        //1、定义一个电影类：Movie
        //2、定义一个ArrayList集合存储这些影片对象
        ArrayList<Movie> movies= new ArrayList<>();

        //3、创建影片对象封装电影数据，把对象加入到集合中去。
//        Movie m1 = new Movie("《肖申克的救赎》", 9.7 ,"罗宾斯");
//        movies.add(m1);

        movies.add(new Movie("《肖申克的救赎》", 9.7 ,"罗宾斯"));
        movies.add(new Movie("《霸王别姬》", 9.6 ,"张国荣，张丰毅"));
        movies.add(new Movie("《阿甘正传》", 9.5 ,"汤姆.汉克斯"));
        //集合里面装的是对象的地址
        System.out.println(movies);
        System.out.println("-----------------------------------------------");

        //4、遍历集合中的影片对象并展示出来
        for (int i = 0; i < movies.size(); i++) {
            Movie movie = movies.get(i);
            System.out.println("片名：" + movie.getName());
            System.out.println("评分：" + movie.getScore());
            System.out.println("主演：" + movie.getActor());
            System.out.println();
        }

    }
```



7、ArrayList集合案例：元素搜索

需求：后台程序需要存储如上学生信息并展示，然后要提供按照学号搜索学生信息的功能。

分析：

- 定义Student类，定义ArrayList集合存储如上学生对象信息，并遍历展示出来。(重点)
- 提供一个方法，可以接收ArrayList集合，和要搜索的学号，返回搜索到的学生对象信息，并展示
- 使用死循环，让用户可以不停的搜索。

```
package arraylist;

import java.util.ArrayList;
import java.util.Scanner;

/**
 * 案例：学生信息系统的数据搜索
 * 需求：后台程序需要存储如上学生信息并展示，然后要提供按照学号搜索学生信息的功能。
 */

public class ArrayListExec3 {
    public static void main(String[] ars){
        //1、定义一个学生信息类：Student
        //2、定义一个ArrayList集合存储这些学生对象
        ArrayList<Student> students = new ArrayList<>();

        //3、创建学生对象封装学生信息数据，把对象加入到集合中去。
        students.add(new Student(20180302,"叶孤城",23,"护理一班"));
        students.add(new Student(20180303,"东风不败",23,"推拿二班"));
        students.add(new Student(20180304,"西门吹牛",26,"中药学四班"));
        students.add(new Student(20180305,"梅超风",26,"神经科2班"));
        //要时刻记住：集合中装的是对象的地址
        System.out.println(students);
        System.out.println("--------------------------------------");

        //遍历集合中的每个学生对象并展示其数据
        for (int i = 0; i < students.size(); i++) {
            Student student1= students.get(i);
            System.out.println(student1.getId());
            System.out.println(student1.getName());
            System.out.println(student1.getAge());
            System.out.println(student1.getGrade());
            System.out.println();
        }


        //4、让用户不断地输入学号，可以搜索出该学生对象信息并展示出来（独立成方法）
        Scanner scanner = new Scanner(System.in);
        while (true) {
            System.out.println("请您输入要查询的学生的学号：");
            int id = scanner.nextInt();
            Student s = getStudentById(students, id);
            //判断学号是否存在
            if(s == null){
                System.out.println("查无此人！");
            }else{
                //找到了该学生对象了，信息如下
                System.out.println(s.getId());
                System.out.println(s.getName());
                System.out.println(s.getAge());
                System.out.println(s.getGrade());
                System.out.println();
            }
        }

    }

    /**
     * 根据学号去集合中找到学生对象并返回。
     * @param student
     * @param id
     * @return
     */

    public static Student getStudentById(ArrayList<Student> student,int id){
        for (int i = 0; i < student.size(); i++) {
            Student s = student.get(i);
            if(s.getId() == id){  //这里可以不用equals()来进行对比，因为我们使用的id是int型的，不是字符串类型
                return s;
            }
        }
        return null; //查无此学号！
    }

}

```



Student类

```
package arraylist;

public class Student {
    private int id;
    private String name;
    private int age;
    private String grade;

    //创建一个有参构造器
    public Student(){

    }


    //创建一个有参构造器
    public Student(int id, String name, int age, String grade){
        this.id = id;
        this.name = name;
        this.age = age;
        this.grade = grade;
    }

    //创建对于私有对象的set和get方法
    public int getId(){
        return id;
    }
    public void setId(int id){
        this.id = id;
    }

    public String getName(){
        return name;
    }
    public void setName(String name){
        this.name = name;
    }

    public int getAge(){
        return age;
    }
    public void setAge(int age){
        this.age = age;
    }

    public String getGrade(){
        return grade;
    }
    public void setGrade(){
        this.grade = grade;
    }
}

```





# 05 ATM项目

![](../../typora/Photo File/photo202403271835607.png)

1、系统准备、首页设计

​	系统准备内容分析：

- 每个用户的账户信息都是一个对象，需要提供账户类。
- 需要准备一个容器，用于存储系统全部账户对象信息。
- 首页只需要包含：登录和注册2个功能。

​	实现步骤：

- 定义账户类，用于后期创建账户对象封装用户的账户信息。

- 账户类中的信息至少需要包含（卡号、姓名、密码、余额、取现额度）

- 需要准备一个ArrayList的集合，用于存储系统用户的账户信息。

- 需要展示换用页包含2个功能：开户功能、登陆账户。

  ![](../../typora/Photo File/photo202403271858371.png)



2、用户开户功能实现

分析：开户功能其实就是往系统的集合容器中存入一个新的账户对象的信息。

开户功能实现步骤：

- 定义方法完成开户：

  ```
  public static void register(ArrayList<Account> accounts){...}
  ```

- 键盘录入姓名、密码、确认密码（需保证两次密码一致）

- 生成账户卡号，卡号必须由系统自动生成8为数字（必须保证卡号的唯一）

- 创建Account账户类对象用于封装账户信息（姓名、密码、卡号）

- 把Account账户类对象存入到集合accounts中去。

![](../../typora/Photo File/photo202403271859983.png)



3、用户登陆功能实现

分析：

- 定义方法：

  ```
  public static void login(ArrayList<Account> accounts){...}
  ```

- 让用户键盘录入卡号，根据卡号查询账户对象。

- 如果没有找到账户对象，说明卡号不存在，提示继续输入卡号。

- 如果找到了账户对象，说明卡号存在，继续输入密码。

- 如果密码不正确，提示继续输入密码

- 如果密码正确，提示登陆成功！

![](../../typora/Photo File/photo202403271859786.png)



4、用户操作页设计、查询账户、推出账户功能实现

分析：

- 用户登录成功后，需要进入用户操作页。

- 查询就是直接展示当前登录成功的账户对象的信息。

- 推出账户是需要回到首页的。

  ![](../../typora/Photo File/photo202403271859172.png)



5、用户存款功能实现

分析：

- 存款就是拿到当前账户对象。

- 然后让用户输入存款的金额。

- 调用账户对象的setMoney方法将账户余额修改成存钱后的余额。

- 存钱后需要查询一下账户信息，确认是否存钱成功了！

  ![](../../typora/Photo File/photo202403271900654.png)



6、用户取款功能实现

分析：

- 取款需要先判断账户是否有钱。

- 有钱则拿到自己账户对象。

- 然后让用户输入取款金额。

- 判断取款金额是否超过了当次限额，以及余额是否足够

- 满足要求则调用账户对象的setMoney方法完成金额的修改。

  ![](../../typora/Photo File/photo202403271900540.png)



7、用户转账功能实现

分析：

- 转账功能需要判断系统中是否有2个账户对象及以上。
- 同时还要判断自己账户是否有钱。
- 接下来需要输入对方卡号，判断对方账户是否存在。
- 对方账户存在还需要认证对方户主的姓氏。
- 满足要求则可以把自己账户对象的金额修改到对方账户对象中去。

![3.25捕获7](../typora/Photo File/3.25捕获7.PNG)



8、用户密码修改、销户功能实现

分析：

- 修改密码就是把当前对象的密码属性使用set方法进行更新。

- 销户就是从集合对象中删除当前对象，并回到首页。

  ![](../../typora/Photo File/photo202403271900029.png)



# 06基础加强课

一、IDEA开发模式统一

IDEA项目结构介绍：

- project（项目、工程）

- module（模块）

- package（包）

- class（类）

  ![](../../typora/Photo File/photo202403271901463.png)

==注意！注意！注意！：基础加强阶段依然统一建空工程，再创建模块、采取一天一个模块梳理知识！==





二、面向对象知识快速回顾

1、面向对象思想概述、类、对象

面向对象思想：

- 把现实世界的事物全部看成一个一个的对象来解决问题，代码看起来很像人类的自然语言。
- ==在java中需要先定义类，才能创建对象。==
- ==类是相同事物共同特征的描述（设计图），对象是具体存在的实例。==



定义类的注意事项：

- 类名建议首字母大写。满足驼峰模式。

- ==一个Java文件中可以定义多个类，但是只能有一个类是用public修饰的，public修饰的类名必须成为Java代码的文件名称。==

  ![](../../typora/Photo File/photo202403271902256.png)

- **==按照规范：建议一个Java文件只定义一个类。==**  只要这些类在一个包下面，都可以互相访问！



类中成分：

- 类中可以定义的5大成分：==成员变量、构造器、成员方法、==代码块、内部类。

  ![](../../typora/Photo File/photo202403271902429.png)





2、构造器

==初始化类的对象并返回对象的地址。==

构造器格式：  修饰符  ==类名==（形参列表）{  }

初始化对象格式： ==类名== ==对象变量==  =  new 构造器；

构造器的分类和作用：

- 无参数构造器：初始化对象数据为默认值。
- 有参数构造器：可以在初始化对象的时候同时为对象的数据赋值。





3、this关键字

自己的理解：格式==this.变量==，就是说这个变量是当前java文件中的变量

Eg： this.name = name;   就是把==别的java文件传过来的name值==，赋值给==当前文件的name==。



this关键字：

- 作用：出现在成员方法、构造器中代表当前对象的地址，用于==指定访问当前对象==的成员变量、成员方法。

- **==this出现在构造器，或者方法中，哪个对象调用他们，this就代表哪个对象。==**（大白话：对象就是我们平时定义的，int a；  这里的a就是对象！  String name； 这里的name也是对象！）

  ![](../../typora/Photo File/photo202403271902199.png)

![](../../typora/Photo File/photo202403271903229.png)

![](../../typora/Photo File/photo202403271903712.png)





4、面向对象三大特征之一：封装

面向对象的三大特征：==封装、继承、多态。==

- 封装基本思想：合理隐藏（隐藏细节），合理暴露（提供访问入口）。
- 封装步骤：通常将成员变量私有，提供方法进行暴露。
- 封装作用：提高业务功能设计的安全性，提高组件化。



特征的含义：

- 所谓特征指的是已经成为Java设计代码的基本特点，即使毫无意义，通常也需要满足这样的设计要求来编写程序。





5、标准JavaBean

也可以理解成实体类，其对象可以用于在程序中封装数据。



Java中书写标准JavaBean必须满足如下要求：

- 成员变量使用==private==修饰。
- 提供每一个成员变量对应的==setXxx（）/getXxx（）==。
- 必须提供一个==无参数构造器==。

