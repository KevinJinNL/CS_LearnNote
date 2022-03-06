# Java特性学习

# 一、类和对象

------

​	java作为一门面向对象的程序设计语言，在java中所有的东西都会属于某个类（class），你会建立的是源文件（扩展名为.java），然后将它编译成新的文件（扩展名为.class），实际上真正执行的是类class

```java
//一个狗的示例类
class dog{
    int age;
    String name;
    //数据成员
    public void eat()
    {
        System.out.print("小狗吃东西")；
    }
    //抽象行为
    public void Needfood(int food)
    {
        System.out.print("小狗要吃"+food+"克狗食")；
    }
    //成员方法
}
```

​	在上面的小狗类示例中，可以发现一个类有几种基本元素

- 数据成员(Data)
- 抽象行为(Abstract Behavior)
- 成员方法(Method)

## 对象的继承(Inheritance)

​	首先我们想象这么一个场景，两位programmer接到了相同的任务，要求在图形接口画出四方形，圆形与三角形，当用户点选图形时，图形需要顺时针转动360°并依据形状的不同播放不同音频文件，我们分别称呼两位programmer为一号和二号

------

一号的设计思路是这样的，写出旋转以及播放音频函数：

```java
rotate(shapeNum)
{
    //旋转360°
}//旋转函数
playsound(shapeNum)
{
    //播放对应音频文件
}//音频播放函数
```

而二号的设计思路是将需求的三个类都写出来并且每一个类都对其旋转和音频播放函数进行定义

```java
class Square{//正方形
    rotate(){
        //旋转函数
    }
    playsound(){
        //音频播放函数
    }
}

class Circle(){//圆形
    rotate(){
        //旋转函数
    }
    playsound(){
        //音频播放函数
    }
}

class Triangle(){//三角形
	rotate(){
        //旋转函数
    }
    playsound(){
        //音频播放函数
    }
}
```

​	综上可以看出，一号的代码量要少很多，但是可读性以及后期针对不同需求的时候需要修改，比如我们增加一个阿米巴虫形状，一号的程序代码就需要针对阿米巴虫形状进行专门的修改,以至于后期如果增加更多的类和不同情况下的需求，需要在playsound函数中增加大量的分支语句，无论是读起来还是理解起来都非常吃力(如果还不是自己写的)

```java
playsound(shapeNum){
	//如果不是阿米巴虫形状
		//查询使用哪个音频文件
		//播放
	//不然
		//播放阿米巴虫对应的音频文件
}
```

​	而二号在可读性以及后期的修改上就要轻松很多，但是代码量要多得多，而且真正修改起来还得寻找相应的对象，也是非常麻烦，只要有新的需求就需要重新写入一个类

​	由此在这种情况下我们就可以用到java中继承(inheritance)的特性，利用**extends**关键字，创建最顶层的类shape类,shape类具有包括正方形长方形三角形等几何图形所具有的共同特征以及特性

```java
class shape{
    double area;//面积
    String name;//图形名称
    
    void rotate()
    {
        //图形旋转
    }
    void playsound()
    {
        //播放音频文件
    }
}
```

​	上面我们定义了顶层的图形类shape，在定义其他图形时可以直接继承shape类的各种数据成员以及方法，例如直接让三角形继承shape类

```java
class Triangle extends shape{
    //此处我们可以直接对shape中已有的方法进行重写override
    
    void rotate(){
        //三角形旋转的具体实现
    }
    void playsound(){
        //三角形旋转时播放的音频文件
    }
}
```

### 重载(Override)

​	如果想要继承的对象其中的某一个方法不按主类的具体方法实现，可以采取对方法进行重载的方式，只需要在子类中定义具体的实现方法即可

## 控制对象

------

- 事实上并没有对象变量这样的东西存在

- 只有引用(reference)到对象的变量

- 对象引用变量保存的是存取对象的方法

  ------

  对象的声明、创建与赋值有3个步骤：

```java
//以Dog类为例
Dog mydog=new Dog();
```

​	在其背后的具体实现细节分为三步：

一、声明一个引用变量

​	**Dog myDog**=new Dog();

​	要求Java虚拟机分配空间给引用变量，并将此变量命名为myDog，此引用变量将永远被固定为Dog类型，换句话说，它是个控制Dog的遥控器

二、创建对象

​	Dog myDog=**new Dog()**;

​	要求Java虚拟机分配堆空间给新建立的Dog对象

三、连接对象和引用

​	Dog myDog**=**new Dog();

​	将新的Dog赋值给myDog这个引用变量

## 对象中的变量

------

​	在Java对象中，有实例变量和局部变量两种变量，实例变量时声明在类中，而局部变量是声明在方法中的

实例变量声明在类中：

```java
class Horse{
    private double height=15.2;
    private String breed;
   	//more code......
}
```

局部变量声明在方法中且局部变量没有默认值，如果在变量被初始前就被使用的话，编译器就会显示错误

```java
class Foo{
    public void go()
    {
        int x;
        int z=x+3;//无法编译，x并未初始化
    }
}
```

## 对象的比较

------

​	在Java中，运算符“==”可以用于比较两个引用是否指向同一对象

```java
Foo a=new Foo();
Foo b=new Foo();
Foo c=a;
a==b;//false
a==c;//true
b==c;//false
```

# 二、使用函数库(Java API)

------

