1.volatile

​	**volatile 关键字是一种类型修饰符**，用它声明的类型变量表示可以被某些编译器未知的因素更改。volatile 提醒编译器它后面所定义的变量随时都有可能改变，因此编译后的程序每次需要存储或读取这个变量的时候，都会**直接从变量地址中读取数据**。如 果没有 volatile 关键字，则编译器可能优化读取和存储，可能暂时使用寄存器中的值，如果这个变量由别的程序更新了的话，将出现不一致的现象。所以**遇到这个关键字声明的变量，编译器对访问该变量的代码就不再进行优化，从而可以提供对特殊地址的稳定访问**。 

​	让我们举几个volatile的例子

> 1）并行设备的硬件寄存器（如：状态寄存器）
> 2）一个中断服务子程序中会访问到的非自动变量（Non-automatic variables)
> 3）多线程应用中被几个任务共享的变量

2.const

1. 定义变量（局部变量或全局变量）为常量 。

2. 修饰函数的参数，表示在函数体内不能修改这个参数的值。

3. 修饰函数的返回值。 

   a.如果给用 const修饰**返回值的类型为指针**，那么函数返回值（即指针）的内容是不能被修改的， 

   而且这个返回值只能赋给被 const修饰的指针。

   b.如果用 const修饰**普通的返回值**，如返回int变量，由于这个返回值是一个临时变量，在函数调用 

   结束后这个临时变量的生命周期也就结束了，因此把这些返回值修饰为 const是没有意义的

4. 节省空间，避免不必要的内存分配 。

3.static

   1.在函数体，**只会被初始化一次**，一个被声明为静态的变量在这一函数被调用过程中维持其值不变。 

2. 在模块内（但在函数体外），一个被声明为静态的变量可以被模块内所用函数访问，但不能被模块 

外其它函数访问。它是一个**本地的全局变量**（只能被当前文件使用）。 

3. 在模块内，一个被声明为**静态的函数**只可被这一模块内的其它函数调用。那就是，这个函数被限制 

在声明它的模块的本地范围内使用（只能被当前文件使用）。

4.666