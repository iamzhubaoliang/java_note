## 1.分析一种情况

![Screenshot_20200926_204014](picture\Screenshot_20200926_204014.png)

报的错误是：java.lang.NulpointerException 类型转换异常



![Screenshot_20200926_204533](picture\Screenshot_20200926_204533.png)



程序员的一个好习惯是：

任何时候，任何地点，对类型向下转型的时候，一定要使用instanceof运算符进行判断（java规范中要求的），这样可以避免：calssCastException

![Screenshot_20200926_205014](picture\Screenshot_20200926_205014.png)

instanceof 使用是一个好习惯

![image-20200927100517620](picture\image-20200927100517620.png)

这样写会出现问题，因为你不知道a是个cat还是dog所以用instaceof判断一下





