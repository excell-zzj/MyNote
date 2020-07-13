# Const int *ptr和int *const ptr

---

本身`const int`和`int const`没有区别，但是如果后面是指针，那么久有区别了。看代码：

~~~c++
int i = 1;
int j = 2;
const int ii = 3;

const int *ptr = &i;		//表示ptr指向i，不可以通过*ptr修改的值，但是可以修改ptr指向别的
*ptr = j;								//这样不行
ptr = &j;								//这样可以

int *const ptr2 = &i;		//表示ptr2只能指向i，能通过ptr对i进行修改，但是不能指向别的
*ptr2 = j;							//可以
ptr2 = &j;							//不行

~~~

**用顶层const表示指针本身是常量不可改变**

**用底层const表示指针指向的对象是常量**



对于赋值来说，顶层的const无所谓，底层的const不行,拷入和拷出的数据要具有相同的底层const属性

~~~c++
const int *p2 = &ci;
const int *const p3 = p2;				//p3是顶层和底层的结合
int *p = p3;										//错误，因为*p是普通的，而p3包含底层属性
p2 = p3;												//正确，都有底层const属性
~~~

`constexpr`表示将后面的东西强制表示为常量

~~~c++
constexpr int *q = nullptr		//q本身是一个指向整数的常量
const int *p = nullptr				//p指向常量，但本身不是常量
~~~



