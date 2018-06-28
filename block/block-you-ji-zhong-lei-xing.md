# Block有几种类型

Block 常见的类型有三种，分别是 `_NSConcreteStackBlock` `_NSConcreteMallocBlock` `_NSConcreteGlobalBlock` 。

 另外还包括只在GC环境下使用的 `_NSConcreteFinalizingBlock` `_NSConcreteAutoBlock` `_NSConcreteWeakBlockVariable`。

`_NSConcreteGlobalBlock` 全局的静态 block，不会访问任何外部变量。

`_NSConcreteStackBlock` 保存在栈中的 block，当函数返回时会被销毁。

`_NSConcreteMallocBlock` 保存在堆中的 block，当引用计数为 0 时会被销毁。

