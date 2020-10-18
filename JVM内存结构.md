# 1.JVM结构 

![image-20200914154022567](picture\image-20200914154022567.png)

JVM首先从方法区中加载main方法。

# 2.方法执行时的内存变化

**局部变量只在方法体中有效，方法结束之后，局部变量的内存就释放了**

JVM三块主要内存：栈内存，堆内存，方法区内存

方法区中最先有数据：方法区中放代码的片段，存放class字节码文件

堆内存：后面讲

**栈内存：方法调用的时候，该方法需要的内存空间在栈中分配，方法不调用是不会在栈中分配空间的，方法只有在调用的时候才会在栈中分配空间，并且调用的时候是压栈。方法执行结束之后，该方法所以需要的空间就会释放，此时发生弹栈动作。（猜测这就是局部变量出了方法之后没有效的原因），当写上方法并没有调用的时候，只在方法区中占有空间。栈中存储的是运行过程中需要的内存空间以及栈中会存储方法的局部变量，先压栈的是main方法**

例子

```java
class HelloWorld{

    public static void main(String[] args){

       System.out.println("main begin");
       int x =100;
       int b=x;//这个是x中保存到的变量复制一份传递到b，所以x和b并不是一块相同的内存空间，是两个局部变量
       m1(x);
       System.out.println("main over");

        
    }

    public static void m1(int i){

        System.out.println("m1 begin");
        m2(i);
        System.out.println("m1 over");
    }

    public static void m2(int i){
        System.out.println("m2 begin");
        m3(i);
        System.out.println("m2 over");
    }
    public static void m3(int i){
        System.out.println("m3 begin");
        System.out.println(i);
        System.out.println("m3 over");
    }

}

class Myclass{

    public static void dayin() {
        System.out.println("MyClass");

    }

}
```

![image-20200914162950305](picture\image-20200914162950305.png)

执行顺序在上边用数字标出了