## C++ 空类

C++ 空类中包含 6 个默认函数

```c++
class Empty
{
};
```

一个空的 class 在 C++ 编译器处理过后就不再为空，编译器会自动地为我们声明一些 member function。

```c++
class Empty
{
public:
    Empty();  // 默认构造函数
    Empty(const Empty&);  // 拷贝构造函数
    ~Empty();     // 析构函数
    Empty& operator=(const Empty&);   // 赋值运算符
    Empty* operator&();   // 取址运算符
    const Empty* operator&() const;   // 取址运算符 const
};
```

如果只是声明一个空类，不做任何事情的话，编译器会自动为你生成一个默认构造函数、一个拷贝默认构造函数、一个默认拷贝赋值操作符和一个默认析构函数。

### 默认函数的默认操作

默认构造函数：调用所有成员变量的默认构造函数，基本类型（int等）的默认构造函数是赋0
拷贝构造函数：调用所有成员变量的拷贝构造函数
析构函数：啥也不干
赋值运算符：调用所有成员变量的赋值运算符
取址运算符:return this;
取址运算符 const:return this;