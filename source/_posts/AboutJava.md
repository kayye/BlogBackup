---
title: AboutJava
date: 2017-09-06 15:29:41
categories: Java
keywords: 知识点
tags: 知识点
---

+ 关键字
![](/assets/blogImg/AboutJava/keyword.jpg)

## switch语句
+ 主体
```
switch(表达式){
  case 常量值 1：
        代码块1;
        break;
  case 常量值2:
        代码块2;
        break;
  ...
  default:
        当以上常量值均不是时，执行本代码（可有可无）
}
```
<!--more-->

例子
```
Scanner scanner =new Scanner(System.in);
        System.out.println("输入一个五分制的数");
        int score = scanner.nextInt();
        switch(score){
            case 5:
                System.out.println("优秀");
                break;
            case 4:
                System.out.println("良好");
                break;
            case 3:
                System.out.println("及格");
                break;
            case 2: case1:
                System.out.println("不及格");
                break;
            default:
                System.out.println("输入的分数不是五分制");
        }
```

```
 Scanner scanner =new Scanner(System.in);
        System.out.println("输入分数的等级");
        char grade = scanner.next().charAt(0);
        switch(grade){
            case '优':
                System.out.println("5");
                break;
            case '良':
                System.out.println("4");
                break;
            case '中':
                System.out.println("3");
                break;
            case '差':
                System.out.println("2");
                break;
            default:
                System.out.println("输入的不是分数等级");
        }
```

## 循环语句
+ while循环
```
while(循环继续的条件表达式){
      循环体或称循环类容
}
```
![](/assets/blogImg/AboutJava/循环.jpg)



## 数组

+ 数组初始化分为两种
1.静态初始化 //在数组创建之初直接指定其内容
2.动态初始化 //所有内容不会具体指定，都是默认值

动态初始化声明一个数组
```
int 数组名 [] / int[] 数组名
int arrayDame [];//声明一个数组
int [] arrayDame;
arrayDame = new int [10];//为数组开辟存储空间
```

静态初始化声明一个数组
```
int arrayDame[] = {2,5,6,7,8,9,10};
int[] arrayDame = {2,5,6,7,8,9,10};
```


*没有空间的数组是不能用的

给数组每个空间输出一个值,并且打印出来
```
//给数组每个空间输入一个值
        for (int i = 0; i < arrayDame.length; i++){
            arrayDame[i] =  i*2+1;
        }

        //打印数组每个空间对应的值
        for(int i = 0; i<arrayDame.length; i++){
            System.out.println(arrayDame[i]);
        }
```

+ 数组的应用
比较一个数组中的最大值和最小值
```
 int[] arrayDemo = {43, 34, 5, 66, 12};
        int max,min;
        max = min = arrayDemo[0];
        for(int i=0;i<arrayDemo.length;i++){
            if(max>arrayDemo[i]){
                max =arrayDemo[i];
            }
            if(min<arrayDemo[i]){
                min =arrayDemo[i];
            }
        }
        System.out.println("最大值:"+max);
        System.out.println("最小值:"+min);
```
冒泡排序：泡沫排序或气泡排序）是一种简单的排序算法。 它重复地走访过要排序的数列，一次比较两个元素，如果他们的顺序错误就把他们交换过来。 走访数列的工作是重复地进行直到没有再需要交换，也就是说该数列已经排序完成。 这个算法的名字由来是因为越小的元素会经由交换慢慢“浮”到数列的顶端
```
int arrayDemo[] = {12,45,23,10,300};
       for (int i =0;i<arrayDemo.length-1;i++){
           for(int j=i+1;j<arrayDemo.length;j++) {
               if (arrayDemo[i]<arrayDemo[j]) {
                   int temp = arrayDemo[i];
                   arrayDemo[i] = arrayDemo[j];
                   arrayDemo[j] = temp;
               }
           }
           //每次排序的详细过程
           System.out.print("第"+(i+1)+"排序:");
           for(int j =0;j<arrayDemo.length;j++){
                System.out.print(" "+arrayDemo[j]);
           }
           System.out.println(" ");

       }
       for (int i=0;i<arrayDemo.length;i++){
           System.out.println(arrayDemo[i]);
       }
```
![排序的步骤过程](/assets/blogImg/AboutJava/冒泡排序过程.png)

+ 二维数组
动态初始化声明一个数组
```
int 数组名 [][] / int[][] 数组名
int arrayDame [][];//声明一个数组
int [][] arrayDame;
arrayDame = new int [10][10];//为数组开辟存储空间
```

静态初始化声明一个数组
```
int arrayDemo[][] ={{1,2},{5,6},{3,4}};
int[][] arrayDame = {{1,2},{5,6},{3,4,5}};
```
打印二维数组
```
int arrayDemo [][] ;
       arrayDemo = new int[10][10];
        for (int i=0;i<arrayDemo.length;i++){
            for (int j=0;j<arrayDemo[i].length;j++){
                System.out.print(arrayDemo[i][j]);
            }
            System.out.println();
        }
```

## 方法

+ 方法
 一半情况下方法的语法问<br>
 ```
 modifier returnValueType methodName(list of parameters) {
  // Method body;
}
 ```
 ![](/assets/blogImg/AboutJava/方法的模型.png)
 <br>
    +  修飾符:修飾符是可選的，告訴編譯器如何調用該方法。這定義了該方法的  訪|問類型。
 
    + 返回類型: 方法可以返回一個值。returnValueType的值是方法返回的數據類型。有些方法冇有返回值執行所需的操作。在這種情況下，returnValueType是關鍵字void.

    + 方法名稱: 這是方法的實際名稱。方法名和參數列表一起構成了方法簽名.

    + 參數: 參數像一個占位符. 當調用一個方法，傳遞一個值給參數. 這個值被稱為實際參數或參數. 參數列表是指類型，順序和方法的參數的個數. 參數是可選的，也就是說，一個方法可以包含任何參數.

    + 方法體: 方法體包含定義哪些方法語句的集合.
>方法的返回值类型，void类型是不需要返回值的，全部的类型都需要返回值
<br>
  + 方法的调用
  创建一个方法，是做什么的定义，若要使用方法，必须调用它。有两种方法来调用一个方法，该选择是基于方法是否返回一个值或木有。
    - 该方法有返回值的，调用该方法通常被视为一个值
    ```
    int larger = max(30, 40);
    ```
    
    例子：
  ```
  public class text {
    public static void main(String args[]) {
        int i = 5;
        int j = 7;
        int k = max(i,j);
        System.out.println("The maximum between " + i +
                    " and " + j + " is " + k);
    }
  public static int max(int i ,int j) {
      int result = 0;
      if (i < j)
          result = j;

      if (i > j)
          result = i;

      return result;
    }
  ```
    
    - 该方法返回void，则调用该方法是一个语句
    ```
    System.out.println("Welcome to Java!");
    ```
    
    例子
    ```
    public static void main(String[] args) {
      printGrade(78.5);
   }

   public static void printGrade(double score) {
      if (score >= 90.0) {
         System.out.println('A');
      }
      else if (score >= 80.0) {
         System.out.println('B');
      }
      else if (score >= 70.0) {
         System.out.println('C');
      }
      else if (score >= 60.0) {
         System.out.println('D');
      }
      else {
         System.out.println('F');
      }
   }
    ```
>在這裡，printGrade方法是一個void方法。它不返回任何值。調用一個void方法必須是一個語句。因此，它被調用在第3行中的main方法的聲明。此語句像分號結尾的Java語句。
  

  + 方法的重载
    定义：方法名称相同，但是参数的类型和个数不同，通过传递参数的个数和类型不同来完成不同的功能。
```
public static void tell(int i,int o){
        System.out.println(i+o);
    }
    public static void tell(int i,int o,int j){
        System.out.println(i+o+j);
    }
```

## 类和对象
+ 类的定义 
```
class{
    属性
    方法
}
```
>
声明一个类一定要有关键字class，类名的首字母要大写
<

+ 类与对象的关系
定义：类是对某一类事物的描述，是抽象的、概念上的意义，对象是实际存在的该类事物的每一个个体，也称为对象或实例

内存的划分：
![](/assets/blogImg/AboutJava/内存的划分.png)

用法：
```
//创建一个类
class Person{
    String name;
    int age;
    public void tell(){
        System.out.println("姓名"+name+" "+"年龄"+age);
    }
}
public class text {
    public static void main(String args[]) {
        //创建对象
        //赋值
        //对象.属性
        //对象.方法
        Person per = null;   //声明
        per =new Person;     //实例化操作
        Person per =new Person();//声明并实例化
        per.age = 30;
        per.name = "张三";
        per.tell();
```

+ 对象
 - 创建对象；
 基本上一个对象是从一个类创建的。在java中，关键字new用于创建心的对象
 从类创建对象时有三个步骤：
    + 声明：变量声明，一个变量名的对象类型
    + 实例：“new”关键字用来创建对象
    + 初始化：关键字“new”后跟调用一个构造函数，用这个调用初始化对象

+ 異常處理
  - 捕获异常
    一种捕获的方法是使用try/catch关键字的组合异常。try/cath块放在围绕之中，可能产生异常的代码。try/catch块中的代码被称为受保护的代码，以及语法使用try/catch语句如下：
    ```
    try
{
   //Protected code
}catch(ExceptionName e1)
{
   //Catch block
}
    ```
    catch语句涉及声明异常的正在视图捕捉类型。吐过受保护的代码发生异常，catch块后面的试一下检查。如果发生异常的类型列在catch块，异常被传递到catch块多作为一个参数被传递到方法参数。

   - 例子
   下面一个数组并有两个元素声明。然后代码视图访问它抛出一个异常数组的第三个元素。
   ```
   // File Name : ExcepTest.java
import java.io.*;
public class ExcepTest{

   public static void main(String args[]){
      try{
         int a[] = new int[2];
         System.out.println("Access element three :" + a[3]);
      }catch(ArrayIndexOutOfBoundsException e){
         System.out.println("Exception thrown  :" + e);
      }
      System.out.println("Out of the block");
   }
}
   ```
    
    - 多个catch快
    一个try块后面可以跟多个catch快。多个catch代码语法如下所示：
    
    ```
    try
{
   //Protected code
}catch(ExceptionType1 e1)
{
   //Catch block
}catch(ExceptionType2 e2)
{
   //Catch block
}catch(ExceptionType3 e3)
{
   //Catch block
}
    ```
    前面的语句演示3个catch块，但可以有任意数量的其中的一个try后。如果受保护的代码发生异常，该异常被抛出到列表中的第一个catch块。如果抛出的异常的数据类型相匹配ExceptionType1，他就会被捕获不那里，如果不是，则该异常传递到第二catch语句，这中情况持续下去，知道异常要么被捕获或下落通过全部捕获，在这种情况下，目前的方法停止执行并抛出异常下落到以前的方法调用堆栈

##  继承
 - IS-A关系
  IS-A（是一个）是一种表达：这个对象是一个类型的对象
  ```
public class Animal{
}

public class Mammal extends Animal{
}

public class Reptile extends Animal{
}

public class Dog extends Mammal{
}    
public class Animal{

}

  ```
   根据上面的语法，满足一下条件
    + 动物是哺乳动物类的父类
    + 动物是爬行类的父类
    + 哺乳动物和爬行动物是动物类的子类
    + 狗是哺乳动物双方的动物类的子类
   考虑到IS-A的关系。可以说
    + 哺乳动物IS-A动物
    + 爬行动物IS-A的动物
    + 狗IS-A哺乳动物
    + 因此:狗IS-A动物
   使用extends关键字的子类就可以除父类的私有属性，它继承父类的所有属
 - instanceof 关键字:
     用instanceof检测子类是否与父类相关
 - HAS-A关系:
    這些關係主要是基於使用。這就決定了某一類是否 HAS-A 某一個東西。這種關係有助於​​減少重複代碼，以及錯誤。
   ```
   public class Vehicle{}
public class Speed{}
public class Van extends Vehicle{
  private Speed sp;
}  
   ```
     这表明，Van类 HAS-A
     Speed类，通过让飞车一个单独的类，我们不必把属于加速Van类中的全部代码。这使他可以重复使用Speed类在多个应用程序。
  
  + 覆盖与重载
  重载好处是：定义一个行为是特定于该子类的类型表示一个子类可以实现根据它要求一个父类的方法的能力

    + 规则方法重载：
      - 参数列表应该是完全一样被覆盖的方法
      - 返回类型应相同或父类中的原重写方法声明的返回类型的子类型
      - 访问级别不能比被重写的方法的访问级别更严格。例如：如果父类方法声明为public，在子类中重写的方法不能是private或protected
      - 实例方法可以被覆盖，仅有上他们是由子类继承
      - 方法声明为finally不能被重写
      - 方法声明为静态的不能被覆盖，但可以重新声明
      - 如果一个方法不能被继承，那么它不能被重写
      - 作为实例的父类在容一个包内的子类可以重写未声明为四友的或最终的任何父类方法
      - 在不同的包中的子类只能重写非finally方法声明为public或protected
      - 重写方法可以抛出任何异常取消勾选，无论重写的方法是否抛出异常与否，但压倒一切的方法不应该抛出checked exceptions新的或不是由重写的方法声明的那些更广泛。重写方法可以抛出比重写的方法较窄或更少的例外。
      - 构造函数不能被重写
    + 使用super关键字：
     当调用一个重载方法的类型版本，那么需要使用super关键字
    ```
    class Animal{

   public void move(){
      System.out.println("Animals can move");
   }
}

class Dog extends Animal{

   public void move(){
      super.move(); // invokes the super class method
      System.out.println("Dogs can walk and run");
   }
}

public class TestDog{

   public static void main(String args[]){

      Animal b = new Dog(); // Animal reference but Dog object
      b.move(); //Runs the method in Dog class

   }
}
    ```
    将产生以下结果：
    ```
    Animals can move
Dogs can walk and run
    ```

~~删除线~~
[引用网址](http://tw.gitbook.net/java)