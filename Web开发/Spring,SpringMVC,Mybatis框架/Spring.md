# Spring

Spring主要有两个功能,IOC和AOP

解决的问题是:项目系统的核心意义在于业务,与业务无关的部分应当分离

## Spring IOC解决的问题

* 组件依赖关系异常复杂,系统初始化非常麻烦,各组件初始化和装配顺序,接口匹配难以管理
* 各组件生命周期难以管理
* 直接new进行的依赖管理太难以测试

解决方案:使用一个类(容器)从外部读取描述系统如何组装的配置文件或读取注解,然后运行时动态生成对象(利用反射),并按需拼装系统中的各种对象

## Spring AOP解决的问题

方法执行中包含太多业务无关的代码,日志记录,开启,关闭事物等等

解决方案:允许在方法执行前,执行后,返回后,异常后执行一些操作,把那些业务无关的操作移到一个称作Aspect的类中,然后由AOP框架按配置文件或注解中的配置把对应操作的调用放到对应的位置
```java
try{
    try{
        //@Before
        method.invoke(..);
    }finally{
        //@After
    }
    //@AfterReturning
}catch(){
    //@AfterThrowing
}
```