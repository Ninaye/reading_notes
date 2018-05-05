## 第一章

##### 1、计算机界的摩尔定律：当价格不变时，集成电路上可容纳的元器件的数目，约每隔18-24个月便会增加一倍，性能也将提升一倍。

##### 2、多线程的发展和摩尔定律的失效有关，现在的人们已经不在追求更快的处理器了，而是着眼于获得更多的处理器（并发性）。

##### 3、在网页中运行的Java称为applet，要使用applet，需要启用Java的Web浏览器执行字节码。

##### 4、关于Java的常见误区：

##### 	1、Java是HTML的扩展：java是一种程序设计语言而HTML是一种描述网页结构的方式，除了用于在网页上放置Java applet的HTML扩展外，两者没有任何共同之处。

##### 	2、使用XML就不需要Java：XML是一种数据描述方式，而Java是一种程序设计语言。可以使用任何一种程序设计语言处理XML数据，而Java API对于XML处理提供了很好的支持。

##### 	3、Java将成为适用于所有平台的通用性编程语言：理论上是完全有可能的，但是实际中某些领域其他语言有更出色的表现，比如JavaScript在浏览器中的作用 。

##### 	4、Java是解释型的，对于关键的应用程序速度太慢：现在的Java虚拟机使用了及时编译器，因此采用Java写的“热点“代码运行速度和C++相差无几。

##### 	5、JavaScript 是Java 的简易版：JavaScript 是一种在网页中使用的脚本语言， 语法类似Java, 除此之外，两者无任何关系。与Java applet 相比，JavaScript 更紧密地与浏览器集成在一起。特别是JavaScript 程序可以修改正在显示的文档， 而applet 只能在有限的区域内控制外观。



## 第二章

##### 1、一般看到Bad command or file name 或者 javac:commond not found之类的错误一般是 执行路径错误的问题。



## 第三章

##### 1、java应用程序退出代码为0，表示成功的运行了程序。运用System.exit方法可以在程序终止时返回其他代码。



### 数据类型

##### 1、Java中有8中基本数据类型，其中4种整型、2种浮点类型、1种用于表示Unicode编码的字符单元的字符类型char和一种用于表示真值的boolean类型。

##### 	整型：int--4字节、short--2字节、long--8字节、byte--1字节。

##### 	浮点型：float--4字节（有效位数6~7位，后缀要加L）、double--8字节（有效位数为15位，后缀D可有可无）。

##### 	正无穷：Double.POSITIVE_INFINITY。

##### 	负无穷：Double.NEGATIVE_INFINITY。

##### 	0/0和负数的平方根：Double.NaN（不是一个数字）判断一个数是否为NaN用Double.isNaN方法。

##### 2、int a = 1000000 可以写成 int a = 1_000_000在编译时Java编译器会除去这些下划线。



### 变量

##### 	1、Java变量名必须是一个以字母开头并由字母或者数字构成的序列，大小写敏感，变量长度无限制。

##### 2、声明一个变量后必须使用赋值语句对变量进行显示的初始化。

##### 	3、Java中不区分变量的声明与定义。

##### 	4、常量，在Java中用关键字final指示常量，关键字final表示这个变量只能被赋值一次，一旦被赋值之后就不能够更改了。

##### 	5、关键字static final可以设置一个类常量， 该常量可以在一个类的多个方法中使用，类常量的定义位于main方法的外部， 同时如果一个常量被声明为public，那么其他类也可以使用这个常量。

##### 	6、const是Java保留的关键字，但是目前并没有使用。



### 运算符

##### 	1、一般处理器处理浮点数运算时都会增加中间过程的计算精度，但可以使用strictfp关键字标记的方法来使用严格的浮点计算   比如public static strictfp void main(String args[]),使得main函数内部的所有运算都使用严格的浮点计算。

##### 	2、Math.floorMod(a+b,Mod);使得结果总为正的余数 == ((a+b)%Mod+Mod)%Mod

![52300144317](C:\Users\Ninaye\AppData\Local\Temp\1523001443179.png)

其中虚线表示转换过程中可能存在精度损失，实线表示转换过程中不存在精度损失

##### 	3、如果想对浮点数进行舍人运算， 以便得到最接近的整数（在很多情况下， 这种操作更有用)，那就需要使用Math_round 方法：

##### 	4、最后>>> 运算符会用0 填充高位，这与>>不同，它会用符号位填充高位。不存在<<<运算符。



##### 枚举类型：变量的取值范围只在一个有限的集合内 enum Size{SMALL,MEDIUM,LARGE,EXTRA_LARGE};

##### 		   Size s = Size.MEDIUM;



### 字符串

##### 	1、可以通过substring方法获得一个子串。

##### 		String greeting = "Hello";

##### 		String s = greeting.substring(0, 3);	// 效果是创建了一个子串"Hel"   创建规则左闭右开

##### 	2、可以使用+号连接两个字符串。

##### 		String expletive = "Expletive";

##### 		String PG13 = "deleted";

##### 		String message = expletive + PG13;	//效果就是拼接成一个字符串"Expletivedeleted"

##### 	3、如果需要把多个字符串放在一起， 用一个定界符分隔，可以使用静态join 方法。

##### 		String all = String.join(" / ", "S", "M", "L", "XL");		// all is the string "S / H / L / XL"

##### 	4、空串和null串是有区别的，空串代表的是字符串的长度为0的串。

##### 	5、代码点：是指一个编码表中的某个字符对应的代码值，也就是Unicode编码表中每个字符对应的数值。

##### 	6、大多数常用的Unicode字符使用一个代码单元就可以表示，而辅助字符需要一对代码单元表示。

##### 	7、int compareTo(String other) 按照字典顺序， 如果字符串位于other 之前， 返回一个负数；如果字符串位于other 之后，返回一个正数； 如果两个字符串相等，返回0。

##### 	8、new String(int[] codePoints, int offset, int count) 用数组中从offset 开始的count 个码点构造一个字符串

##### 	9、boolean equalsIgnoreCase(String other )如果字符串与other 相等（忽略大小写)，返回true。

##### 	10、boolean startsWith(String prefix)   boolean endsWith(String suffix)如果字符串以suffix 开头或结尾，则返回true。

##### 	11、int indexOf (String str)

##### 		int indexOf (String str , int fromlndex)

##### 		返回与字符串str匹配的第一个子串的开始位置。这个位置从索引0 或fromlndex 开始计算。如果在原始串中不存在str， 返回-1。

##### 	12、int lastIndexOf (String str)

##### 		返回与字符串str匹配的最后一个子串的开始位置。这个位置从索引0 或fromlndex 开始计算。如果在原始串中不存在str， 返回-1。

##### 	13、String toLowerCase()：转换为小写字母

##### 		String toUpperCase()：转换为大写字母

##### 	14、String trim()：返回一个去除两头空格的新字符串

##### 	15、String replace(CharSequence oldString, CharSequence newString):用newString替换字符串中的oldString

#####  	16、StringBuilder()构造一个空的字符串构建器。 

##### 	17、StringBuilder append(String str)追加一个字符串并返回this。

##### 	18、StringBuilder insert(int offset,String str)在offset 位置插入一个字符串并返回this。

##### 	19、StringBuilder insert(int offset,Char c)在offset 位置插入一个代码单元并返回this。

##### 	20、StringBuilder delete(int startindex,int endlndex)删除偏移量从startindex 到-endlndex-1 的代码单元并返回this。

##### 	21、String toString()返回一个与构建器或缓冲器内容相同的字符串



### 输入输出

##### 1、读取输入Scanner cin = new Scanner(System.in);    需要import java.util.*;

##### 2、String name = cin.nextLine();	//读入一行

##### 3、String firstName = cin.next();	//读入下一个的单词（以空白符作为分隔符） 

##### 4、int age = cin.nextInt();		//读取下一个整数

##### 5、import java.io.*;   里的Console类的char passwd[] = cons.readPassword("Password: ");可以隐藏密码，同时每次只能读一行以\n作为结束的标志。

##### 6、Java也有printf()方法

##### 7、可以使用静态的String.format方法创建一个格式化的字符串，而不打印输出：String message = String.format("Hello, %s, Next year, you'll be %d",name,age);

##### 8、文件读入	Scanner in new Scanner(Paths.get("myfile.txt"),"UTF-8");

##### 9、文件写入PrintWriter out = new PrintWriter("myfile.txt", "UTF-8");

```java
import java.util.*;
import java.io.*;
public class Main{
	public static void main(String args[]) throws IOException{
		PrintWriter out = new PrintWriter("./myfile.txt","UTF-8");			
		String name = "Ninaye";
		int age = 21;
		String str = String.format("hello, %s. Next year ,you'll be %d",name,age);
		out.println(str);
		out.printf("%1s %2tB %2te, %2tY", "Due date:\n", new Date());
		out.close();		//流如果不关闭则不会写入到。
	}
}
```

##### 10、显示自己的当前路径String dir = System.getProperty("user.dir");



### 大数值

##### 1、java.math中的BigInteger用于处理包含任意长度数字序列的数值，BigDecimal实现任意精度的浮点数运算。

##### 2、可以使用静态发方法valueOf方法可以将普通的数值转换为大数值BigInteger a = BigInteger.valueOf(100);

##### 3、Java没有提供运算符重载功能

##### 4、BigInteger add(BigInteger other);			//加

##### 5、Biglnteger subtract(Biglnteger other)		//减

##### 6、Biglnteger multipiy(Biginteger other)		//乘

##### 7、Biglnteger divide(Biglnteger other)		//除

##### 8、Biglnteger mod(Biglnteger other)			//模

##### 9、int compareTo(Biglnteger other)			//两个大数是否相等

##### 10、static Biglnteger valueOf(long x)			//返回值为大数类型



### 数组

##### 1、int a[] = new int[100];

##### 2、创建一个数字数组时， 所有元素都初始化为0。boolean 数组的元素会初始化为false。对象数组的元素则初始化为一个特殊值null , 这表示这些元素还未存放任何对象。

##### 3、for each循环

```java
for (int element : a)			//循环a中的每一个元素  for each element in a
    System.out.println(element);
```

##### 4、在Java 应用程序的main 方法中， 程序名并没有存储在args 数组中。例如，当使用下列命令运行程序时

##### 	java Message -h world 

##### 	args[0] 是“ -h”， 而不是“ Message” 或“ java”。

##### 5、数组二分查找 static int binarySearch(type[] a, type v);		//如果查找成功，则返回相应的下标值；否则返回一个负数值r，-r-1 是为保持a 有序v 应插入的位置。

##### 6、数组快速排序 static void sort(type[] a);

##### 7、static void fill(type[]a , type v) 		//将数组的所有数据元素值设置为v。

##### 8、static boolean equals(type[]a, type[]b)	//如果两个数组大小相同， 并且下标相同的元素都对应相等， 返回true。

##### 9、多重循环的for each语句

```java
int [][] a = {
    {1,2,3,4},
    {4,5,6,7},
    {8,9,10,11},
    {12,13,14,15}
};
for (double[] row : a)
	for (double value : row)
		do something with value
```

##### 10、Java 实际上没有多维数组， 只有一维数组。多维数组被解释为“ 数组的数组。”



## 第四章 对象与类

##### 1、实现封装的关键在于绝对不能让类中的方法直接地访问其他类的实例域。程序仅通过对象的方法与对象数据进行交互。这是提高重用性和可靠性的关键。

##### 2、Object类是所有类的父类。

##### 3、识别类的简单规则是在分析问题的过程中寻找名词，而方法对应着动词。

##### 4、类之间的最常见的关系就是

- ##### 依赖（“uses-a")

- ##### 聚合（”has-a")

- ##### 继承（“is-a”）


##### 5、java中使用构造器构造新实例   Date data = new Date() 	//new 后面的就是构造器

##### 6、一个对象并没有实际包含一个对象，而仅仅引用一个对象   new 操作符的返回值也是一个引用

##### 7、局部变量不会自动地初始化为null，而必须通过调用new或将他们设置为null进行初始化

#####  8 、LocalDate类

```java
import java.time.LocalDate;			//所在的库
LocalDate.now()					   //获取当前时间（公历）
LocalDate.of(1999, 12, 31)			//构造一个特定的时间的对象
//一旦有了一个LocalDate 对象， 可以用方法getYear、getMonthValue 和getDayOfMonth得到年、月、日
LocalDate aThousandDaysLater = newYearsEve.piusDays(nextdate);	//当前日期后nextdate的日期
```

##### 9、当java编译器编译时用到某个类的时候，如果没有找到就会自动地搜索相应的java文件，然后对它进行编译。可以认为java编译器中内置了"make"功能。

##### 10、类的封装的好处，修改内部实现的时候，除了该类的方法外，不会影响其他代码。

##### 11、一个方法可以访问所属类的所有对象的私有数据，比如Employee类的方法可以访问Employee的任何一个对象的私有域。

##### 12、final类似于C++中的const，必须被初始化，而且只能初始化一次，同时不能被继承。

##### 13、对于可变的类final 关键字只是表示存储在变量中的对象引用不会再指示其他对象，可以修改。



### 静态域

##### 1、如果将类域定义为static，则每个类中只有一个这样的域，而每个对象对于所有的实例域都有一个自己的拷贝。

##### 2、又称为类域（属于该类的，就算没有对象也存在）

```java
class Employee{
    private static int nextId = 1;
    private int id;
}
public void setId(){
    id = nextId;		//harry.id = Employee.nextId;
    nextId++;			//Employee.nextId++;
}
```

##### 3、如果查看一下System 类， 就会发现有一个setOut 方法， 它可以将System.out 设置为不同的流。读者可能会感到奇怪， 为什么这个方法可以修改final 变量的值。原因在于， setOut 方法是一个本地方法， 而不是用Java 语言实现的。本地方法可以绕过Java 语言的存取控制机制

##### 4、静态方法是一种不能向对象实施操作的方法，可以理解为金泰方法没有this参数，不能访问实例域，但是可以访问自身类的静态域。

```java
class Employee{
    private static int nextId = 1;
    private int id;
    Public static int getNextId(){
        return nextId;
    }
}
int n = Employee.getNextId();
```

##### 5、下面两种情况下使用静态方法：

- ##### 一个方法不需要访问对象状态，其所需参数都是通过显示参数提供的（例如：Math.pow）。

- ##### 一个方法只需要访问类的静态域。

##### 6、每一个类都可以有一个main方法。

##### 7、Java中方法参数的使用情况：

- ##### 一个方法不能修改一个基本数据类型的参数。

- ##### 一个方法不能改变一个参数对象的状态。

- ##### 一个方法不能让对象参数引用一个新的对象。

##### 8、如果多个方法有相同的名字、不同的参数、便产生了重载。

##### 9、调用构造器的具体处理步骤：

1. ##### 所有数据域被初始化为默认值（0，false或null）。

2. ##### 按照在类声明中出现的次序，依次执行所有域初始化语句和初始化块。

3. ##### 如果构造器第一行调用了第二个构造器，则执行第二个构造器的主体。

4. ##### 执行这个构造器的主体。

```java
Random generator = new Random();		//构造一个新的随机数生成器。
nextld = generator.nextlnt(lOOOO);		//返回一个0 ~ n-1之间的随机数。
```

##### 10、java有自动的垃圾回收器，所以java不支持析构器。

##### 11、如果某个资源需要在使用完毕后立刻被关闭，那么就需要由人工来管理。对象用完时，可以应用一个close 方法来完成相应的清理操作。

##### 12、finalize方法可以用于回收资源。



### 包

##### 1、所有标准的Java包都处于java和javax包层次中。

##### 2、编译器在编译原文件的时候不检查目录结构，但是如果目录结构和包名不一致的话，虚拟机就找不到这个类，最终程序无法运行。

##### 3、包作用域：没有指定public或者private，这个部分（类、方法或变量）可以被同一个包中的所有方法访问。



### 文档注释 javadoc

##### 1、可以用javadoc + 文件名.java生成在线文档。

##### 1、注释的插入：javadoc实用程序（utility）从下面几个特性中抽取信息：

- ##### 包

- ##### 公有类与接口

- ##### 公有的和受保护的构造器及方法

- ##### 公有的和受保护的域

##### 2、方法注释：每一个方法注释必须放在所描述的方法之前

- ##### @parma变量描述

- ##### @return描述

- ##### @throws类描述

##### 3、域注释：只需要对公有域（通常指的是静态常量）建立文档。

##### 4、通用注释：

- ##### @author 姓名：这个标记将产生一个“author”( 作者）条目。

- ##### @version 文本：这个标记将产生一个“ version”（版本）条目。这里的文本可以是对当前版本的任何描述。

- ##### @since 文本：这个标记将产生一个“ since” （始于）条目。这里的text可以是对引人特性的版本描述。例如，©since version 1.7.10

- ##### @deprecated 文本：这个标记将对类、方法或变量添加一个不再使用的注释。文本中给出了取代的建议

- ##### @see 引用：这个标记将在“ see also” 部分增加一个超级链接。它可以用于类中，也可以用于方法中。



### 类设计的技巧

##### 1、一定要保证数据私有。

##### 2、一定要对数据初始化。

##### 3、不要在类中使用过多的基本类型：用其他的类代替多个相关的基本类型的使用。这样会使类更加易于理解且易于修改。

##### 4、不是所有的域都需要独立的域访问器和域更改器。

##### 5、将职责过多的类进行分解。

##### 6、类名和方法名要能够体现它们的职责。

##### 7、优先使用不可变的类。



## 第五章 继承



### 超类和子类

##### 1、在java中用关键字extends表示继承。同时在java中所有的继承都是公有继承。

##### 2、已存在的类称为超类、基类或父类；新类称为子类、派生类或孩子类。子类比超类拥有更多的功能。

##### 3、子类无法直接访问父类的私有域。

##### 4、子类可以通过super关键之来访问父类的共有接口（子类的某方法与父类重名时）

```java
public double getSalary(){
	double baseSalary = super.getSalary();
	return baseSalary + bonus;
}
```

##### 5、super和this引用的概念不同，super不是一个对象的引用，不能将super赋给另一个对象变量，它只是一个指示编译器调用父类方法的特殊关键字。

##### 6、可以通过super()调用父类的构造方法 ，使用super调用构造器的语句必须是子类构造器的第一条语句。

```java
public Manager(String name, double salary, int year, int month, int day){
	super(name, salary, year , month, day) ;
	bonus = 0;
}
```

##### 7、一个对象变量可以指示多种实际类型的现象被称为多态。在运行的时候能自动地选择调用哪个方法的现象称为动态绑定。

##### 8、当e 引用Employee 对象时， e.getSalary( ) 调用的是Employee 类中的getSalary 方法；当e 引用Manager 对象时，e.getSalary( ) 调用的是Manager 类中的getSalary 方法。虚拟机知道e 实际引用的对象类型，因此能够正确地调用相应的方法。

##### 9、方法的调用：假设要调用x.f(args)，隐式参数x声明为类C的一个对象。

1. ##### 编译器查看对象的声明类型和方法名。编译器列举所有C类中名为f的方法和其超类中访问属性为public且名为f的方法。

2. ##### 编译器查看调用方法是提供的参数类型，如果在所有名为f的方法中存在一个与提供的参数类型完全匹配，就选择这个方法。这个过程被称为重载解析。

##### 10、 Java不支持多继承。

##### 11、阻止继承：final类和方法

- ##### 不允许被继承的类被称为final类，如果在定义类的时候使用了final修饰符就表明这个类是final类。

- ##### 在类中的特定方法也可以被声明为final，这样子类就不能重写这个类（final类中的所有方法自动地成为final方法但不包括域）。

##### 12、通过关键字instanceof操作符可以判断对象是否为一个特定类的实例。

```java
/**
* 只能在继承层次内进行类型转换。
* 在将父类转换成子类之前，应该使用instanceof进行检查。
* 在一般情况下，应该尽量少用类型转换和instanceof运算符。
*/
if(staff[1] instanceof Manager){
    boss = (Manager) staff[1];
}
```

##### 13、抽象类：关键字abstract声明，除了抽象方法之外， 抽象类还可以包含具体数据和具体方法

```java
public abstract class Person{
    private String name;
    public Person(String name){
        this.name = name;
    }
    public abstract String getDescription();
    public String  getName(){
        return name;
    }
}
```

##### 14、编译器只允许调用在类中声明的方法。

##### 15、子类不能访问父类的私有域，如果是protected，子类就可以访问父类的这个域。

##### 16、对于protected类型的域或方法，子类只能访问自己的对象中的protected的域，而对于父类的其他子类的protected的域无法访问。

##### 17、可见性：

- ##### private：仅对本类可见。

- ##### public：对所有类可见。

- ##### protected：对本包和所有子类可见。

- ##### 默认：对于本包可见。




### Object：所有类的父类

##### 1、Object类是所有类的始祖，没有明确指出父类的类的父类默认是Object类。

##### 2、在Object 中有几个只在处理线程时才会被调用的方法。

##### 3、在Java中除了基本类型不是对象，其他的都扩展了Object类。

##### 4、对象.getClass()得到的是某个具体的子类，而instanceof判断的是是否是某个类或者某个类的子类。

##### 5、java规范中要求equals方法具有自反性、对称性、传递性、一致性，对于任意非空引用x.equals(null)返回false。

##### 6、int hashCode()返回对象的散列码。

##### 7、static int hashCode(Object a) 如果a为null返回0，否则返回a.hashCode()。

##### 8、static int hash(Object . . . objects) 返回一个散列码，由提供的所有对象的散列码组合而得到。



### 泛型数组列表ArrayList

##### 1、类似于C++中的vector。

##### 2、add()将元素添加到列表中。

##### 3、ArrayList对象.size()将返回数组的列表中包含的实际元素数目。

##### 4、ArrayList的trimToSize()这个方法将存储区域的大小调整为当前元素数量所需要的存储空间数目。垃圾回收器将回收多余的存储空间。

##### 5、void ensureCapacity( int capacity)	确保数组列表在不重新分配存储空间的情况下就能够保存给定数量的元素。

##### 6、ArrayList并不是java程序设计语言的一部分，而是由人编写的放入到标准库的一个实用类。

##### 7、a.set(i,harry)	设置第i个元素。 //等价于a[i] = harry;

##### 8、add方法添加新元素，set方法只能用于修改已有的元素的值。

##### 9、get方法用于获取数组列表的元素。

##### 10、ArrayList可以转换为数组

```java
ArrayList<X> list = new ArrayList<>();
while (. . .){
	x = . . .;
	list.add(x);
}
X[] = new X[list.size()];
list.toArray(a);
```

##### 11、add方法还可以指定位置插入元素，比如a.add(10,e);所有位于10之后的元素自动向后移一个位置。

##### 12、删除一个元素Employee e = staff.remove(n);

##### 13、@SuppressWamings("unchecked") 标注来标记这个变量能够接受类型转换。

##### 14、鉴于兼容性的考虑， 编译器在对类型转换进行检査之后， 如果没有发现违反规则的现象， 就将所有的类型化数组列表转换成原始ArrayList 对象。在程序运行时， 所有的数组列表都是一样的， 即没有虚拟机中的类型参数。



### 对象包装器与自动装箱

##### 1、所有的基本类型都有一个与之对应的类，如Integer就对应int，这些类称之为包装器。

##### 2、ArrayList<Integer> 的效率远远低于int[ ]。

##### 3、list.add(3)  会自动变换成list.add(Integer.valueOf(3));		//这种变换被称为自动装箱。

##### 4、包装器还会自动拆箱	int n = list.get(i)会被编译器翻译成int n = list.get(i).intValue();

##### 5、如果在一个条件表达式中混合使用Integer 和Double 类型， Integer 值就会拆箱，提升为double, 再装箱为Double。

##### 6、装箱和拆箱是编译器认可的， 而不是虚拟机。编译器在生成类的字节码时， 插人必要的方法调用。虚拟机只是执行这些字节码。

##### 7、如果想编写一个修改数值参数值的方法， 就需要使用在org.omg.CORBA 包中定义的持有者（ holder ) 类型， 包括IntHolder、BooleanHolder 等。每个持有者类型都包含'一个公有（！）域值， 通过它可以访问存储在其中的值。

```java
import org.omg.CORBA.IntHolder;
public static void triple(IntHolder x){
	x.value = 3 * x.value;
}
```

##### 8、java中  “...”  表示这个方法可以接收任意数量的对象。

##### ​	Object...   	类似于		Object[];

##### ​	double...	也类似于		double[];

##### 9、static Enum Enum.valueOf(Class enum.Class, Stirng name);		//返回指定名字、给定类的枚举常量。

##### 10、String toString();		//返回枚举常量名。

##### 11、int ordinal();			//返回枚举变量在enum申明中的位置，位置从0开始计数。

##### 12、int compareTo(E other)	//如果枚举常量出现在other之前这返回一个负值，如果this == other则返回0,否则返回正值。



### 反射(P207回头再好好看)

##### 1、JAVA反射机制是在运行状态中，对于任意一个类，都能够知道这个类的所有属性和方法；对于任意一个对象，都能够调用它的任意方法和属性；这种动态获取信息以及动态调用对象方法的功能称为java语言的反射机制。



### 继承的设计技巧

##### 1、将公共操作和域放在超类。

##### 2、尽量少用protected类型的域。

##### 3、使用继承实现“is-a"的关系。

##### 4、除非所有继承的方法都有意义，否则不要使用继承。

##### 5、在覆盖方法时，不要改变预期的行为。

##### 6、使用多态，而非类型信息。

##### 7、不要过多的使用反射。



## 第六章 接口、lambda表达式与内部类



### 6.1接口

##### 1、接口的概念：接口是对类的一组需求描述。

##### 2、在接口中声明的所有的方法自动的属于public，因此在接口中声明方法时，不必提供关键字public。

##### 3、接口没有实例，Java SE 8之前，不能在接口中实现方法，现在可以了。

##### 4、将类声明为实现某个接口，需要使用关键字implements。

```java
class Employee implements Comparable<Employee>{
    public int compareTo(Employee other){
        return Double.compare(salary, other.salary);
    }
}
```

##### 5、接口不是类，不能使用new运算符实例化一个接口，但是可以声明接口的变量，接口变量必须引用实现接口的类的对象。

##### 6、可以用instanceof检查一个对象是否实现了某个特定的接口。

```java
if(anObject instaceof Comparable){
    ...
}
```

##### 7、在接口中域将被自动设为public static final。

##### 8、一个类可以实现多个接口。

##### 		比如 class Employee  impalements Cloneable,  Comparable;

##### 9、 接口的存在其实是为了实现多继承，接口是抽象的规范。

##### 10、可以为接口方法提供一个默认实现。但是必须用default修饰符标记这样的一个方法。

##### 11、定义为default的方法在实现接口的时候可以忽略不管它，因为有默认方法了。

##### 12、解决默认方法冲突的方式。如果在一个接口中将一个方法定义为默认方法，然后又在超类或者另一个接口中定义了同样的方法，怎么处理

1. ##### 超类优先，如果超类提供一个具体方法，同名且有相同参数类型的默认方法会被忽略。

2. ##### 接口冲突，如果一个超接口提供了一个默认方法， 另一个接口提供了一个同名而且参数类型（不论是否是默认参数）相同的方法， 必须覆盖这个方法来解决冲突。

3. #####  如果一个类同时实现两个接口，Java会报错让程序员来解决这个二义性。

   ```java
   interface Named{
       default String getName(){
           return getClass().getName() + "_" + hashCode();
       }
   }
   class Student implements Person,Named{
       public String getName(){
           return Person.super.getName();		//程序员自己选择继承那个类的方法。
       }
   }	
   ```




### 6.2 对象克隆  Cloneable接口

##### 1、由于java中的变量中存储的其实是一个对象的引用变量，如果直接简单赋值，原变量和副本都是同一个对象的引用。如果希望得到一个初始状态相同的新的变量而不是复制引用的话可以使用clone方法。

```java
Employee original = new Employee("John Public", 50000);
Employee copy = original;			//这个只是简单的复制引用。

Employee copy = original.clone();	//创建了一个新的对象。
```

![1523501663042](C:\Users\Ninaye\AppData\Local\Temp\1523501663042.png)

##### 2、默认的clone方法是“浅拷贝“，也就是说不会拷贝对象中引用的其他对象，还是会有一些数据共享。

![1523502098723](C:\Users\Ninaye\AppData\Local\Temp\1523502098723.png)

##### 由于通常子对象是可变的，必须重新定义clone方法来建立一个深拷贝，同时克隆所有子对象。

##### 3、对于每一个类需要确定：

1. ##### 默认的clone方法是否满足要求。

2. ##### 是否可以在可变的子对象上调用clone来修补默认的clone方法。

3. ##### 是否不该使用clone。

4. ##### 如果选择1或2选项，则必须实现Cloneable接口，和重新定义clone方法，并指定public访问修饰符。

##### 4、子类只能调用受保护的clone方法来克隆它自己的对象。必须重新定义clone 为public 才能允许所有方法克隆对象。

##### 5、标记接口的用途是确保一个类实现了一个或一组特定的方法，标记接口不包含任何方法，唯一的作用就是允许在类型查询中使用instanceof。

##### 6、深拷贝的一个例子：

```java
class Employee implements Cloneable{
    ...
    public Employee clone() throw CloneNotSupportedException{//为了防止对象的类没有实现Cloneable接口，Object类的clone方法就会抛出异常。
    	// call Object.clone()
        Employee cloned = (Employee) super.clone();
        // clone mutable fields
        cloned.hireDay = (Date) hireDay.clone();
        return cloned;
    }
}
```

##### 7、所有数组类型都有一个public的clone方法，可以用这个方法建立一个新数组，包含原数组所有元素的副本。



### 6.3 lambda 表达式

##### 1、lambda 表达式就是一个代码块。

##### 2、如果lambda表达式只在某些分支返回一个值，而在另外一些分支不返回值，这是不合法的。

##### 3、lambda表达式形式： 参数，箭头（->）以及一个表达式

```java
(String first, String second) -> {
    if(first.length() < second.length())
   		return -1;
   	else if(first.length() > second.length())
   		return 1;
   	else
   		return 0;
}
```

##### 4、即使lambda表达式没有参数，仍然要提供空括号，就像无参数的方法一样：

```java
() -> {
    for(int i = 100; i >= 0; i--) 
        System.out.println(i);
}
```

##### 5、Java SE 8中接口可以声明非抽象方法。

##### 6、在Java中，lambda表达式所能做的也只是能转换为函数式接口。

##### 7、lambda表达式不是在任意场合都能适用的，它需要有 对应的函数式接口。


