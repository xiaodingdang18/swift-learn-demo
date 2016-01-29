# swift-demo

###类与结构
* 1.类与结构体初始化，实例化
* 2.结构体成员初始化（类没有）
* 3.结构体，数组，字典为数值类型，类是引用类型


###存储属性
* 1.结构体属性存储
* 2.懒惰存储
* 3.计算属性（set,get）
* 4.类属性语句（static,class声明变量或常量，静态变量，）


###方法
* 1.实例方法用.语法调用
* 2.每一个实例都有一个隐藏的self属性，可以给实例属性前面+self，和方法参数同名区分
* 3.数值类型结构的实例属性默认不能被它的实例方法修改，前面+multating关键词，（不适用常量实例）
* 4.类方法，类的类方法前+class关键词，数值结构的类方法前+static关键词


###下标方法
* 1.通过subscript定义一个或多个参数以及一个返回值。可以只读或读写，通过setter和getter


###继承
* 1.基类
* 2.子类
* 3.重写方法。override
* 4.重写属性，get set
* 5.重写观察者
* 6.不可重写 final关键词


###类的继承和初始化
* 1.类初始化时必须保证所有属性被赋予合理的值，直接赋值比放在构造函数要好
* 2.自定义初始化，可以写多个初始化函数，但是都必须保证所有属性被赋值
* 3.实参和形参，不要形参用_代替
* 4.可选类型 ？
* 5.静态属性只有在初始化完成之前可以修改，即init里面修改
* 6.类当所有属性都有默认值，并且是基类，则系统会创建默认构造器
* 7.结构体即使属性没有被赋值也会生成默认构造器
* 8.类的继承和初始化
* 9.构造器的继承和重写
* 10.构造器的自动继承
* 11.是的的初始化 init?
* 12.闭包函数设置默认值


###析构函数
* 1.每个类最多有一个析构函数 deinit{}
* 2.西枸杞操作，实例销毁前自动调用