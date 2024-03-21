# java教程

## java快速入门

### java特点

- java是基于JVM虚拟机的跨平台语言，一次编写，到处运行；
- java程序易于编写，而且有内置垃圾收集，不必考虑内存管理；
- java虚拟机拥有工业级的稳定性和高度优化的性能，且经过了长时期的考验；
- java拥有最广泛的开源社区支持，各种高质量主键随时可用。

### java简介

1. java最早由SUN公司（已被Oracle收购）的詹姆斯•高斯林（**高司令，人称java之父**）在上世纪90年代初开发的一种编程语言，最初被命名为Oak。**在1995年以java的名称正式发布**，原因是Oak已被人注册了，因此SUN注册了java这个商标。

2. **java介于编程型语言和解释型语言之间**，编程型语言如C、C++。代码是直接编译成机器码执行，但是不同的平台（x86、ARM等）CPU的指令集不同，因此，需要编译出一种平台的对于机器码。解释型语言如Python、Ruby没有这个问题，可以直接由解释器直接加载源码然后运行，代价是运行效率太低。而java是将代码编译成一种“字节码”，它类似于抽象的CPU指令，然后，争对不同平台编写虚拟机、不同平台的虚拟机负责加载字节码并执行，这样就实现了“**一次性编写，到处运行**”的效果。当然，这是针对java开发者而言。对于虚拟机，需要为每个平台分别开发，为了保证不同平台、不同公司开发的虚拟机都能正确执行java字节码，SUN公司制定了一系列的java虚拟机规范。从实践的角度看，JVM的兼容性做得非常好，低版本的java字节码完全可以正常运行在高版本的JVM上。

3. 随着java的发展，SUN给java又分出了三个不同版本：

   - Java SE:Standard Edition

   - Java EE:Enterprise Edition

   - Java ME:Micro Edition

4. 这三者之间的关系：

   1. ![](D:\Study\Self\Typora\images\java版本区别.png)
   2. Java SE就是标准版本，包含标准的JVM和标准库，而Java EE是企业版，它只是在Java SE的基础上加上了大量的API和库，以便开发Web应用，数据库，信息服务，Java EE的应用使用的虚拟机和Java SE完全相同。
   3. Java ME就和Java SE不同，它是一个针对嵌入式设备的“瘦身版”，Java SE的标准库无法在Java ME上使用，Java ME的虚拟机也是“瘦身版”。
   4. Java SE是整个Java平台的核心，而Java EE是进一步学习Web应用所必须的。Spring等框架都是Java EE开源生态系统的一部分。

5. java版本

   从1995年发布1.0版本开始，到目前为止，最新的java版本是java21：

   <img src="D:\Study\Self\Typora\images\javaJDK版本.png" style="zoom: 50%;" />

   JRE就是运行Java字节码的虚拟机。Java源码要编译成Java字节码就需要JDK，JDK除了包含JRE，还提供了编译器，调试器等开发工具。

   - JDK：Java Devlopment Kit

   - JRE：Java Runtime Environment

      ![](D:\Study\Self\Typora\images\JDK与JRE关系.png)

   JSP是一系列的规范，从JVM的内存模型到Web程序接口，全部都标准化了，而负责审核JSR的组织就是JCP。

   - JSR规范：Java Specification Request
   - JCP组织：Java Community Process

6. java命令简介

   - java：可执行程序JVM，运行Java程序，就是启动JVM，JVM执行指定的编译后的代码；
   - javac：Java的编译器，它用于把Java源码文件（以.java后缀结尾）编译为Java字节码文件（以.class后缀结尾）；
   - jar：用于把一组.class文件打包成一个.jar文件，便于发布；
   - javadoc：用于从java源码中提取注释并生成文档；
   - jdb：java调试器，用于开发阶段的运行调试；

### 创建第一个Java程序

```java
public class Hello{
    public static void main(String[] args){
        System.out.println("Hello,world!")
    }
}
```

#### java程序简介

- 创建一个Hello的java程序，class称（类），类名是Hello，class用来定义一个类，public表示这个类是公开的，**public，class都是java的关键字**，必须小写，Hello是类名，按照习惯首字母H大写，而{}中间则是类的定义。

- main为类Hello内定义的一个方法，**方法是可执行的代码块**，一个方法除了方法名main，还有用（）括起来的方法参数，这里的main方法有一个参数，参数类型是String[]，参数名args，public，static用来修饰方法，void是方法的返回类型，而{}中间的就是方法的代码。这里表示main是一个公开的静态方法无返回值

- java规定，某个类定义的public staticvoid main(String[] args)是java程序的固定入口方法（主方法），因此java程序总是从main方法开始执行。
- java源码缩进不是必须的

- 文件名与类名一样，当保存文件时文件名必须为Hello.java，文件名也要求大小写

- java关键字

  | 类别                 | 关键字       | 说明                               |
  | -------------------- | ------------ | ---------------------------------- |
  | 访问控制             | private      | 私有的（只能在自己类或内部类访问） |
  |                      | protected    | 受保护的（只能在自己和子类访问）   |
  |                      | public       | 公共的（任何类的可以访问）         |
  |                      | default      | 默认（一般用于接口方法）           |
  | 类、方法和变量修饰符 | abstract     | 声明抽象                           |
  |                      | class        | 类                                 |
  |                      | extends      | 扩充、继承                         |
  |                      | final        | 最终值、不可改变的                 |
  |                      | implements   | 实现（接口）                       |
  |                      | native       | 本地、原生方法（非java实现）       |
  |                      | new          | 创建                               |
  |                      | static       | 静态                               |
  |                      | strictfp     | 严格浮点、精确浮点                 |
  |                      | synchronized | 线程、同步                         |
  |                      | transient    | 短暂                               |
  |                      | volatile     | 易失                               |
  | 程序控制语句         | break        | 跳出循环                           |
  |                      | case         | 定义一个值以供switch选择           |
  |                      | continue     | 继续                               |
  |                      | do           | 运行                               |
  |                      | else         | 否则                               |
  |                      | for          | 循环                               |
  |                      | if           | 如果                               |
  |                      | instanceof   | 实例                               |
  |                      | return       | 返回                               |
  |                      | switch       | 根据值选择执行                     |
  |                      | while        | 循环                               |
  | 错误处理             | assert       | 断言表达式是否为真                 |
  |                      | catch        | 捕捉异常                           |
  |                      | finally      | 有没有异常都执行                   |
  |                      | throw        | 抛出一个异常对象                   |
  |                      | throws       | 声明一个异常可能被抛出             |
  |                      | try          | 捕获异常                           |
  | 包相关               | import       | 引入                               |
  |                      | package      | 包                                 |
  | 变量引用             | super        | 父类、超类                         |
  |                      | this         | 本类                               |
  |                      | void         | 无返回值                           |
  | 保留关键字           | goto         | 是关键字，但不能使用               |
  |                      | const        | 是关键字，但不能使用               |
  
  

#### 运行java程序

- java源码本质是一个文本文件，我们需要先用javac把Hello.java编译成字节码文件Hello.class，然后用java命令执行字节码文件
- ![](D:\Study\Self\Typora\images\java源程序与编译型运行区别.png)

### java程序基础

#### java程序基本结构

1. public是访问修饰符，表示该class是公开的。不写public，也能正确编译，但这个类无法从命令行执行。
2. 一个文件源中只能有一个public类，一个文件源中可以有多个非publiuc类。
3. 源文件名称应该和public类的类名保持一致。
4. 类名必须以英文字母开头，后接字母，数字和下划线的组合，类名习惯以大写字母开头。
5. 如果一个类定义在某个包中，那么package语句应该在源文件的首行。
6. 如果源文件包含import语句，那么应该放在package语句和类定义之间。如果没有package语句，那么import语句应该在源文件中的最前面。
7. import语句和package语句对源文件中定义的所有类都有效。在同一源文件中，不能给不同的类不同的包申明。
8. 方法必须以英文字母开头，后接字母，数字和下划线的组合，类名习惯以小写字母开头。
9. 在内部方法中语句才是执行代码。java的每一行语句必须以分号（**;**）结束;
10. 在java程序中，注释是给人阅读的文本，不是程序的一部分，编译器会自动忽略注释，java注释有三种。
   - 单行注释`//以双斜杠(//)开头，直到这一行的结尾结束`
   - 多行注释`/*以斜杠星号（/*）开头，以星号斜杠（*/）结束，可以有多行*/`
   - 特殊的多行注释`/**以斜杠星号星号（/**）开头，以星号斜杠（*/）结束，可以有多行，每行通常以星号开头*/`

#### 变量和数据类型

1. 变量就是初中数学的代数的概念，变量就是指代在内存中开辟的存储路径，用于存放运算过程中需要用到的数据。

2. java语言有两大数据类型：内置数据类型、引用数据类型

   1. 内置数据类型

      - java语言提供8种基本类型，6种数字类型（4种整数型，2种浮点型），1种字符类型，还有1种布尔型

      | 序号 |     数据类型      | 位数 |   默认值    |                           取值范围                           | 简介                                                   | 字节 | 例子                                                         |
      | :--: | :---------------: | :--: | :---------: | :----------------------------------------------------------: | ------------------------------------------------------ | ---- | ------------------------------------------------------------ |
      |  1   |    byte（位）     |  8   |      0      |             Min：-128（-2^7） Max：127（2^7-1）              | byte数据类型是8位、有符号的，以二进制补码表示的整数    | 1    | `byte b=100;`                                                |
      |  2   |  short（短整型）  |  16  |      0      |          Min：-32768（-2^15） Max：32767（2^15-1）           | short数据类型是16位、有符号的以二进制补码表示的整数    | 2    | `short s=1000;`                                              |
      |  3   |    int（整型）    |  32  |      0      |  Min：-2,147,483,648（-2^31） Max：2,147,483,647（2^31-1）   | int数据类型是32位，有符号的以二进制补码表示的整数      | 4    | `int i=10000;`                                               |
      |  4   |  long（长整型）   |  64  |   0L（0）   | Min：-9,223,372,036,854,775,808（-2^63） Max：9,223,372,036,854,775,807（2^63 -1） | long数据类型是64位，有符号的以二进制补码表示的整数     | 8    | `long lg=10000L`                                             |
      |  5   |  float（单精度）  |  32  | 0.0（0.0f） |  Min：-2,147,483,648（-2^31） Max：2,147,483,647（2^31-1）   | float数据类型是单精度、32位、符号IEEE754标准的浮点数   | 4    | `float f=123.5f`                                             |
      |  6   | double（双精度）  |  64  | 0.0（0.0d） | Min：-9,223,372,036,854,775,808（-2^63） Max：9,223,372,036,854,775,807（2^63 -1） | double数据类型是双精度、64位、符合IEEE754标准的浮点数  | 8    | `double d1=7D;double d2=7.;double d3=8.0;double d4=8.D,double d5=123.12341;` |
      |  7   |   char（字符）    |  16  |   ‘u0000’   | 0-2^16-1 Min：\u0000（十进制等效值为0） Max：\uffff（即为65535） | char类型是一个单一的16位Unicode字符                    | 2    | `char c='A';`                                                |
      |  8   | boolean（布尔值） |  1   |    false    |                         true、false                          | boolean数据类型表示一位信息，只有两个取值：true和false |      | `boolean bl=true;`                                           |

      **附件：**

      ![补码，源码，反码](D:\Study\Self\Typora\images\补码反码源码.png)

   2. 引用数据类型

      - 在java中，引用类型是指向一个对象，指向对象的变量就是引用变量。
      - 对象、数组都是引用数据类型。
      - 所有引用类型的默认值都是null.
      - 一个引用变量可以用来引用任何与之兼容的类型。

   3. 常量

      - 常量在程序运行时是不能被修改的。
      - 在java中使用final关键字来修饰常量，声明方式和变量类似:`final double PI = 3.1415927;`

   4. 转换

      整形、实型（常量）、字符型数据可以混合运算。运算中，不同类型的数据先转化为同一类型，然后运算。

      转换从低级到高级：

      ![](D:\Study\Self\Typora\images\java基本数据类型大小.png)

      数据类型转换必须满足的条件和转换提示：

      - 不能对boolean类型进行类型转换。
      - 不能把对象类型转换成不相关的对象。
      - 在把容量大的类型转换为容量小的类型时必须使用强制类型转换。
      - 转换过程中可能导致溢出或者损失精度。
      - 浮点数到整数的转换是通过舍弃小数得到。而不是四舍五入。

      转换类型：

      ​	转换分为3大类型：自动类型转换，强制类型转换，隐含强制类型转换

      1. 自动类型转换
         - 必须满足转换前的数据类型的数位要低于转换后的数据类型。
      2. 强制类型转换
         - 条件是转换的数据类型必须是兼容的。
         - 格式：(type)value 其中type是要强制转换类型转换后的数据类型
      3. 隐含强制类型转换
         - 整数的默认类型是int
         - 小数的默认类型是double类型浮点数，在定义float类型时必须在数学后面跟上F或f。

   5. 等号为赋值符号。

   6. 小结

      - 定义变量时，要遵循作用域最小化原则，尽量将变量定义在尽可能小的作用域，并且，不要重复使用变量名。
      - java提供了两种变量类型：基本类型和引用类型
      - 基本类型包括整形，浮点型，布尔型，字符型。
      - 变量可重新赋值，常量初始化后不可从新赋值。
      - 大部分类型可以相互转换。

#### java运算符

java运算符可以分为以下几组：算数运算符，关系运算符，位运算符，逻辑运算符，赋值运算符，其他运算符

1. 算数运算符

   算数运算符在数学表达式中，它们的作用和数学中的作用一样。

   | 操作符 |                描述                |   例子   |
   | :----: | :--------------------------------: | :------: |
   |   +    |     加法（相加运算符两侧的值）     | 10+15=25 |
   |   -    |    减法（左操作数减去又操作数）    | 20-15=5  |
   |   *    |     乘法（相乘操作符两侧的值）     |  3*6=18  |
   |   /    |    除法（左操作数除以右操作数）    |  24/3=8  |
   |   %    | 取余（左操作数除以右操作数的余数） |  25%3=1  |
   |   ++   |      自增（操作数的值增加1）       |  ++1=2   |
   |   --   |      自减（操作数的值减少1）       |  --2=1   |

   注意：自增（++）/自减（--）是一种特殊运算符：

   ​		前缀自增/自减先进行自增/自减运算，在进行表达式运算。

   ​		后缀自增/自减先进行表达式运算，在进行自增/自减运算

2. 关系运算符

   关系运算符常用于判断表达式，验证二者之间的关系

   | 运算符 |                             描述                             |   例子   |
   | :----: | :----------------------------------------------------------: | :------: |
   |   ==   |  全等于（检查两个操作数是否相等，相等返回true，反之false）   | 10==10.0 |
   |   !=   | 不等于（检查两个操作数是否不相等，不相等返回true，反之false） |  12!=10  |
   |   >    | 大于（检查左操作数是否大于右操作数，大于返回true，反之false） |   10>5   |
   |   <    | 小于（检查左操作数是否小于右操作数，小于返回true，反之false） | 100<200  |
   |   >=   | 大于等于（检查左操作数是否大于或等于右操作数，大于或等于返回true，反之false） | 100>=99  |
   |   <=   | 小于等于（检查左操作数是否小于或等于右操作数，小于或等于返回true，反之false） |  9<=10   |

3. 位运算符

   位运算符作用在所有位上，并按位运算。

   例子：A=60，B=13即（二进制）A=00111100,B=00001101

   | 操作符 | 描                                                           | 例子               |
   | ------ | ------------------------------------------------------------ | ------------------ |
   | &      | 如果相对应位都是1，则结果为1，反之为0                        | A&B=12即00001100   |
   | \|     | 如果相对应位都是0，则结果为0，反之为1                        | A\|B=61即00111101  |
   | ^      | 如果相对应位值相同，则结果为0，否则为1                       | A^B=49即00110001   |
   | ~      | 按位取反运算符翻转操作数的每一位，即0变成1，1变成0           | ~A=-61即11000011   |
   | <<     | 按位左移运算符，左操作数按位左移右操作数指定的位数           | A<<2=240即11110000 |
   | >>     | 按位右移运算符，左操作数按位右移右操作数指定的位数           | A>>2=15即1111      |
   | >>>    | 按位右移补零操作符，左操作数的值按右操作数指定的位数右移，移动得到的空位以零填充 | A>>>2=15即00001111 |

4. 逻辑运算符

   | 操作符 | 描述                                         | 例子                |
   | ------ | -------------------------------------------- | ------------------- |
   | &&     | 逻辑与（两个操作数都为真，条件才为真）       | true&&false则false  |
   | \|\|   | 逻辑或（两个操作数任何一个为中，条件都为真） | true\|\|false则true |
   | !      | 逻辑非（用来反转操作数的逻辑状态）           | !true则false        |

   注意：当使用逻辑与运算符时，在两个操作数都为true时，结果才为true，但第一个为false时那则不会判断第二个操作。

5. 赋值运算符

   | 操作符 | 描述                                                     | 例子          |
   | ------ | -------------------------------------------------------- | ------------- |
   | =      | 等于（将右操作数的值赋给左侧操作数）                     | c=a+b则a+b=c  |
   | +=     | 加等于（将左操作数和右操作数相加赋值给左操作数）         | c+=a则c=c+a   |
   | -=     | 减等于（将左操作数和右操作数相减赋值给左操作数）         | c-=a则c=c-a   |
   | *=     | 乘等于（将左操作数和右操作数相乘赋值给左操作数）         | c*=a则`c=c*a` |
   | /=     | 除等于（将左操作数除以右操作数后赋值给左操作数）         | c/=a则c=c/a   |
   | %=     | 取余等于（将左操作数除以右操作数后的余数赋值给左操作数） | c%=a则c=c%a   |
   | <<=    | 左移位赋值运算符                                         | c<<=2则c=c<<2 |
   | >>=    | 右移位赋值运算符                                         | c>>=2则c=c>>2 |
   | &=     | 按位与赋值运算符                                         | c&=2则c=c&2   |
   | ^=     | 按位异或赋值操作符                                       | c^=2则c=c^2   |
   | \|=    | 按位或赋值操作符                                         | c\|=2则c=c\|2 |

6. 条件运算符（?:）

   条件运算符也被称为三元表达式，（例子）：value?value if true:value if false;

7. java运算符优先级

   多个运算符出现在一个表达式中。

   | 类别     | 操作符                                       | 关联性   |
   | -------- | -------------------------------------------- | -------- |
   | 后缀     | ()、[]、.(点操作符)                          | 左到右   |
   | 一元     | expr++、expr--                               | 从左到右 |
   | 一元     | ++expr、--expr、+、-、~、!                   | 从右到左 |
   | 乘性     | *、/、%                                      | 左到右   |
   | 加性     | +、-                                         | 左到右   |
   | 位移     | >>、>>>、<<                                  | 左到右   |
   | 关系     | >、>=、<、<=                                 | 左到右   |
   | 相等     | ==、!=                                       | 左到右   |
   | 按位与   | &                                            | 左到右   |
   | 按位异或 | ^                                            | 左到右   |
   | 按位或   | \|                                           | 左到右   |
   | 逻辑与   | &&                                           | 左到右   |
   | 逻辑或   | \|\|                                         | 左到右   |
   | 条件     | ?、:                                         | 从右到左 |
   | 赋值     | =、+=、-=、*=、/=、%=、>>=、<<=、&=、^=、\|= | 从右到左 |
   | 逗号     | ,                                            | 左到右   |

### 流程控制

#### 输入输出

总是使用：`System.out.println();`来向屏幕输出一些内容。

| 占位符 | 说明                             |
| ------ | -------------------------------- |
| %d     | 格式化输出整数                   |
| %x     | 格式化输出十六进制整数           |
| %f     | 格式化输出浮点数                 |
| %e     | 格式化输出科学计数法表示的浮点数 |
| %s     | 格式化字符串                     |

输入

```java
import java.util.Scanner;

public class Main{
	public static void main(String args){
		Scanner scanner = new Scanner(System.in);//创建Scanner对象
        System.out.print("your name:");//打印提示
        String name = scaner.nextLine();//读取一行输入并获取字符串
	}
}
```

#### if判断

根据条件来决定是否执行某段代码就需要if语句

```
if(条件){
	//条件满足时执行
}else{//可不写else
	//不满足条件执行
}
```

1. else是可选的
2. 当条件结果为true则执行if{}内语句，反之则不执行或者可以选择else不满足条件执行的语句。
3. 当if{}内只有一行语句可以省略{}，要注意if的边界。
4. 引用类型判断内容相等要使用equals()
5. 浮点数判断不能直接使用==运算符，不够精确

#### switch多重选择

根据表达式的结果，分别去执行不同的分支。

```
//假设条件=数字
int a=1;
switch(a){
	case 1:
		//当条件a==1时执行内容
	break;
	case 2:
		//当条件a==2时执行内容
	break;
	//以此类推
	default:
		//当条件a不满足上述case任意条件时执行
	break;
}
```

1. switch语句可以多重选择，然后执行匹配的case语句后续代码

2. switch的计算结果必须是整型，字符串或枚举类型

3. 当在两个或两个以上case后写break;语句在满足任意之一条件都会执行一样的break内代码；

4. 从java14开始，switch语句正式升级为表达式，不再需要break，并且允许私用**yield**返回值。

   ```
   switch(结果){
   	case "条件" -> //执行代码;
   	case "条件","条件" -> //执行代码;
   	default -> //执行代码;
   }
   //或
   int a = switch(结果){
   	case "条件" ->{
   		//任意代码
   		yield 返回值;
   	}
   	case "条件","条件" ->{
   		//任意代码
   		yield 返回值;
   	}
   	default -> {
   		//任意代码
   		yield 返回值；
   	}
   };注意赋值语句要以;结尾
   ```

#### while循环

while循环在每次循环开始前，首先判断条件是否成立。如果计算结果为true，就把循环体内的语句执行一遍，如果计算结果为false，那就直接结束循环。

```
while(条件表达式){
	//循环语句
}
```

while循环，是先判断在执行，可能一次都不执行

#### do……while循环

do……while循环是先循环，在判断条件是否成立，至少会循环一次

```
do{
	//循环语句
}while(条件表达式);
```

#### for循环

java使用最广泛的循环for，for循环使用计数器实现循环。for循环会先初始化计数器，然后在每次循环前检测循环条件，在每次循环后更新计数器。计数器变量命名通常为i。

```java
//例子，输出0-100
for(int i=0;i<=100;i++){
	System.out.println(i);
}
```

for循环通过计数器可实现复杂的循环

for each循环可以直接遍历数组的每一个元素

```java
int ns = {1,2,3,4,5,6};
for(int n:ns){
    Sytem.out.println(n);
}
```

#### break和continue

使用任意循环while或for,可以使用break和continue语句

**break**语句可以跳出当前循环，跳出最近的一层循环，可配合if语句使用。

**continue**语句和break类似，但是效果不同，可以提前结束本次循环，进行下一次循环

## 面向对象编程

java是一种面向对象的编程语句。面向对象编程，英文**Object-Oriented Programming**，简称**OOP**;

和面向对象编程不同的，是**面向过程编程**，面向过程编程，是把模型分解成一步一步的过程。

TODO类似于标记的作用，可以很快的定位到这个位置，方便查找。

1. 读取文件；
2. 编写TODO；
3. 保存文件；

而面向对象编程，是一种通过对象的方式，把现实世界映射到计算机模型的一种编程方法。

面向对象和面向过程是两种不同的编程思想和方法。面向过程编程是按照步骤顺序进行编程，将程序分解为若干给函数或者模块，以实现特定的功能，它强调每一步的细节和顺序，是一种比较直观的程序设计方法。面向对象编程则是以对象为中心进行编程，将程序设计的重点放在数据结构、对象之间的互动以及方法上，通过将功能进行封装，以及简化程序的设计和开发过程。它强调对象的属性和方法，将程序看作是一些对象的集合。总的来说，面向过程是以“做什么”为核心，面向对象是以“谁来做”的角度考虑问题，两种方法各有优缺点，具体选择视问题而定。

区别：

- 面向过程强调的是功能行为，以函数为最小单位，考虑怎么做。
- 面向对象，将功能封装进对象，强调具备了功能的对象，以类/对象为最小单位，考虑谁来做

联系：

- 二者均可实现代码重用和模块化编程；但面向过程简单直接，容易理解，面向对象更为复杂，模块化程度更高。从开发角度来看，面向对象比面向过程复杂，从维护和扩展功能的角度上来看，面向对象更容易操作。

例：人把大象关进冰箱。

1. 面向过程的分析过程

   1. 把冰箱门打开；
   2. 将大象放进冰箱；
   3. 把冰箱门关闭；

2. 面向对象的分析过程

   1. 分析动作是由那些实体发出的：

      人，冰箱，大象

   2. 定义主体，为其增加属性和功能：

      人：人需要有打开关闭冰箱，及将大象放入冰箱的功能

      冰箱：冰箱需要具有能开门和关门的属性

      大象：大象需要具有能够进入冰箱的功能

### 面向对象基础

现实世界中，五菱宏光、长城、保时捷、法拉利等……都是具体类型的车，但是车又可以概况它们，所以'车'可以定义为一个**类（class）**，而具体什么类型的车则定义为**实例（instance）**，以此类推……

- class是一种对象的模板，它定义了如何创建实例，一个class可以包含多个**字段（field）**

- instance是对象实例，**instance是根据class创建的实例，可以创建多个instance，每个instance相同，但各自属性可能不同**

- 在OOP中class和instance是“模板”和“实例”的关系，定义class就是定义了一种数据类型，对应的instance是这种数据类型的实例

- class定义的field，在每个instance都会拥有各自的field，且互不干扰

- 通过new操作符创建新的instance，然后用变量指向它，即可通过变量来引用这个instance

- 访问instance中field的方法是`变量名.字段名`

  ```java
  //创建Book书的class类
  class Book{
  	public String id;//编号
  	public String name;//书名
  	public double price;//价格
  }
  //创建Book书的instance实例
  Book book = new Book();
  //引用Book书的field字段
  book.id = "D1002";
  book.name = "java基础";
  book.price = 38.4;
  ```

#### 类（class）

一个class可以包含多个field,直接把field用public暴露给外部可能会破坏封装性，容易造成逻辑混乱。为了避免外部代码直接去访问field，我们可以用**private（私有的）**修饰field，拒绝外部访问。

通过创建构造函数，instance调用构造函数来修改和读取field的值，通过构造函数还可以检查传入参数的合理性，输出也可以自己定义。

```java
//创建Dog书的class类
class Dog{
	private String name;//名字
	private String colour;//颜色
	private int age;//年龄
	public String getName(){
		return name;
	}
	public void setName(String name){
		this.name = name;
	}
	public String getcolour(){
		return colour;
	}
	public void setcolour(String colour){
		this.colour = colour;
	}
	public String getAge(){
		return age;
	}
	public void setAge(int age){
		if(age>0){
			System.out.println("年龄必须大于0");
			return;
		}
		this.age = age;
	}
}
//创建Book书的instance实例
Dog dog = new Dog();
//调用Book书的构造函数写入方法
Dog.setName = "菜狗";
Dog.setColour = "red";
Dog.setAge = 5;

```

#### 构造方法

构造方法，当一个实例被创建时用来初始化该对象。构造方法和它所在的类的名字系统，构造方法没有返回值，也没有void，调用构造方法必须用new操作符。

- 在没有定义构造方法时，每个类都默认有一个默认无参的构造方法，如果我们自己定义了构造方法那么编译器将不再自动创建默认的构造方法
- 构造方法可以重载多个，编译器根据参数自动判断
- 可以在构造方法内部调用另一个构造方法，便于代码复用

```java
class Cat{
	private String name;
	public Cat(){}//默认构造方法
	public Cat(String name){//重载的构造方法
		this.name=name;
	}
}
```

#### 方法重载

**方法名相同，但各自的参数不同，称为方法重载。**方法重载返回的类型通常是相同的。方法重载的目的是功能类似的方法使用同一名字，更容易记住，调用起来更简单。例子如上；

#### 继承

继承可以复用代码，子类自动获得了父类的所有字段，严禁定义域父类重名的字段。

继承方法同名，方法会被重写，子类对象调用同名的方法优先，调用子类自己重写的。（覆盖）

在OOP术语中，有：超类（super class），父类（parent class），基类（base class），子类（subclass），扩展类（extended class）。

在java中，没有明确写extends的类，编译器会自动加上**extends Object**，任何类除了Object，都会继承某个类。如图：<img src="D:\Study\Self\Typora\images\继承01.png"  />

java中只允许一个class继承至一个类，一个类有且仅有一个父类。只有Object特殊，它没有父类。

<img src="D:\Study\Self\Typora\images\继承02.png"  />

继承的子类无法访问父类的private字段/方法，protected字段方法可以被其子类，以及子类的子类所访问。

super关键词表示父类（超类）,类似super.name\this.name\name。但有时必须使用super,super()调用父类的构造方法，如果没有默认构造方法，子类就必须显示调用super()并给出参数定位到合适的构造方法。

子类不会继承任何父类的构造方法，子类的默认构造方法是编译器自动生成的，不是继承的。

```java
class Person{
	private String name;//私用字段，本地访问
	protected int age;//受保护的字段，允许子类访问
	public String getName(){return name;}
	public void setName(String name){this.name=name;}
	public int getAge(){return age;}
	public void setAge(int age){this.age=age;}
}

class Student extends Person{
    //无需重复name和age字段/方法，只需要定义新字段score字段/方法
    private int score;
    public int getScore(){return score;}
	public void setScore(int score){this.score=score;}
}
class Teacher extends Person{
    //无需重复name和age字段/方法，只需要定义新字段job字段/方法
    private String job;
    public String getJob(){return job;}
	public void setJob(int job){this.job=job;}
}
```

##### 阻断继承

正常情况下，只要某个class没有final修饰符，那么任何类的可以从该class继承。

从java15开始，允许使用sealed修饰class,并通过permits明确写出能够从该class继承的子类名称。

sealed类主要用于一些框架，防止继承被滥用。

sealed类在java15中目前是预览状态，要启用它，必须使用参数--enable-preview和--source15。

```java
public sealed class Shape permits Rect,Circle,Triangle{}
//Shape类只允许指定的3个类继承（Rect,Circle,Triangle）如果定义一个其他类就会报错
```

##### 向上转型

可以把子类类型安全的变为父类类型的赋值，被称为向上转型（upcasting）。

向上转型实际是把子类型安全的变为更加抽象的父类型。

```java
//假设Students类型继承自Person类型，则
Person p = new Students();
//同理
Object o1 = new Students();
Object o2 = p;
//因为Person类型默认继承Object类型所以可以吧Students类型\Person类型，转换为更高层次的Object
```

##### 向下转型

和向上转型相反把**（父类实际指向为子类）向下转型成为子类**当父类实际指向为子类的时候才能转换成功，不能将父类转换为子类。

为避免向下转型出错，java提供了**instanceof**操作符，可以判断一个实例是不是某种类型

在java14开始，判断**instanceof**后可以直接转换为指定变量，避免二次转换。

**instanceof**实际判断一个变量所指向的实例是否是指定类型，或这个类型的子类。如果一个引用变量为null，那么对任何instanceof的判断都为false。

```java
Person p1 = new Person();
Person p2 = new Students();
if(p2 instanceof Students){}//false
if(p2 instanceof Students){//true
    //只有判断成功才会向下转型
    Students s = (Students)p1;
}
Object obj = "hello";
if(obj instanceof String s){
    //可以直接使用变量无需转换
    System.out.prinln(s.toUpperCase());
}
```

子类和父类的关系是is，has关系不能用继承。

#### 多态（Polymorphic）

多态是指，针对某个类型的方法调用，其真正执行的方法取决于运行时期实际类型的方法。

**Overide（覆写）Overload（重写）final（最终值）**

Overide是覆盖：方法名称，参数，返回值都是一样的。

Overload是新方法：方法名称一样，参数，返回值不一样。

final是唯一的常量：修饰字段的值不可改变（常量）修饰方法不可重写。

```java
class Person{
	public void run(){
		System.out.println("我是Person");
	}
    //当使用修饰符final的方法无法被覆写
    public final void hello(){
        System.out.println("Hello！");
    }
}
class Student extends Person{
	//可以验证覆写的正确性，写错会报错
	@Override
	public void run(){
		System.out.println("我是Student");
        //调用父类的run方法
        super.run();
	}
}
class Test{
    public static void main(String[] ages){
        //依靠实际类型动态调用，而非变量声明类型
        Person p=new Student();
        p.run();
        //输出“我是Studnet”
    }
}
```

如果Person没有run()方法，就会失去多态的特性，当声明变量类型为Person实际引用类型为Student调用run()方法会导致编译错误，除抽象类或接口外覆写的方法父类必须实现执行语句，否则会导致编译错误。

#### 抽象类（abstract class）

如果一个class定义了方法，但没有具体执行代码，这个方法就是抽象方法，抽象方法用abstract修饰，因为无法执行抽象方法，因此这个类也必须申明为抽象类（abstract class）。

使用了abstract修饰的类就是抽象类。无法实例化抽象类。

抽象类本身被设计成只能用于被继承，因此抽象类可以强迫子类实现其定义的抽象方法，否则编译会报错。抽象方法实际是相当于定义了"规范"。

**抽象类定义了抽象方法，那么实现子类的时候就必须覆写该方法。**

抽象方法类似多态，当定义了抽象类，以及实现了它的子类的时候，可以声明抽象类类型去引用具体的子类的实例。

面向抽象编程的本质：

- 上层代码只定义规范。
- 不需要子类就可以实现业务逻辑。
- 具体的业务逻辑由不同的子类实现，调用者并不关心。

```java
abstract class Person{//抽象类
    //抽象方法
	public abstract void run();//没有执行语句
}
class Student extends Person{
    //继承抽象类必须实现抽象方法
	//可以验证覆写的正确性，写错会报错
	@Override
	public void run(){
		System.out.println("我是Student");
        //调用父类的run方法
        super.run();
	}
}
class Test{
    public static void main(String[] ages){
        //依靠实际类型动态调用，而非变量声明类型
        Person p=new Student();
        p.run();
        //输出“我是Studnet”
    }
}
```

#### 接口（interface）

在抽象类中，抽象方法的本质就是定义接口规范：即规定高层类的接口，从而保证所有子类都有相同的接口实现，这样，多态就能发挥作用。

接口（interface）就是比抽象类还要抽象的纯抽象接口。

可以有字段，但接口字段默认为**public static final**所修饰的无法修改。

定义接口的所有方法都是**public abstract**的修饰，接口修饰符可以省略。

在java中继承一个类只能继承一个类，不能继承多个类。但一个类可以实现多个**interface**

##### 接口继承

一个interface可以继承另一个interface，使用extends，相当于扩展了接口的方法。

##### default方法

在接口中可以定义**default**方法，实现类可以不必要覆写default方法。当给接口新增方法时会涉及到修改全部子类，如果是用default方法，那么子类就不必修改，只要在需要的地方覆写。

有default修饰的方法，可以在接口中实现。

当声明变量为有default修饰的方法的类时，实际实例里面没有覆写默认调用接口的default方法。

```java
interface Hello{
    //字段修饰默认为public static final
    //public static final String name="";
    //必须初始化值，且不可修改
    String name="";
    void hello();
}
//继承接口Person拥有Hello接口的所有抽象方法字段
interface Person extends Hello{
    void run();
    //default修饰按需覆写
    default String runTxt(){
     	System.out.println("我是runTxt,需要我可以覆写");   
    }
}
//实现接口
class Students implements Person{
    public void hello(){
        System.out.println("我是hello,来自Hello，被Person继承，必须要覆写");
    }
    public void run(){
    	System.out.println("我是run，一定要覆写");
    }
}
```

#### 静态字段和静态方法

静态字段或静态方法，可以直接**Class.字段/Class.方法**无需创建实例。

##### 静态字段（static field）

在一个class中定义的字段，称为**实例字段**。

实例字段的特点：每个实例都有独立的字段，各个实例的同名字段互不影响。

还有一种字段，用**static**修饰，称为**静态字段（static field）**。

静态字段的特点：只有一个共享空间，所有实例都会共享该字段。

##### 静态方法

**用static修饰的方法称为静态方法**

调用实例方法必须要创建实例变量，而调用静态方法则直接**类名.方法**调用。

静态方法无法访问**this.字段**

```java
class Person{
	//默认为private字段
	//static int count;
    public static int count;
    
    String name;
    int age;
    //静态方法
    public static void addCount(){
        count++;
    }
    public static int getCount(){
       	return count;
    }
    //报错
    //public static void setName(String name){this.name=name;}
    public void setName(String name){this.name=name;}
    public String getName(){return name};
    public void setAge(int age){this.age=age;}
    public int getAge(){return age};
    
    public void run(){
        System.out.println(getName()+"\n"+getAge()+"\n"+count);
    }
}
public static void main(String[] ages){
    Person p1 = new Person();
    Person p2 = new Person();
    p1.setName("小红");
    p1.serAge(19);
    p1.count = 10;
    p2.setName("小蓝");
    p2.serAge(29);
    p2.count = 20;
    p1.run();//输出小红、19、20
    p2.run();//输出小蓝、29、20
    //调用静态
    Person.addCount();
    System.out.println(Person.count);//21
}
```

#### 包

java内建的package机制是为了避免class命名冲突。

JDK的核心类使用java.lang包，编译器自动导入。

JDK的其他常用类定义在java.util.*,java.math.*,java.text.*,……。

包名推荐使用倒置的域名。

#### 作用域

**public**（公共的）修饰的class、interface可以被其他任何类访问，修饰字段field、方法method，需要访问该class的权限。

**private**（私有的）只能在本地访问，如果该类定义了嵌套类，则嵌套类也拥有访问权限。

**nested class**（嵌套类）定义在一个class内部的class称为嵌套类。

**protected**（受保护的）作用于继承关系，修饰的字段和方法可以被子类访问，以及子类的子类。

**package**（包）指一个类允许访问同一个package的没有public、private修饰的class，以及没有public、protected、private修饰的字段和方法。

**一个java只能有一个public类，但可以包含无数个非public类。**

##### 局部变量

在方法内部定义的变量称为局部变量，局部变量从变量声明处开始到方法结束。方法参数也是局部变量。

##### final

final与访问权限不冲突。

修饰**类class**可以阻止被继承。

修饰**方法method**可以阻止被子类覆写。

修饰**字段field**可以阻止被重新赋值。

#### 内部类(Nested class)

内部类，它被定义在另一个类的内部，所以被称为内部类（Nested Class）。在java中内部类分为多种：

- Inner class：在一个类内定义了另一个类，这个类就是inner class。

- Anonymous class：匿名类，不需要明确地定义这个class，而是在方法内部。

- Static Nested class：静态内部类，和Inner class类似，多个static修饰符的类

  ```java
  public class Test{
   	public static void main(String[] ages){
          //内部类
          Outer o = new Outer("小明");
          Outer.Inner i = o.new Inner();
          i.hello();
          //匿名类
          o.Run();
          //静态类
          Outer.NInner ni = new Outer.NInner();
          ni.hello();
      }   
  }
  public class Outer{
      private String name;
      public Outer(String name){
          this.name = name;
      }
      //内部类Inner class
      class Inner{
          void hello(){
              //内部类的方法允许访问所在类的值
              System.out.println("Hello，"+Outer.this.name);
          }
      }
      //匿名类Anonymous class
      void Run(){//匿名方法
          Runnable re = new Runnable() {//匿名类
              @Override
              public void run() {
                  System.out.println("您好！这里是匿名类！");
              }
          };
          System.out.println("加载完成！");
          re.run();
      }
      //静态内部类Static Nested class
      public static class NInner{
          public void hello(){
              //不能访问本地非静态字段
              System.out.println("这里是静态内部类");
          }
      }
  }
  ```

#### classpath和jar

- classpath是JVM用到的一个环境变量，它用来指示JVM如何搜索class，通过classpath决定搜索class的路径和顺序
  - 不推荐直接设置环境变量，始终建议通过-cp命令传入

- jar包实际就是一个zip格式的压缩文件，而jar包相当于目录，里面可以包含很多.class的文件，方便下载使用。
  - MANIFEST.MF文件可以提供jar包的信息，可以直接运行jar包。

#### 模块

- Java 9引入的模块目的是为了管理依赖；
- 使用模块可以按需打包JRE；
- 使用模块对类的访问权限有了进一步限制。

### 核心类

**java的核心类**，包括：

- 字符串
- StringBuilder
- StringJoiner
- 包装类型
- JavaBean
- 举枚
- 常用工具类

#### 字符串和编码

##### String

String是一个引用类型，它本身也是一个类。java编译器对String有特殊处理，即可以直接用“……”表示一个字符串。

String方法在java中比较是否相同时用==不能正确判断

String字符串，相当于‘A’，‘B’，‘C’三个字符串联起来，组合成“ABC“字符串，组合后‘A’，‘B’，‘C’三个字符都是字符串”ABC“的子串

###### 字符串常用的方法

- equals()：比较两个字符串是否相同
- equalsIgnoreCase()：比较两个字符串是否相同（忽略大小写）
- contains()：检查是否包含子串（CharSequence是String实现的一个接口）
- indexOf()：从前开始搜索子串（返回第一个目标的索引）
- lastIndexOf()：从后开始搜索子串（返回第一个目标的索引）
- startsWith()：检查头部是否一致（返回true/false）
- endsWith()：检查尾部是否一致（返回true/false）
- substring()：提取子串，一个参数即索引至末尾，两个参数即索引至索引
- trim()：去除首尾空白字符
- strip()：去除首尾空白字符（空格字符\u3000也会被移除）
- isEmpty()：判断字符串长度是否为0（返回true/false）;
- isBlank()：判断字符串是否只包含空字符（返回true/false）;
- replace()：替换子串，两个参数第一个需要替换参数，第二个替换成为的参数。
- split()：字符串分割
- join()：字符串拼接
- formatted()|format()：格式化字符串，传入参数替换占位符，生成新字符串。（参数数量和类型要和占位符一致。如果不确定就用%s，可以显示任何数据）常用的占位符有
  - %s：字符串
  - %d：整数
  - %x：十六位进制整数
  - %f：浮点数
- valueOf()：转换成为字符串，编译器会根据参数自动选择合适的方法

###### 字符编码

在早期的计算机系统中，为了给字符编码，美国国家标准学会（American National Standard Institute：ANSI）制定了一套英文字母、数字和常用符号的编码，它占用一个字节，编码范围从0-127，最高位始终为0，简称**ASCII**编码。

为了统一全球所有语言的编码，全球统一码联盟发布了Unicode编码，它把世界上主要语言都纳入同一个编码，这样，不同的语言就不会冲突。

#### StringBuilder

它是一个可变对象，用来高效拼接字符串，新增字符时，不会创建新的临时对象，避免浪费内存，提高效率。

可支持链式操作，实现链式操作本身的关键是返回实例本身。

StringBuffer是StringBuilder的线程安全本版，现在很少用。

```java
StringBuilder ber = new StringBuilder();//可传参指定大小，或初始化内容
ber.append("");//添加字符
```



#### StringJoiner

用指定分隔符拼接字符串内容，使用StringJoiner或者String.join()更方便。

用StringJoiner拼接字符串时，还可以额外附加一个开头和结尾。

String.join()为String提供的静态方法，无需要指定开头和结尾的时候，用String.join()更方便。

```java
String.join(","，["A","b"]);//参数一分隔的字符，参数二需要分隔的数组，返回组合后的内容
var s = new StringJoiner(", ","Hello","!");//参数一分隔的字符，参数而初始化开头，参数三初始化结尾
s.add("")；//每次添加会自动加上，
```

