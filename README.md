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


###自动引用计数
* 1.ARC实现：每当创建一个实例，ARC分配一块内存存储实例信息，当有强引用指向实例时，内存不会释放，没有强引用时释放内存
* 2.循环引用：使用weak或unowned修饰变量，unowned（类似unsafe）修为的变量一定有值，weak修饰的变量可能为空（可选值），当weak引用的对象释放时会被置空
* 3.无主引用:unowned类型必须有值，所以在类构造函数时候，必须初始化保证有值
* 4.无主引用和隐式拆分可选属性：当两个属性都要一直有值得时候，看例子
* 5.闭包强引用循环：闭包是函数指针，即类实例有一个强引用指向函数，函数体内截获的类成员属性又间接对实例强引用，构成函数和实例的循环引用
* 7.闭包循环引用解决方法： 创建捕获列表，捕获元素由weak/unowned关键词修饰[unowned self, weak delegate = self.delegate!] in 


###可选链
* 1.可选链：告诉编译器自检查当前调用的目标可能为空，如果为空则直接返回nil，否则就调用成功


###错误处理
* 1.函数前面声明throws声明此函数可以抛出错误，throwing函数
* 2.抛出错误使用throw关键字
* 3.在调用一个能抛出错误的函数前面。加try关键字
* 4.Do-Catch处理函数
* 5.将错误转换成可选值，let x = try? someThrowingFunction()
* 6.如果明知道throwing函数不会抛出错误，想要禁止错误传递，可以用try!
* 7.指定清理操作，defer语句在即将离开当前作用域前执行一些清理操作

###类型检查
* 1.使用is检查一个实例是否是一个类的子类 if item is Class
* 2.使用as？ ，as! 类型转换, let movie = item as? Class
* 3.Any 任何对象类型
* 4.AnyObject,任何类型，包括函数

###类型嵌套
* 1.枚举、类、结构体支持类型嵌套

###扩展
* 1.扩展语法类似Objective-C 的Catergory: 向一个已有的类、结构体、枚举中添加新方法
* 2.添加计算型属性和计算静态属性
* 3.提供实例方法和类型方法
* 4.提供新的构造器(只能是便捷构造器)
* 5.定义下标
* 6.定义和使用新的嵌套类型
* 7.使一个类型遵从某个协议

###协议
* 1.协议语法
* 2.协议声明属性
* 3.协议声明方法
* 4.协议突变方法，修改自身
* 5.协议声明构造函数
* 6.协议作为类型，入参，返回类型、常量、变量、数组或字典中的元素
* 7.委托
* 8.在扩展中给类添加协议
* 9.当一个类型已经实现了协议中所要求的，却没有声明，可以通过扩展来声明
* 10.集合中的协议类型
* 11.协议的继承，协议能继承一个或多个协议
* 12.声明只允许类遵从的协议
* 13.协议的合成，protocol<protocol1,procotol2>
* 14.检查协议的一致性，is, as?, as!
* 15.添加可选协议，@objc前缀修饰协议，协议中用optional声明方法或属性
* 16.协议的扩展：不仅声明方法，还可以添加方法的实现
* 17.给协议提供默认的实现方法，利用extension
* 18.为协议扩展添加闲置条件

###泛型
* 1。泛型解决的问题<T>占位符，告诉编译器它只是占位符，不用查找所代表的类型，只有在调用的时候才知道
* 2. 泛型类型
* 3.扩展一个泛型类型
* 4.给泛型类型加约束
* 5.通过扩展给一个存在的类型指定关联类型

###访问控制
* 1.Xcode的每个target都被当做独立的模块处理
* 2.源文件就是swift中的源代码文件，它通常属于一个模块
* 3.public（最高级别）:可以访问同一模块源文件中的任何实体，在模块外也可以通过导入该模块来访问源文件里的所有实体
* 4.internal（默认级别）:可以访问同一模块源文件中的任何实体，但是不能从模块外访问访问模块源文件中的实体
* 5.private（最低级别）: 限制实体只能在所在源文件内部使用
* 6.访问级别的基本原则：
	* 一个public访问级别的变量，其类型的访问级别不能是internal或private
	* 函数的访问级别不能高于它的参数类型和返回类型的访问级别
* 7.单元测试target的访问级别：默认情况只有public界别的实体才可以访问其他模块访问，为了测试，可以在导入应用程序模块的语句前使用@testable特性，然后在允许测试的编译设置（Build Options -> Enable Testablity）下编译这个应用程序模块，单元测试target就可以访问应用程序模块中所有internal级别的实体
* 8.自定义类型，如果类型指定为private级别，那么该类型的所有成员的默认级别也会为private,如果类型指定为public或internal级别，那么该类型的所有成员默认访问级别是internal
* 9.函数的访问级别根据访问级别最严格的参数类型或返回类型级别决定，如果这个访问级别不符合函数定义的默认级别，需要明确的指定该函数的访问级别
* 10.枚举成员的访问级别和枚举类型相同，不能为枚举成员单独指定不同的访问级别，并且初始值不能低于枚举类型的级别
* 11.嵌套类型：如果在private级别的类型中定义嵌套，那么嵌套类型自动拥有private访问级别；如果在public或internal级别的类型中定义嵌套，默认拥有internal访问级别
* 12.子类的访问级别不得高于父类的访问级别，可以通过重写为继承来的类成员提供更高的界别
* 13.自定义构造器的访问级别可以低于或等于其所属类型的访问级别，但是require得构造器必须与所属类型的访问级别相同
* 14.默认构造器的访问级别与所属类型相同，如果类型级别为public，那默认构造器级别是internal
* 15.如果结构体中任意存储属性访问级别为private，那默认的成员逐一构造器级别为private,否则默认为internal
* 16.协议中的每一个要求都具有和该协议相同的访问级别。如果协议是public级别，则其他成员的访问级别也是public。
* 17.协议继承：如果定义了一个继承自其他协议的新协议，那么新协议的访问级别<=被继承的洗衣级别
* 18.协议一致性：一个类型可以采纳比自身访问级别低的协议，采纳了协议的类型访问级别取决于它本身和所采纳协议两者间最低的访问级别。采纳协议后，确保协议的实现级别不低于协议的级别
* 19.扩展，默认internal，
		