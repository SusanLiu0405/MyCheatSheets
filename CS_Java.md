## Kinds of questions to expect: 

**» Explain object-oriented concepts and terminologies** 

***concept: what is static variable? difference between static variables & instance variables?***

***Answer:***

Static variable------variables that can be shared by all objects of a class (aka class variables), looks like:

```java
class City{
    static int count;
}
```

Instance variable------variables that belong to an object, looks like:

```java
class City{
    int count;
}
```

difference: each object has one copy of its instance variables. They are not shared with other objects with the same class type. 

***concept: what's the meaning of inheritance? show an example.***

***Answer:***

Inheritance means, your current class is a sub class, and you are inherited from a super class, like:

```java
public class Person{
    private String name;
    public Person(){
        …
    }
    …
}
//Note: Student is the sub class and Person is the super class
public class Student extends Person{
    private int studentName;
    public Student(){
        super();
    	…
    }
    …
}
```

**1 byte=8 bits**

Java程序运行的步骤是：source code/JVM/Complier/Memory...

**Variable**

variable要素：value stored in particular location & variable has a name/ hold only one value/ when running, value may change

variable命名要素: 

1.start with letter or underscore 必须字母或下划线开头

2.only letter/digit/underscore 只能含有字母 数字 下划线

3.case sensitive 区分大小写

variable type: int/double/boolean/char

注意区别：char只能储存单个字符或者标志，而String是字符串，且String是一个类

**Scanner**(本质上是一个类)

Scanner的使用方法：

```java
#declare and initialize Scanner object
Scanner input = new Scanner(System.in); 

#read in an integer:
int variable;	#注意这里的variable不需要赋初值
variable=input.nextInt();
```



**» Explain a program or part of a program** 

***Exercise: show the output***

```java
System.out.println(Integer.parseInt("13"));
System.out.println(Integer.parseInt("23",10));
System.out.println(Integer.parseInt("33",16));
```

line1: output=13

parseInt(string, radix):解析一个字符串并且返回指定基数(radix)的十进制整数。

例如：

parseInt("33",16) 返回的值是51，也就是把十六进制的33转化为十进制

**» while, do-while, and for loops** 

while loop的长相: 需要先判断条件是否满足，再执行循环体。

```java
while(需要满足的条件){
	循环体;
}

int i=1;
int sum=0;
while(i<=100){
    sum=sum+i;
    i++;
}
```

do-while的长相: 需要先执行循环体，再判断条件是否满足。

```java
do{
    循环体;
}while(需要满足的条件);

int i=1;
int sum=0;
do{
    sum=sum+i;
    i++;
}while();
```





**» Methods** 

分为predefined methods 和programmer-defined methods

predefined：用math的时候记得写：

```java
import java.math.*;
```

常见函数：

Math.pow(底数,指数)求幂

Math.log(N)是计算e为底N为真数的对数。（用除法解决底数不为10不为e）

Math.log10(N)是计算10为底N为真数的对数。

Math.abs(数字)求绝对值

Math.sqrt(数字)开方

Math.round(number*10^n)/10^n.0 四舍五入到小数点后，保留n位小数

**» Array and ArrayList** 

```java
定义Array：
int[] vals=new int[5];
定义ArrayList from现有array：
String[] array1 = new String[list.size()];
list.toArray(array1);
//使用参数
public static void addOne(int[] a){
    ...
}
定义ArrayList:import java.util.ArrayList
ArrayList 类是一个可以动态修改的数组，与普通数组的区别就是它是没有固定大小的限制，我们可以添加或删除元素。
public class RunoobTest {
    public static void main(String[] args) {
        ArrayList<String> sites = new ArrayList<String>();
        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
        sites.add("Weibo");
        System.out.println(sites);
    }
}
```



**» File I/O and exceptions**

File Input:

```java
import java.io.*;
impoort java.util.Scanner;
//new a file
File f = new File("test.txt");
Scanner fin = new Scanner(f);
//OR:
Scanner fin = new Scanner(new File("test.txt"));
```

File Input, Output and Exceptions:

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.io.PrintWriter;
import java.util.Scanner;
public class ClassExamples {
    public static void main(String[] args) {
        try (
            Scanner fin = new Scanner(new File("jediCode.txt"));
            PrintWriter fout = new PrintWriter(new File("lineCounts.txt"));
        ) {
            while (fin.hasNextLine()) {
                String nextLine = fin.nextLine();
                System.out.println(nextLine.length());
                fout.println(nextLine.length());
            }
        }
        catch (FileNotFoundException ex) {
            System.out.println("File not found!");
            System.exit(0);
        }
    }
}
```

**» Classes and Objects(Def.)** 

Difference: Object is an instance of class.

**Constructor:**

class定义的时候可以没有constructor，但是：

若有参的constructor一个都没有，那么无参无body的constructor，写不写，它都实际存在；若有参的constructor存在，那么无参constructor自动消失

"this" keyword: refer to object itself; use: invoke another constructor of the same class

**» Inheritance and Polymorphism**

Polymorphism means that a variable of a supertype  can refer to a subtype object.

Inheritance: when different classes have in common, avoid redundancy

连接几个分离的char：

```java
public static int parseInt(char[] numbers) {
	int i=0;
	int result=0;
	for(i=0;i<numbers.length;i++) {
		if(Character.isDigit(numbers[i])) {
			int num=(int)numbers[i]-(int)('0');
			result=result*10+num;
		}
	}
	return result;
}
public static int parseInt(String s) {
	int a=Integer.valueOf(s).intValue();
	return a;
}
```



Run JavaFX Configurations:

```
--module-path "C:\Users\Susan\Documents\javafx-sdk-19\lib" --add-modules javafx.controls,javafx.fxml
```

TF Q5:

```
Polymorphism means that a variable of supertype can refer to a subtype object.
(This sentence should replace polymorphism with inheritance and it will be correct.)
```



TF Q7:

```
String buffer has no size limitation. You can add at the tail whenever you want.
```

