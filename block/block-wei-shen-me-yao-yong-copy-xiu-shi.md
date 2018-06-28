# Block为什么要用Copy修饰

1.使用非ARC的时候，如果block里有外部变量，会保存在栈上（\_NSConcreteStackBlock）。当超出了作用域后就会被回收，在后面使用就会Crash。retain/release函数在\_NSConcreteStackBlock这个类的定义中，不会对指针做任何操作。如果要长期持有block对象就需要使用copy将block移到堆上\(\_NSConcreteMallocBlock\)。

2.使用ARC的时候，无论使用copy还是strong都会讲block移到堆上。使用copy只是习惯问题。

[http://www.cnblogs.com/biosli/archive/2013/05/29/iOS\_Objective-C\_Block.html](http://www.cnblogs.com/biosli/archive/2013/05/29/iOS_Objective-C_Block.html)



