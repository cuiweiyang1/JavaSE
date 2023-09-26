[TOC]

# 自我介绍

**<font color= 'bludccc'>本人是一名在校大二学生,以下是我学习JavaSE的笔记分享,希望可以帮助大家</font> ** 

**<font color = 'redcc'>哪里有错误的地方希望大家及时纠正</font> **

![boos](https://gitee.com/cwy0710/image/raw/master/img/boos.jpg)

# 数据类型.

**<font color = "red">先简单介绍java中的语法可以速速过一遍</font>**

## 1.基本类型(八个)

## 数值型{

### 整型类型

- #### byte型：1字节 8bit位 第一位是符号位

  ```java
  byte a = 127;
  ```

  ####  

- #### short型：2字节 

  ```java
  short b = 32767;
  ```

  

- #### int 型：4字节

  ```java
  int c = 123;
  int c = 0b123;//二进制
  int c = 0123;//八进制
  int c = 0x123;//十六进制
  ```

  

- #### long型：8字节

  ```java
  long d = 123l;
  long d = 123L;//数字后缀L或l
  ```

  

0b或0B开头数字 为二进制

0开头数字为 八进制

0x或0X开头为16进制

### 浮点类型

- #### float ：4字节

- 单精度，尾数可以精确到7位有效数字

  ```java
  float e = 123.4f//数字后缀加f或F
  ```

  

- #### double： 8字节

- 双精度，精度是float的两倍。通常采用此类型。

  ```java
  double f = 123.4
  ```

  ######  %%java浮点型默认为double类型%%

  - **十进制数形式，例如: 3.14 314.0**

  - **科学记数法形式，如 3.14e2 3.14E2**

    

## }

### 字符型 （char）2字节

- ##### 使用了Unicode 编码 兼容了Ascll码

- ##### 可以参与算术运算，本质是使用了Unicode编码表中对应的10进制编号来进行计算

### 逻辑型(boolean)

- #### ture

- #### false

## 2.引用类型

### String类型(字符串)(相关API会在API.md文件里面介绍)

**String是一个类，String的变量是对象的管理者而非所有者**

- '+'相当于字符串连接符

- String s = "abcd";

- 1.任意八种基本数据类型的数据与String类型只能进行连接“+”运算(字符串连接)，且结果一定也是String类型

- 2.String类型不能转为其他的基本类型

```java
	String s = new String("a string");//创建一个String的对象，用“a string”初始化这个对象
 String a = "hello";
       String b = "world";
       String c = a + b;
       String d = a + b + 12;
       System.out.println(a);
       System.out.println(b);
       System.out.println(c);
     System.out.println(d);
```

```
  
运行结果:
  
  ```java
  
  hello
  world
  helloworld
  helloworld12
  
  Process finished with exit code 0
  
```

- **输入字符串**

  **in.next();**读入一个单词，单词标志是空格（包括空格、tap和换行）

  **in.nextLine();**读入一整行

- **比较两个String**

  ```java
  if(input == "bye"){//比较是否同一个
  	····
  }
  if(input.equals("bye")){//比较内容是否相同
  	····
  }
  ```

  **Strings因该用.equals 来比较**


### 接口(interface)(后面会介绍)

### 数组([])(后面专门介绍)

### 包裹类型（特殊的数据类型）

它用于将基本数据类型包装成对象

# 基本数据类型的转换

八种基本类型除了boolean类型以外，其他七种类型之间可以相互转化

## 转换规则：

### 1.默认转换

**将取值范围小的的类型自动提升为取值范围大的类型**

(byte,char,short(byte->short))->(int)->(long)->(float)->(double)

**4个字节float比8个字节long取值范围要大**

**原因: 浮点数在存储时结构与整数计算方式不同**

### 2.强制转换

容量大的转换为容量小的

**格式 ： (强制转换的类型) 变量名**

```java
int a =258;
byte b = (byte)a;
```

注:有多种类型的数据混合运算时，系统首先自动的将所有数据转换成容量最大的那一 种数据类型，然后再进行计算**会有精度损失**

# 算术运算

|        分类        |                   运算符                    |
| :----------------: | :-----------------------------------------: |
|     算数运算符     |          *   /   +   -   %  ++  --          |
|     赋值运算符     | +=， -=， /=， *=， %=(扩展赋值运算符)，  = |
| 比较（关系）运算符 |         == != > <=  >=  instanceof          |
|     逻辑运算符     |                                             |
|      位运算符      |                                             |
|     条件运算符     |       (条件表达式)? 表达式1：表达式2        |

## 算数运算符

### 1.‘+’

- 表示正数
- 进行加法运算（数值+数值，数值+‘字符’，‘字符’+‘字符’）
- 连接作用 （**字符串**+字符串，**字符串**+数值......**字符串**+其他）=**字符串**

### 2.‘-’

- 表示负数
- 减法运算（数值-数值，数值-‘字符’，‘字符’-‘字符’）
- 注：字符串没有减法

### 3.‘*’

### 4.‘/’

### 5.‘++’

++数值：先++再赋值y=x++ +3;//x+3

数值++：先赋值再++y=++x+3;//x+1+3

### 6.‘--’

### 7.‘%’

两边为整数

与++同理

## 赋值运算符

short s = 3;
s=s+2; ①会出错，因为2为int型
s+=2; ②是对的，+2后会进行隐式转换为s对应的数据类型

/= ，*=，-=，%=同理

![1688960932459](https://gitee.com/cwy0710/image/raw/master/img/1688960932459.png)

![1688961030282](https://gitee.com/cwy0710/image/raw/master/img/1688961030282.png)

注：**两边数据类型必须一致**

## 比较运算符（结果为true与false）

### 1.'=='

判断两边数值是否相等（基本类型与基本类型），Boolean与Boolean进行比较，String与String进行比较（引用类型与引用类型），

注意 字符串自己不能比较大小，Boolean与Boolean不能比较大小

### 2.'!='

数值!=数值，bool!=bool,string!=string;

### 3.'>'和'<'

数值与数值，字符与数值，字符与字符

### 4.'>='与'<='

与3同理

### 5.instanceof

**判断左边类型是否与右边类型一致**

```java
package homeworkday7.chouxiang;

public class Test {
    public static void main(String[] args) {
        Cuiweiyang dqw=new Dengqinwen();
        Cuiweiyang dqw2=new Dengqinwen2();
        Person zs = new Person();
          dqw.sleep();
          dqw2.sleep();
          Dengqinwen dqw3=(Dengqinwen) dqw;
          zs.feed(dqw3);
    }
}
package homeworkday7.chouxiang;

public class Person {
    public void feed(Cuiweiyang cuiweiyang){
        cuiweiyang.eat();
        if(cuiweiyang instanceof Dengqinwen){//判断cuiweiyang是否与Dengqinwen是一个类型
            System.out.println("转换为Dengqinwen成功!");
        }
    }
}

```

![1689579249022](https://gitee.com/cwy0710/image/raw/master/img/1689579249022.png)

## 逻辑运算符

### 1.& 逻辑与 

所有表达式结果为true，结果为true ，否则false

特点：当第一个表达式为false时，还会去继续执行第二个式子

### 2.&& 逻辑与/短路与

所有表达式结果为true，结果为true ，否则false

特点：当第一个结果为false时，不会再继续执行第二个式子

```java
int a=1;
        int b=2;
        int c=3;
        System.out.println(a>b&(b++)>c);
        System.out.println(b);
        b=2;
        System.out.println(a>b&&(b++)>c);
        System.out.println(b);
```

```
false
3
false
2
```



### 3.|  逻辑或

当所有表达式结果为false，结果为false，否则为true

特点：当第一个表达式为true时，还会去继续执行第二个式子

### 4.|| 逻辑或/短路或

当所有表达式结果为false，结果为false，否则为true

特点：当第一个表达式为true时，不会去继续执行第二个式子

```java
int a=1;
        int b=2;
        int c=3;
        System.out.println(a<b|(b++)>c);
        System.out.println(b);
        b=2;
        System.out.println(a<b||(b++)>c);
        System.out.println(b);
```

```
true
3
true
2

```



### 5.！ 逻辑非

！true = false，！false = true；

### 6.^ 逻辑异或 

相同为false 不同为true 

## 条件运算符

**(条件表达式)? 表达式 1 : 表达式2**

**若 条件表达式 为true 去执行表达式 1 ，否则执行表达式 2；**

## 位运算符

### 1.<< 左移

空位补0，被移除的最高位丢弃，空缺位补0

```java
int a=7;
        int b=4;
        System.out.println(b<<2);
        //0000 0100 4
        //0001 0000 16
```



### 2.>> 右移

被移位的二进制最高位是0，右移后，空缺位补0，最高位是1，空缺位补1

```java

        int b=4;
        System.out.println(b>>2);
        //0000 0100 4
        //0000 0001 1
```



### 3.>>> 无符号 右移

被移位二进制最高位无论是0还是1，空缺位都用0补

正数

```java

        int b=4;
        System.out.println(b>>>2);
        //0000 0100 4
        //0000 0001 1
```

 负数

```java
		int b=-4;
        System.out.println(b>>>2);
        /*
            0111 1111 1111 1111 
            1111 1111 1111 1100 -4
         */
        /*
            0011 1111 1111 1111
            1111 1111 1111 1110 1073741823
         */
```



### 4.& 与

对应两位都为1，则结果为1，否则0

```java
		int a=2;
        int b=4;
        System.out.println(a&b);
        /*
            0000 0010 2
            0000 0100 4 &
            0000 0000
         */
```



### 5.^ 异或

对应两位都相等，则结果为0，否则1

```java
		int a=2;
        int b=4;
        System.out.println(a^b);
        /*
            0000 0010 2
            0000 0100 4 ^
            0000 0110
         */
```



### 6.| 或

对应两位都为0，则结果为0，否则1

```java
		int a=2;
        int b=4;
        System.out.println(a|b);
        /*
            0000 0010 2
            0000 0100 4 |
            0000 0110
         */
```



### 7.~ 非

对所有位取反 1~0 0~1

```java
		int a=2;
        int b=4;
        System.out.println(~a);
        /*
            ~0000 0010 2
             1111 1101 -3(最高位为1)
         */
```

注:**使用byte类型移位时，系统会自动换为int进行位运算**

# 关键字

**具有特殊含义的  全部都是小写的**

# 标识符

**也就是名字,对类名,变量名称,方法名称,参数名称等修饰**

## 标识符命名规则

- 以字母,下划线_或者$开头,其后可以是字母,数字,下划线或$
- 如:Aa $h m5 abc69_
- 如:hello HELLO Hello

## 标识符命名规范

- 建议:见名知意,也就是说最好编写单词,如name age
- 建议:类名的每个单词首字母大写,和驼峰命名法 如:Hello,HelloWorld
- 建议:变量名称,方法名称,参数名称首字母小写,采用驼峰命名法,如age,getAge
- 建议:标识符长度不超过15个字符,如avg表示average......

# 字面值

- 整数类型字面值,如:99,100,-1;
- 浮点类型字面值:如:0.1,3.1415926
- 字符串类型字面值:如:"你好","98","3.1415926"
  - 字符串:表示一次可以存放0个,1个或多个,但是必须使用英文双引号引起来
- 字符类型字面值 如'a','7'
  - 字符类型:表示一次只能存放一个,并且使用英文单引号引起来
- 布尔类型字面值 如:true false 
  - 布尔类型:表示只有两个取值,分别是 ture false

# 控制台输入(Scanner类)

```java
import java.util.Scanner;//导包

public class BasicType {
    public static void main(String[] args){

        Scanner in = new Scanner(System.in);//Scanner 后面可以跟任何标识符来做对象，System.in为固定格式
        int a = in.nextInt();//读入整型
        float b = in.nextFloat();//读入浮点型
        double c = in.nextDouble();//读入浮点数
        boolean d = in.nextBoolean();//读入布尔类型
        String b = in.next();
        System.out.println(a);
        System.out.println(b);
    }
}
```

# 控制语句(基本C语言一样多了foreach循环)

条件语句 - 根据不同条件，执行不同语句

- if
- if...else
- if...else if
- if...else if ... else if...else
- switch

## if条件结构

if条件结构是根据条件判断之后再做处理

- **if-else**
- **if - else if....嵌套**

### switch语句

![1688981437307](https://gitee.com/cwy0710/image/raw/master/img/1688981437307.png)

### switch与if区别

![1688981481779](https://gitee.com/cwy0710/image/raw/master/img/1688981481779.png)

## for 循环

初始化-->判断条件 -->true(循环体)-->继续判断

​                      |false-->结束

**for格式**

```java
for(初始化;判断条件;步进){
		循环体
}
eg:for(int i=0;i<9;i++){
		sum+=i;
}
```

**增强for循环**

```java
for(元素类型 临时变量:遍历的数组){
	临时变量
}
for(int t : a){
    System.out.println(t);
}
```



## while循环

### while与do while

**while**格式

```java
while(判断条件){
	循环体
}
```

do while循环(不管满不满足判断条件 都先执行一遍循环体)

```java
do{
循环体
}while(判断条件)
```

# *print与println,printf区别

- **System.out.print();括号内必须含有参数**

- **System.out.println();括号内可以不含参数，此时代表newline即换行;**

- **System.out.printf();使用方法和C语言类似;**

# *标签、break、continue

当需要结束多个循环后,则使用标签

```java
label:for(int i=0;i<3;i++){
	for(int j=0;j<3;j++){
        if(j==2){
            break label;
        }
    }
}
```

break:只能跳出一个循环，要想跳出多个循环时，可以使用如上所示的标签；

续: continue 跳过本次循环，直接执行下次循环

# Java中的方法(函数)

**概念:用来实现某一功能**

- 习惯在面向过程的语言中把有名字的代码块称为函数
- 在面向对象的语言中称为方法
- java中的方法--C语言函数
- 将某个重复使用的一段代码块定义到一个有名字的代码块中
- 通过名字可以多次重复调用代码块
- 函数,方法-->某种功能

## **方法声明格式：**(与函数类似)

```java
[访问权限修饰符 修饰符...] [ 返回值类型 ] 方法名( 形式参数类型 参数名){

			java语句[函数体];

			[return 返回值;]

}
```



- <font color = 'blue'>修饰符</font>：这是可选的，告诉编译器如何调用该方法，定义了该方法的访问类型

- <font color = 'blue'>形式参数</font>：在方法被调用时用于接收外界输入数据

- <font color = 'blue'>返回值类型</font>：事先约定的返回值的数据类型，如无返回值，必须给出返回值类型void

- <font color = 'blue'>方法体</font>：方法体必须有{}括起来，在{}中编写完成方法功能的代码

- <font color = 'blue'>返回值</font>：方法在执行完毕后返还给调用它的环境数据。

  **return 返回值; return;(不返回任何数值)**

- <font color = 'blue'>实参</font>：调用方法时 实际传给方法的数据

**注：**

- **若方法再同一个类中，调用时，直接调用名字**
- **若方法不在一个类中，调用时:类名.方法名(静态方法)**

```java
eg:public class PracticeInClass {
    public static void main(String[] args) {
        print();//同一个类中
    }
    public static void print(){
        for(int i=1;i<10;i++){
            for(int j=i;j<10;j++){
                System.out.print(i+"*"+j+"="+i*j+" ");
            }
            System.out.println();
        }
    }
}

```

```java
public class PracticeInClass {
    public static void main(String[] args) {
       Function.print();//调用其他类的方法，类名.方法名
    }
}
```

```java
public class Function {
    public static void print(){
        for(int i=1;i<10;i++){
            for(int j=i;j<10;j++){
                System.out.print(i+"*"+j+"="+i*j+" ");
            }
            System.out.println();
        }
    }
}
```

```java
public class PracticeInClass {
    public static void main(String[] args) {
       Function.print();
       int a=10;
       int b=9;
        System.out.println(max(a,b));
    }
    public static int max(int a,int b ){
        return a>b?a:b;
    }
}
    //传参的方法
```

# 数组

## 概念

- **数组是一组相同数据类型元素的集合，是一个容器**
- **数组本身时引用数据类型，是一个对象**
- **数组可以存储基本数据类型，也可以存储引用数据类型**
- **数组创建时必须指定长度，且长度不可变**
- **数组中每个元素是连续的**

## 如何创建数组

**数组声明的两种方法**

**1. 数据类型 [] 数组名字；eg：int [] a;**

**2. 数据类型 数组的名字 []; eg：int a []**

**注：建议使用第一种**

**数组创建**

​	创建一个容量为5的数组：

```java
import java.util.Arrays;//声明这个包后就可以使用Arrays这个类的方法

public class ArrayPractice {
    public static void main(String[] args) {
        int [] a = new int[5];
        System.out.println(a);//输出的是存储数组元素的内存首地址
        System.out.println(Arrays.toString(a));//直接遍历出来[0, 0, 0, 0, 0]
       //创建数组时，值是已知的，直接进行赋值，就不需要指定长度
        int [] c = new int[]{1,2,3,4,5,6,7};
        //简化版
        int [] d = {1,2,3,4,5,6,7}; 
    }
}
```

## 数组的访问与迭代

- 数组元素的访问:

```java
数组名[索引] 例如：a[0],a[1];
```

- **注意**

```java
数组的索引从0开始。
索引的数据类型是整数(int)
索引最大值和数组长度始终差1
```

- 获取数组名长度

```
数组名.length
```

- **数组元素的遍历**

1.for循环

```java
for(int i=0;i<a.length;i++){
	System.out.println(a[i]);
}
```

2.增强for循环

```java
for(元素类型 临时变量:遍历的数组){
	临时变量
}
for(int t : a){
    System.out.println(t);
}
```

# 二维数组

## 定义：

数组的数组，二维数组的每一个元素是一个一维数组

## 数组的声明

```java
int[][]a;
int a[][];
```

**注：最好使用第一种声明方式，不容易混淆a的数据类型**

## 数组创建(会自动进行初始换为0)

```java
int [][]a = new int [][]{{1,2,3},{1,2,3},{1,2,3}};
int [][]a = {{1,2,3},{1,2,3},{1,2,3}};
int [][]a = new int[3][5];//定义了一个整型的二维数组 ,这个二维数组有3个一维数组,每一个一维数组包含5个元素
```

```java
int [][]a = new int [3][]//表示每一个一维数组为null，即没有创建；
    a[0]=new int[4];
	a[1]=new int[5];
	a[2]=new int[4];//对二维数组中的一维数组创建和初始化；
```

## 数组遍历

双层循环遍历

```java
eg:
int[][]a = {{1,2,3,3},{4,5,6,4},{7,8,9,5}};
//循环二维数组 从二维数组中每次取出一个一维数组
for(int i=0;i<a.length;i++){
    //遍历每一个一维数组
	for(int j=0;j<a[i].length;j++){
        //遍历一维数组
        System.out.print(a[i][j]+" ");
    }
    System.out.println();
}
```

# (重点)面向对象

## 面向过程与面向对象

**面向过程和面向对象都是程序设计的一种风格(思想);**

### 面向过程的程序思想(procedure -Oriented Programming),简称POP

- 关注焦点是过程：过程就是操作数据的步骤。如果某个过程的实现代码重复出现，那么就可以把这个过程抽取成一个函数，这样就可以大大简化沉余代码，便于维护。
- 是以函数(一个一个的功能)为结构进行代码组织
- 相对于面向对象语言，扩展能力差，后期维护难度较大

### 面向对象程序思想(Object Oriented Programming),简称OOP

- 关注焦点是**类**：在计算机程序设计过程中，参照现实中事物，将事物的属性特征，行为特征抽象出来，用类来表示。
- 以类为单位进行组织，每种事物都具备自己的**属性和行为/功能**类：一类问题/分类 String，Math，Array，Scanner······
- 以类为模版实例化对象,通过对象之间的交换来实现某种功能
- 是一种**设计思维**，适合解决复杂问题。代码扩展性强，可维护性高

```java
public class 类名{
    
}
```

<font color = 'red'>**注：**千万不要把面向过程和面向对象对立起来，他们是相辅相成的。面向对象离不开面向过程！</font>

**区别**：面向过程适合简单的问题.

​			面向对象适合复杂的问题，先宏观的分类设计，具体的某一个步骤落地时，有需要面向过程，他们是相辅相成的

## 类和对象(面向对象的核心概念)

### 类：

**概念：是具有相同特征的事物的抽象描述**，是对对象的概括和总结

#### 类的结构

- 变量：事物属性的描述（名词）

- 方法：事物的行为（可以做的事情 动词）

- 构造方法：初始化对象

- 块：没有名字的一个代码块

- 内部类：在类的内部定义的类

  ```java
  类的声明格式
  [访问权限修饰符][修饰符]class{
  	
  }
  访问修饰符有两种public，无(默认)
  修饰符：final,abstract
  关键字class用来定义一个类
  Java类名的命名规范:
  类名首字母大写,见名知意,驼峰表示
  ```



### 对象：(Everything is an object)

------

eg:人类-->一类群体 概念

​	  张三-->具体的人，对象

**概念：实际存在的该类事物的每个个体** ,也称为实例；**以类为模板在内存中创建的实际存在的实例**

- 同一个类的每个对象有不同存储空间

------

```java
package day5;

import java.sql.SQLOutput;

public class Car {
    /*
    定义属性 成员变量 直接在类{} 中定义内容，称为类的成员
     */
    String name;
    String color;
    int price;//不需要初始化
    /*
     定义方法 成员方法
     */
    public void run(){
        System.out.println("汽车行驶");
    }
    public void stop(){
        System.out.println("汽车停止");
    }
}

```

```java
package day5;

public class TestCar {
    public static void main(String[] args) {
        Car car=new Car();//
        //new这个运算符来创建一个对象。new的结果是一个对象的引用
        //new以Car类为模板，块独立的空间在内存中开辟一空间，用来存储对象信息
        /*
        Car(类型)car(变量名)声明一个Car变量=[把右边的对象地址赋值给左边的变量，用变量在后面的程序中表示内存中的对象]
        */
        car.name="宝马";
        car.color="黑色";
		car.run();
    }
} 
```

 

# *变量按位置分

<font color = 'redcc'>通过上面类的建立我们又得到了新的概念:<font color ='blue'>成员变量和局部变量</font></font>

## 成员变量:

- 可以使用基本数据类型，也可以使用引用数据类型.
- java中的变量在使用时必须初始化，成员变量不对其初始化，系统会对其默认初始化为 null或0；
- 成员变量可以在成员方法，构造方法，代码块中使用

### 补:成员变量和局部变量

- 在类中的位置不同

  ​	成员变量:在类中定义        局部变量:在方法中定义或方法参数

- 权限修饰不同

  ​	成员变量:可以使用访问权限修饰符

  ​	局部变量:不可以使用权限修饰符

- 初始化不同

  ​	成员变量:创建对象后,由构造方法初始化

  ​	局部变量:没有默认初始化,必须定义,赋值

- 生命周期不同

  ​	成员变量:随着对象的创建而创建,随着对象的消失而消失

  ​	局部变量:随着方法的调用而存在,随着方法的调用完毕而消失

- 在内存中的位置不同

  ​	成员变量:非静态成员变量与对象一起在堆内存中

  ​					静态成员变量与类信息在方法区中存储

  ​	局部变量:与方法一起在栈内存中

## 局部变量(在方法中定义)

- 系统不会对它自动初始化

**在同一类中,成员变量的名字可以与局部变量重名,但是局部变量优先,也就是就近优先**

**类中的成员和成员方法都必须创建出来的对象来调用**

# 类的构造方法

- 定义：构造方法与类名相同，且没有返回值，**且不需要void修饰**

```java
Car bmcar = new Car();
```

- 特点：类中没有定义时，会默认有一个无参的构造方法，在无参的构造方法中为成员变量赋初始值；我们**还可以定义有参的构造方法，通过有参构造方法为成员变量赋初值**

  一旦类中定义了有参的构造方法，那么默认的无参构造方法便会失效，调用不到，如果需要，需要显示的定义无参构造方法

- 作用：用来为新创建的对象中的成员变量进行初始化

  

```java
 public Car(){
        System.out.println("无参构造方法");
        name=null;
        color=null;
        price=0;
    }//无参构造
 Car car=new Car();// Car car=new Car();//无参调用
```

```java
public Car(String n,String m,int p){//有参构造
        System.out.println("有参构造方法");
        name=n;
        color=m;
        price = 300000;
    }
Car dzcar=new Car("大众","黑色",30000);//有参调用
```



# 方法重载

<font color='redcc'>**既然类的构造可以同名,那么我们写的方法能不能重名呢?**</font>

<font color='red'>这就是方法的**重载**</font>

- **概念**:方法的重载是指一个类中具有相同的名字，但参数个数不同的**多个方法**
- 如何区分名称相同的多个方法：通过参数的**个数，类型，顺序**来区分

**<font  color ="red">注：但系统无法区分返回值类型</font>**，所以方法的重载跟返回值类型没有任何关系

```java
    public Car(){
        System.out.println("无参构造方法");
        name=null;
        color=null;
        price=0;
    }
    public Car(String n,String m,int p){
        System.out.println("有参构造方法");
        name=n;
        color=m;
        price = 300000;
    }//这俩方法就是方法的重载
```

# 对象与引用

- Java语言中除了基本数据类型以外都属于引用类型
- Java中的对象是通过引用对其操作的

```javascript
class Car{
	String name;
	String color;
	int price;
}
Car bm = new Car();
```

- 右边的“new Car()”,是以Car类为模板，在堆空间里创建一个Car类对象
- 左边的“Car bm”创建了一个Car类型引用变量。所谓Car类的引用，就是以后可以用来指向Car对象的对象引用
- "="操作符使对象引用指向刚创建的那个Car对象(即把对象存储的地址赋值给了bm)

```java
我们可以把这句拆开两部分理解
Car bm;
bm = new Car;
这样写，就比较清楚了，有两个实体；一个是对象引用变量，一个是对象本身
```

- **参数传递：**

  两种：**值传递与引用传递**

- **<font  color ="blue">值传递</font>：(型参数类型是基本数据类型)**方法调用时，**实际参数把它的值传递给对应的形式参数**，形式参数只是用实际参数的值初始化自己的存储单元内容，是两个不同的存储单元，所以方法执行中形式参数值的改变不影响实际参数的值。

- **<font  color ="blue">引用传递</font>：(形参数类型是引用数据类型参数)**也称为**传递址**。方法调用是，实际参数是对象，这时实际参数与形式参数指向同一个地址，在方法执行中，对形式参数的操作实际上就是对实际参数的操作，这个结果在方法结束后被保留了下来，所以方法执行中形式参数的改变将会影响实际参数。
  <font  color ="red">**注：基本类型传递的是该数据值本身。引用类型传递的是对对象的引用，而不是对象本身 。但是无论是值传递还是引用传递,其本质都是传值,所以也都统称值传递**</font>

# this关键字

**<font color='redcc'>由于存在方法中参数的名字与类中名字重复的问题,我们该如何区分呢?</font>**

java中的this关键字就可以解决这种问题

- **this关键字代表前对象**
- **使用this关键字引用成员变量**
- **使用this关键字引用成员方法或构造方法**

**有了this关键字我们就可以来区分成员变量和局部变量**

**<font color = 'red'>注:一个方法中没有跟他同名的局部变量,可以不加this关键字</font>**



**this表示当前对象,即表示当前调用此方法的对象**

![1689387027564](https://gitee.com/cwy0710/image/raw/master/img/1689387027564.png)

# static关键字

**概念:可以用来就是属性,方法,代码块,内部快**

- 随着类的加载而加载
- 优先于对象存在
- **修饰的成员,被所有对象共享**

## static修饰的属性(静态成员变量)

**静态属性是类的所有对象共享的,静态属性在内存中只有一个**

- 静态变量的默认值规则和实例变量一样
- 静态对象在本类中,可以在任意方法代码块,构造器中直接使用
- 可以通过**类名.静态变量**直接访问,也可以通过**对象.静态变量**的方式访问(**更推荐类名.静态变量的方式**)

```java
static String name="zhangsan";
```

## static修饰的方法(静态方法)

- 静态方法在本类中,可以在任意方法代码块,构造器中直接使用
- 调用方式类似于静态变量
- **注:在static方法内部只能访问类的static修饰的属性或方法,不能访问类的非static的成员,但是非静态方法可以调用静态成员变量**
- **因为不需要实例就可以访问static方法,因此static方法内部不能有this和super**

**使用环境:当某种属性重复使用或某种方法与成员变量无关时,应设计成静态属性和静态方法,这样可以提高程序运行效率,节省运行所需内存**

# 代码块

## 实例代码块

```java
{
代码块
}
```

**在创建对象时,被自动调用执行**

## 静态代码块

```java
static{
代码块
}
```

**在类被加载时,被自动调用执行**

### 类什么时候被加载

{

- 通过类名访问类中静态成员时,类会被加载
- 在一个类中使用main方法,也会加载类
- 创建对象时也会被加载

**类只被加载一次,所以静态代码块只在类加载时执行一次**

}

```java
public class CodeBlock {
    static String name="lisi";
    {
        System.out.println("code1");
    }
    static{
        System.out.println("static code2");
    }

    public static void main(String[] args) {
        new CodeBlock();
        new CodeBlock();
        new CodeBlock();
    }
}
```

![1689407795785](https://gitee.com/cwy0710/image/raw/master/img/1689407795785.png)

**如果有多个静态代码块或实例代码块,他们会按照顺序加载**

# 包(Package)

**为方便管理类(按照不同的功能管理类),解决同名问题的发生**

- 使用package关键字修饰包

- 类名(全类名)=包名(地址)+类名简称

  ```java
  day1.Car
  ```

- 不能一次导入两个名称相同不同包的类**若想使用,则第二个要用全类名**

## 作用

- 按照不同功能管理类
- 避免类重名
- 控制访问权限

## 包名命名规范

- 在包名中,可以使用**.**号来区分包的级别;包名一般情况下是小写

  第一级 指该项目类型,如com,org,gov等

  第二级 指项目所开发或者运行的公司名称 如 sun huawei

  第三级 指项目的名称,如 bcms,oa,erp,cms等

  第四级 指项目模块的名称,如bean.action,exception等

## 导入外部包的类 关键字"import"

**在一个类中使用其他包中的类时,需要先使用import关键字导入进来**

**只有java.lang包中的类比较特殊,使用时不需要导入**

# 访问权限修饰符

**用来修饰类中的成员,控制是否可以被访问**

## public

**公共权限,在系统中哪里都可以访问**

- **修饰类(包含内部类),方法(构造方法,成员方法),成员变量**
- **如果一个类使用public修饰则文件名必须与类名一致**
- **类名前面可以没有public**

## protected

**受保护权限,在本类,同包类,不同包子类可以访问**

- **内部类,修饰方法(构造方法,成员方法),成员变量**

  

## (啥也不写)

**默认权限,在本类,同包类访问**

- **修饰类(包含内部类),方法(构造方法,成员方法),成员变量**

## private

**私有权限 只能在本类中使用**

- **修饰类(包含内部类),方法(构造方法,成员方法),成员变量**

```java
package day7.test1;

public class Test1 {
    public String name="张三";
    String name1="李四";
    private String name2="王麻子";
    protected String name3="666";

    public static void main(String[] args) {
        Test1 a=new Test1();
        System.out.println(a.name);
        System.out.println(a.name1);
        System.out.println(a.name2);
        System.out.println(a.name3);

    }
}
class TestTest2{
    public static void main(String[] args) {
        Test1 a=new Test1();
        System.out.println(a.name);
        System.out.println(a.name1);
//        System.out.println(a.name2);error//只能在private所属类调用
        System.out.println(a.name3);
    }
}

```

```java
package day7.test1;

public class TestTest {
    public static void main(String[] args) {
        Test1 a=new Test1();
        System.out.println(a.name);
        System.out.println(a.name1);
        //System.out.println(a.name2);error//私有的private只能在所属类调用
        System.out.println(a.name3);
    }
}

```

```java
package day7;

import day7.test1.Test1;

public class Test {
    public static void main(String[] args) {
        Test1 a=new Test1();
        System.out.println(a.name);
//        System.out.println(a.name1);//默认修饰符只能在所在包调用
        //System.out.println(a.name2);//私有的private只能在所属类调用
//        System.out.println(a.name3);//protect修饰的只能在所属包调用或者不同包子类
    }
}

```



# 面向对象语言三大特征(<font color = 'red'>重点!</font>)

## 封装

**含义:**

1. 包装,将一些常用的功能进行抽取,定义一个方法
2. 面向对象特征中的封装:隐藏,对类中的成员对外是否可见进行控制

**<font color = 'blue'>概念</font>：将类的某些信息隐藏在类的内部,不允许外部程序直接访问,而是通过该类提供的方法来实现对隐藏信息的操作和访问(总结:控制)**

**案例一:将类中属性私有化**

```java
package day7.test3;

public class Test3 {
    private String name;//将名字私有化,使用方法来控制
    private int age;
    //在本类中使用方法对私有的name进行初始化,方便控制name的初始化
    public void setName(String naem){
        if(name.length()<10){
            this.name=name;   
        }
    }
    public void setAge(int age) {
        if(age>=0&&age<150){
            this.age=age;
        }
    }
    public String getName(){
        return name;
    }
    public int getAge() {
        return age;
    }
}

```

```java
package day7.test3;

public class Test3Test {
    public static void main(String[] args) {
        Test3 a=new Test3();
        a.setName("张三");
        System.out.println(a.getName());
    }
}
```

**案例二:将某种方法私有化**

java设计模式(模板,固定套路)

解决一类问题的固定方式

单例模式,在系统中执行让某个类只创建一个对象

```java
package day7.test4;

public class Test4 {
    static Test4 test4=null;
    private Test4(){

    }
    //单一对象,只创建一个对象
    public static Test4 getTest4(){
        if(test4==null){
            test4=new Test4();
        }
        return test4;
    }
}
```

```java
package day7.test4;

import OOPUnderstand.Test;

public class Test4Test {
    public static void main(String[] args) {
        Test4 a=Test4.getTest4();
        Test4 b=Test4.getTest4();
        System.out.println(a);
        System.out.println(b);
    }
}
```

- 

## 继承

**子继承父,儿子就可以拥有父亲的功能**



**可以将这些共性的属性和行为抽取,这样就不需要在每个类中定义同样属性和行为,只需要类与类之间建立联系即可**



### **好处:**

- **减少代码的冗余,提高了代码的复用性,**
- **有利于功能的扩展**

### **使用环境**

- 满足is-a关系，即什么是什么(猫是动物,狗是动物)

### **继承语法**

**通过extends关键字,可以声明另一个A**

```java
[修饰符]class 类A{
    ......
}

[修饰符]class 类B extends 类A{
    ......
}
```

- 子类会继承父类所有的实例变量和实例方法
- 子类不能直接访问父类中私有的(private)的成员变量和方法
- 在Java中,继承的关键字用的是"extends",表示子类是对父类的扩展
- Java支持多层继承(继承体系)
- 一个父类可以拥有多个子类
- Java只支持单继承,不支持多重继承

**Java中如果一个类没有使用extends关键字显示的继承其他类,那么这个类默认继承Object类**

![1689492299941](https://gitee.com/cwy0710/image/raw/master/img/1689492299941.png)

**所以Java中所有的类都直接或间接的继承了Object类**

**注:父类不可以使用子类功能**

### 方法的重写

**当父类中的方法功能实现不能满足子类需求时,可以对方法进行重写(override)**

**子类可以对从父类中继承的方法来进行改造,在程序执行时,子类方法将覆盖父类方法,我么称为  方法的重写  也称方法的覆盖**

**注:构造方法,静态方法不能重写,成员变量不存在重写**

#### 方法重写的规则

1. 方法名必须和父类相同,参数列表相同(**否则调用的是父类方法**)

2. 方法返回值类型与父类保持一致

   **即子类重写方法结构与父类一致**

3. 子类方法使用的访问权限不能小于父类被重写的访问权限

   **注意:1.父类私有方法不能重写  2.跨包的父类默认权限的方法也不能重写**

4. 子类方法抛出的异常不能大于父类被重写方法的异常

#### @Override使用说明

@Override是java中定义的注解标签,用来进行标记(进阶部分细讲)写在方法上面，表示此方法是从父类重写而来,用来检测是不是满足重写方法的要求。
这个注解就算不写，只要格式满足要求，也是正确的方法覆盖重写。建议保留，这样编译器可以帮助我们检查格式，另外也可以让阅读源代码的程序员清晰的知道这是一个重写的方法

**帮助进行语法检测**

#### super关键字

java类中使用super来调用父类中的操作

- 用于访问父类中定义的属性
- 调用父类中定义的成员方法
- 用于在子类构造器中调用父类构造器

注意：

- 尤其当子父类出现同名成员时，可以用super表明调用的是父类中的成员
- super的追溯不仅限于直接父类还可以是父类的父类
- super和this的用法相像，this代表本类对象的引用，super代表父类的内存空间识的标

**误区:不要把super误认为识父类对象,在创建子类对象时,不会创建父类对象,只会将父类中的信息加载到子类对象中存储**

#### 继承中的构造方法

- 子类继承父类时，不会继承父类的构造方法。只能通过“super(形参列表)”的方式调用父类指定的构造方法。
- **规定super(形参列表)，必须声明在构造器的首行**。
- 如果在子类构造器的首行没有显示调用super(形参列表)，则子类此构器
  默认调用super()，即调用父类中空参的构造器。
- 这么做是为了保证先对父类成员进行初始化

**开发中常见错误**

- **如果子类构造器中既未显示调用父类或本类的构造器,且父类中又没有空参构造器,则编译错误**

```java
父类
package day7.extend;

public class Animal {
    private String name;
    private int age;
    public Animal(){
        System.out.println("父类无参初始化");
    }

    public Animal(String name, int age) {
        this.name = name;
        this.age = age;//this指当前对象
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public void eat(){
        System.out.println("eat thing");
    }
}

```



```java
 子类1
package day7.extend;


public class Cat extends Animal {
    public Cat(){
        //super();
        System.out.println("子类无参初始化");
    }

    public Cat(String name, int age) {
        super(name, age);
        System.out.println("有参构造");
    }

    @Override
    public void eat(){
        System.out.println("eat cat's food");
    }

}
class TestAnimal {
    public static void main(String[] args) {
        Cat mm = new Cat();
        System.out.println("年龄" + mm.getAge());
        System.out.println("名字" + mm.getName());
        mm.eat();
    }
}

```

运行结果:

![1689500705786](https://gitee.com/cwy0710/image/raw/master/img/1689500705786.png)

**无参构造有无super()结果都是一样的,不过推荐写上super()**

```java
package day7.extend;


public class Cat extends Animal {

    public Cat(){
        super();
        System.out.println("子类无参初始化");
    }

    public Cat(String name, int age) {
        //super(name, age);
        System.out.println("有参构造");
    }

    @Override
    public void eat(){
        System.out.println("eat cat's food");
    }

}
class TestAnimal {
    public static void main(String[] args) {
        Cat mm = new Cat("咪咪",2);
        System.out.println("年龄" + mm.getAge());
        System.out.println("名字" + mm.getName());
        mm.eat();
    }
}
```

![1689504634339](https://gitee.com/cwy0710/image/raw/master/img/1689504634339.png)

**注释掉super(name,age),后发现虽然调用子类中有参构造,但运行结果依然是未初始化的成员变量**

```java
package day7.extend;


public class Cat extends Animal {

    /**
     * chidongxi
     */

    public Cat(){
        super();
        System.out.println("子类无参初始化");
    }

    public Cat(String name, int age) {
        super(name, age);
        System.out.println("有参构造");
    }

    @Override
    public void eat(){
        System.out.println("eat cat's food");
    }

}
class TestAnimal {
    public static void main(String[] args) {
        Cat mm = new Cat("咪咪",2);
        System.out.println("年龄" + mm.getAge());
        System.out.println("名字" + mm.getName());
        mm.eat();
    }
}
```

![1689504754560](https://gitee.com/cwy0710/image/raw/master/img/1689504754560.png)

**取消掉注释后,加上super(name,age),就可以调用父类的有参构造方法对成员变量进行了初始化**

**注意,不能把子类构造方法中默认会调用父类无参构造方法,如果需要显示的使用super调用,必须放在构造方法的第一行,还可以调用父类中指定的构造方法**

![1689505060654](https://gitee.com/cwy0710/image/raw/master/img/1689505060654.png)

### 抽象类

**一个类中没有足够的信息来描绘一个具体的对象,这样的类就是抽象类**

**被abstract类关键字修饰的类,可能会出现抽象方法**

**注:抽象类除了不能实例化对象外,类的其他功能依然存在,成员变量,成员方法和构造方法,且没有抽象变量这一说法**

#### 特点:

1. 抽象类不能被实例化<font color ='red'>(**不能创建对象**)</font>,但可以有构造方法,因为抽象类中含有无具体实现的方法所以不能用抽象类创建对象
2. 抽象类只能用做**基类**,表示的是一种关系,继承**抽象类**的**非抽象类**必须实现其中的所有抽象方法,而已实现方法的参数,返回值要和抽象类中的方法一样,否则,该类也必须声明为抽象类

```java
[访问权限符] abstract class 类名{

}
public abstract class Abstract{
	
}
```



------

### 抽象方法

**抽象方法是一种特殊的方法:它只有声明,而没有具体的实现.**

```java
[权限修饰符] abstract [返回值类型] 方法名 (参数列表);
public abstract void setName(String name);
```

抽象方法必须用abstract关键字进行修饰

**<font color = 'red'>注:不可以抽象构造方法</font>**

**抽象方法是为了子类对其的重写,所有不能使用static修饰..被static修饰的为静态方法是可以通过类名直接调用的,但是抽象方法没有任何具体的实现,所以是错误的(静态的方法是不可以被重写的)**

## 多态

**多种状态**

父类的引用指向子类对象,从而产生多种形态

```java
Animal dog = new Dog();//这里Dog是Animal子类
Animal cat = new Cat();
```

同一种事物,在不同时刻表现不同状态

**二者之间存在直接或间接的继承关系时,父类引用指向子类的对象,即形成多态**

- 在编译期类型是父类,运行期类型是子类时,被称为父类引用指向子类对象

```java
class Animal{
....
}
class Cat extends Animal{
.....
}
class Dog extends Animal{

}
Animal cat=new Cat();
Animal dog=new Dog();//Animal的引用指向Dog的对象
```

### 向上转型

```java
package homeworkday7.chouxiang;

public abstract class Cuiweiyang {
    String name;
    String sex;
//public static abstract void setName(String name);不能使用static调用
    public abstract void eat();
    public abstract void setName(String name);
    public abstract void abst();
}
package homeworkday7.chouxiang;

public class Dengqinwen2 extends Cuiweiyang {

    public void eat(){
        System.out.println("喝水");
    }

    @Override
    public void setName(String name) {

    }

    @Override
    public void abst() {

    }
}
package homeworkday7.chouxiang;

public class Test {
    public static void main(String[] args) {
        Cuiweiyang dqw=new Dengqinwen();
        Cuiweiyang dqw2=new Dengqinwen2();
        dqw.eat();//编译期间调用的是父类eat,运行期间运行的是子类eat方法
       
    }
}
```

![1689575220912](https://gitee.com/cwy0710/image/raw/master/img/1689575220912.png)

**<font color ='orange'>编译期间是看父类,运行期间切记是在运行子类方法,就算子类无,父类有,也是运行子类所继承的方法,绝对不是运行父类方法</font>**

### 多态的好处:提高代码的扩展性

```java
class Animal{
	public void eat(){}
    ....
}
class Cat extends Animal{
	public void eat(){
        System.out.println("猫吃鱼");
    }
    .....
}
class Dog extends Animal{
	public void eat(){
    	System.out.println("狗吃骨头");
    }
        .....
}
class Test{
    public static void main(String[]args){
      Animal cat=new Cat();
	  Animal dog=new Dog();//Animal的引用指向Dog的对象  
    }
}

class Person{
    public void Feed(Animal animal){
        animal.eat;//此时传递的参数是子类对象的地址
    }
    //避免了下面的繁琐,提高代码扩展性
    public void Feed(Dog dog){
        dog.eat;
    }
    public void Feed(Cat cat){
        cat.eat;
    }
}

```

### 多态环境下对成员方法(非静态)的调用

```
如上,
cat.eat();
//调用的是子类中的方法
```

**简单来说就是:编译看左边,运行看右边**

### 多态环境下对静态成员方法的调用

```java
package homeworkday7.chouxiang2;
class Animal {
    public static void eat(){
        System.out.println("吃食物");
    }
}
class Cat extends Animal{
    public static void eat(){
        System.out.println("猫吃鱼");
    }
}
class Test{
    public static void main(String[] args) {
        Animal cat=new Cat();
        cat.eat();//调用的是Animal的方法
    }
}
```

![1689566001921](C:\Users\32477\AppData\Roaming\Typora\typora-user-images\1689566001921.png)

**简单的说:编译运行都看左边**

**<font color = 'red'>注意:变量不存在被子类覆盖写这一说法,只有方法存在覆写</font>**



**为了实现多态性,我们将子类类型向上转为了父类类型.但是一旦类型上升为父类类型,那么就调用不到子类特有的方法**

**解决办法:**

​			**就行向下转型,把父类转换为子类类型**

### 向下转型(强制类型转换)

格式 **[类型]对象名1 = (类型)对象名2**

**将后面大的父类对象转换为子类小的对象**

**注:同父类的子类不能相互转化**

```java
package homeworkday7.chouxiang;

public class Test {
    public static void main(String[] args) {
        Cuiweiyang dqw=new Dengqinwen();
        Cuiweiyang dqw2=new Dengqinwen2();
        Person zs = new Person();
          dqw.sleep();
          dqw2.sleep();
          Dengqinwen dqw3=(Dengqinwen) dqw;//把Cuiweiyang类型强制转化为子类的Dengqinwen类型
          zs.feed(dqw3);
    }
}

```

```java
Dengqinwen2 dqw4=(Dengqinwen2) dqw3;//错误,同父类的子类不能相互转化
```

![屏幕截图 2023-07-17 154410](https://gitee.com/cwy0710/image/raw/master/img/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202023-07-17%20154410.png)

### 优缺点

**优点**

1. 灵活性:多态使用使代码更加灵活,可以通过父类类型的引用变量来引用不同子类对象,从而实现不同对象的统一操作
2. 可扩展性:通过多态,我们可以方便地扩展和添新的子类,而不需要修改已有的代码
3. 代码重用:多态可以提高代码的重用性,通过定义父类类型的方法,可以在不同的子类中进行具体实现,减少了代码的冗余

**缺点**

1. 性能损失:多态需要在运行时进行动态绑定和方法调用,这会带来一定的性能损失,相比于直接调用子类方法,多台调用会稍微慢一些
2. 可读性降低:由于多态的特性,代码的行为可能会依赖于运行时的实际对象类型,这可能会增加代码的复杂性和难以理解程度
3. 限制:多态只能通过父类类型的引用变量来引用子类对象,而不能直接访问子类特有的方法和属性,如果需要访问子类特有的功能,需要进行类型转换

# final关键字

**用于修饰类 ,方法,参数和属性**

- 类:不能被定义抽象类或是接口,不可被继承

- 方法:子类里不可以重写

- 参数:参数值在方法中不可被修改

- 属性:定义时就必须直接赋值或者在构造方法中进行赋值,并且后期不能被修改

- ```java
  public final class A{
  	final int num=10;
      public final void Test( final int a){
          
      }
  }
  
  ```

  

# 接口(完全抽象的类)

- **一种更为彻底的抽象,主要用来定义功能**
- JDK8后可以定义4种内容

1. 静态常量
2. 抽象方法
3. 静态方法(JDK8后)
4. 默认方法(JDK8后)

**接口不能被创建对象**

------

## interface关键字

**使用interface关键字来实现接口的创建**

```java
public interface MyInterface {
    int num=0;// 默认为public static int num=0;
    void s();//默认为公共抽象方法即public abstract
}
```

```java
public interface MyInterface extends A,B{
			.......
}//一个接口可以继承多个接口
```

**注:一个类只能继承一个类,间接继承多个类**

​    **一个类可以实现多个接口**

​    **一个接口可以继承多个接口**

​    **接口不可以构造方法**

## implements关键字

```java
package day8.jk;

public class Test implements MyInterface {//implements关键字用来实现接口功能

    @Override
    public void Test() {
    }
    @Override
    public void Test3() {
    }
}

```

**一个类可以实现多个接口(多个接口表示多个功能,一个类需要哪些功能就去实现哪些接口)**

```java
package day9.animal;

public interface Fly {
    void Fly();
}
package day9.animal;

public interface Eat {
    void eat();
}
public class Bird extends Animal implements Fly,Eat {
    @Override
    public void eat() {
    }
    @Override
    public void Fly() {
    }
}

//Bird实现了Fly接口的功能和Eat接口功能且继承了Animal
```

**一个类如果实现接口**

1. 要么实现所有方法
2. 要么特此声明为抽象类

- **实现类和接口之间也是可以有多态关系的**
- **用一个接口,表示一类拥有此功能的类**

------

## 特性

- 接口是隐式抽象的,主要是**定义功能**
- 接口可以定义静态常量,抽象方法,静态方法,默认方法
- 一个接口可以继承其他多个接口
- 接口和抽象类一样,不能实例化对象
- 接口是要被类实现的,一个接口可以被多个实现
- 当类实现接口的时候.类要实现接口中所有的抽象方法,否则,该类必须声明为抽象的类
- 接口与实现类之间存在多态性

# 空指针异常

- **属于运行错误,<font color = 'red'>java.lang.NullPointerException</font>**
- 原因:当引用名称的值为null时,就不能方法某个对象中的属性或方法,如果非要访问则就出现空指针异常
- **解决办法:在访问某个对象中的属性或方法之前必须保证该引用名称中存放的是对象**

# API(看附件API.md)

# 正则表达式(常用的介绍)

- **是一种匹配语法,可以使用一些符号来定义一个规则,然后用规则与字符串进行匹配**

## 用法

- **调用String中的  <font color = 'blue'>match</font>    方法来定义规则**
- **也可以使用String中的 <font color = 'blue'>split</font> 方法来分割字符**

```java

	\d 匹配0~9之间的数字
	\\d 匹配一位数字
	\\d* 匹配多位数字
	\\d{n} 匹配n位数字
	\\d{n, } 匹配至少n位数字
	\\d{n,m} 匹配至少n个数字,最多m个数字
	[1234]匹配的一位数字必须是1,2,3,4
	[1234]* 匹配任意一位数字都是1,2,3,4
	[1-9] 匹配1-9之间的数字
	[a-z] a-z小写字母
	[A-Z] 大写字母
	[a-zA-Z] 可以是大写和小写字母 或[A-z]
	\w 匹配的是单词字符 相当于匹配[1-9] [A-z] [_] 注意区分大小写
	| 在正则表达式中表示 或
	. 也是正则表达式中的符号,匹配任意的字符,使用\\.表示
	
```

- 如手机号规则 第一位数字必须 1,第二位数字3,5,7,8,9 其余九位数字为任意数字

```java
boolean b1 = str.matches("1[35789]\\d{9}");//手机号规则
//其中str为字符串对象
```

- 再比如邮箱格式 字母+@+ 数字字母

```java
boolean b2 = str2.matches("\\w{6,10}@\\w{2,6}\\.(com|com\\.cn)");//str2为字符串
```

- 再比如利用正则表达式可以来使用<font color='blue'>split</font>方法来切割字符串

```java
String str3 = "ab1cd2ef";
String [] str4 = str3.split("\\d");//把含数字的删掉
```

- 或者利用正则表达式来使用<font color='blue'>replaceAll</font>方法来替换某些元素

```java
String str7 = str3.replaceFirst("\\d", "c");
```

<font color = 'red'>注:replace方法是不可以使用正则表达式的</font>

