# DesignPatterns
本项目与CSDN博客同步展示，希望将自己对于设计模式的认知展示出来与大家共同探讨和分析，在讲解设计模式的同时，将写博客期间写的示例进行分享，本项目会在博客更新后一段时间内进行代码示例的更新，请大家多多关注和支持！博客地址：http://blog.csdn.net/wangyang1354/
# 设计模式文章综述
## 单一功能原则
单一功能原则（Single responsibility principle）规定每个类都应该有一个单一的功能，并且该功能应该由这个类完全封装起来。所有它的（这个类的）服务都应该严密的和该功能平行（功能平行，意味着没有依赖）。http://blog.csdn.net/wangyang1354/article/details/51136530

## 里氏替换原则
在面向对象的程序设计中，里氏替换原则（Liskov Substitution principle）是对子类型的特别定义。它由芭芭拉·利斯科夫（Barbara Liskov）在1987年在一次会议上名为“数据的抽象与层次”的演说中首先提出。

里氏替换原则的内容可以描述为： “派生类（子类）对象能够替换其基类（超类）对象被使用。” 以上内容并非利斯科夫的原文，而是译自罗伯特·马丁（Robert Martin）对原文的解读。其原文为：

    Let q(x) be a property provable about objectsx of typeT. Thenq(y) should be true for objectsy of typeS whereS is a subtype ofT.

芭芭拉·利斯科夫与周以真（Jeannette Wing）在1994年发表论文并提出的以上的Liskov代换原则。----维基百科
里氏替换原则我个人的理解是：在继承关系中，父类的对象如果替换为子类的对象，他原来执行的行为依然保持不变，那么这样的程序才符合里氏替换原则，否则违背了里氏替换原则。http://blog.csdn.net/wangyang1354/article/details/51164514

## 依赖倒置原则
In object-oriented programming, the dependency inversion principle refers to a specific form of decoupling software modules. When following this principle, the conventional dependency relationships established from high-level, policy-setting modules to low-level, dependency modules are reversed, thus rendering high-level modules independent of the low-level module implementation details. The principle states:

        A. High-level modules should not depend on low-level modules. Both should depend on abstractions.
        B. Abstractions should not depend on details. Details should depend on abstractions.

The principle inverts the way some people may think about object-oriented design, dictating that both high- and low-level objects must depend on the same abstraction.
----WIKIPEDIA
释义（读者可以试着自己翻译下，个人感觉第二句不好翻，不过蛮有意思的）：

在面向对象的程序设计中，依赖倒置原则是指解耦软件模块的特殊的形式。传统的依赖关系建立在高层次，而具体的策略设置应用在低层次上。使用依赖倒置原则，使得高层独立于底层的实现细节，依赖关系被倒置，使得低层次模块依赖于高层次模块的抽象。

原则规定：
A. 高层模块不应该依赖于低层模块，双方都要依赖于抽象类。
B. 抽象类不应该依赖于实现细节，实现细节应该依赖于抽象。
这项原则颠覆了一些人对面向对象程序设计的认识，比如：高层和低层都应该依赖于相同的抽象。
http://blog.csdn.net/wangyang1354/article/details/51167071

## 接口隔离原则
接口隔离原则（英语：interface-segregation principles， 缩写：ISP）指明没有客户（client）应该被迫依赖于它不使用方法。接口隔离原则(ISP)拆分非常庞大臃肿的接口成为更小的和更具体的接口，这样客户将会只需要知道他们感兴趣的方法。这种缩小的接口也被称为角色接口（role interfaces）。接口隔离原则(ISP)的目的是系统解开耦合，从而容易重构，更改和重新部署。----WIKIPEDIA

个人对于接口隔离原则的理解是:
设计接口的时候，尽量保证实现接口的那些类尽可能一致的包含着接口中的方法，避免过多的设计了接口中的方法，导致其实现类中需要实现多个完全没有用处的方法（会造成代码的冗余和混乱）。
http://blog.csdn.net/wangyang1354/article/details/51172635

## 迪米特法则(最少知道准则)
得墨忒耳(迪米特)定律（Law of Demeter，缩写LoD）亦称为“最少知识原则（Principle of Least Knowledge）”，是一种软件开发的设计指导原则，特别是面向对象的程序设计。得墨忒耳(迪米特)定律是松耦合的一种具体案例。该原则是美国东北大学在1987年末在发明的，可以简单地以下面任一种方式总结:

    1. 每个单元对于其他的单元只能拥有有限的知识：只是与当前单元紧密联系的单元；

    2. 每个单元只能和它的朋友交谈：不能和陌生单元交谈；

    3. 只和自己直接的朋友交谈。

这个原理的名称来源于希腊神话中的农业女神，孤独的得墨忒耳。

很多面向对象程序设计语言用"."表示对象的域的解析算符，因此得墨忒耳定律可以简单地陈述为“只使用一个.算符”。因此，a.b.Method()违反了此定律，而a.Method()不违反此定律。一个简单例子是，人可以命令一条狗行走（walk），但是不应该直接指挥狗的腿行走，应该由狗去指挥控制它的腿如何行走。----WIKIPIDIA

个人的理解：

面向对象的程序设计中，对象与对象之间尽量相互独立，具体对象的行为由具体的对象去完成，而不是由某个对象去指定另一个对象去实施行为而且是具体的行为。迪米特法则，核心的思想就是，要求我们在设计的时候，尽量避免类与类之间的耦合，弱化耦合关系可以提升复用率，但是这样的话，会产生中间的跳转类等，导致系统复杂。实际使用的过程中尽量在保证可读性与复杂性较低的情况下，按照迪米特法则去弱化类与类之间的耦合关系（高内聚、低耦合）。
http://blog.csdn.net/wangyang1354/article/details/51177866

## 开闭原则
在面向对象编程领域中，开闭原则规定“软件中的对象（类，模块，函数等等）应该对于扩展是开放的，但是对于修改是封闭的”，这意味着一个实体是允许在不改变它的源代码的前提下变更它的行为。该特性在产品化的环境中是特别有价值的，在这种环境中，改变源代码需要代码审查，单元测试以及诸如此类的用以确保产品使用质量的过程。遵循这种原则的代码在扩展时并不发生改变，因此无需上述的过程。

开闭原则的命名被应用在两种方式上。这两种方式都使用了继承来解决明显的困境，但是它们的目的，技术以及结果是不同的。----WIKIPEDIA

个人对于开闭原则的理解：

开闭原则相当于一个纲领性质的原则，提倡类等应该在设计完成后通过扩展的方式适应新的业务需求，而不是通过修改的方式去适应新的需求，这样的设计更加灵活、稳定。之前的五大原则是开闭原则思想的具体实现的情况。
http://blog.csdn.net/wangyang1354/article/details/51179851

## 单例模式
单例模式，也叫单子模式，是一种常用的软件设计模式。在应用这个模式时，单例对象的类必须保证只有一个实例存在。许多时候整个系统只需要拥有一个的全局对象，这样有利于我们协调系统整体的行为。比如在某个服务器程序中，该服务器的配置信息存放在一个文件中，这些配置数据由一个单例对象统一读取，然后服务进程中的其他对象再通过这个单例对象获取这些配置信息。这种方式简化了在复杂环境下的配置管理。----维基百科（WIKIPEDIA）

个人的理解：

单例模式概念比较简单，他的目的就是只允许出现一个该类的实例，经常在JDBC操作类等处被用到，我在项目中应用到的地方就是用于获取Dao层的类的实例，单例模式有多种实现方式，这里我认知到的有饿汉式、懒汉式、枚举、静态内部类。庆幸这次整理过程，因为又拓展了不少的单例模式的知识。
http://blog.csdn.net/wangyang1354/article/details/51193223

## 简单工厂、工厂方法、抽象工厂
工厂模式的核心思想在我认为是将类创建的权利授予给工厂类，其他的类不允许创建，授予了权限的类创建好之后，需要某些的对象的时候，可以去工厂当中去取。也就是像一个工厂一样，用的人不需要关心对象怎么来的，你只需要关心怎么用就好了。工厂模式细分为三种，简单工厂、工厂方法、抽象工厂三种模式。这三种模式比较相似，往往会引发混淆，本文主要结合实际的例子去进行区分。理清三者之间的关系与适用范围。

概述
简单工厂
对于简单工厂，我个人的理解是，直接实现一个方法，要生产什么由这个方法以及传入的参数来决定。

工厂方法
1. 解决了哪类“工厂”生产哪类东西的问题。
2.这种模式通过公共的接口或抽象类定义生产出来的是哪种东西，但是不限制生产出来的具体产品，在其子类中或者实现类中去确定具体生产出来的是什么东西。

抽象工厂
1. 解决了同一种东西多种分类的情况。
2. 抽象类去设定生产的产品的具体分类，交给子类去实际生产该分类下的产品。

简单的讲，三者最主要的区别在于：
简单工厂：通过参数控制生产的不同的产品。
工厂方法：通过不同的子类工厂生产不同的产品。
抽象工厂：通过方法生产不同的产品。
http://blog.csdn.net/wangyang1354/article/details/51211877

## 创建者模式
生成器模式（英：Builder Pattern）是一种设计模式，又名：建造模式，是一种对象构建模式。它可以将复杂对象的建造过程抽象出来（抽象类别），使这个抽象过程的不同实现方法可以构造出不同表现（属性）的对象。----WIKIPEDIA

个人的理解：
建造者模式可以设置不同的属性或者行为，创建出不一样的对象。比如说生产汽车，假如有三个重要的工序，塑形、拼装、上色。那么可以通过创建者模式来设置，这三道工序中不同的车来说，三道工序可能就是不一样的。通过创建者模式来创建出对象的表现形式也自然就不一样。
http://blog.csdn.net/wangyang1354/article/details/51317511

## 原型模式
原型模式是创建型模式的一种,其特点在于通过“复制”一个已经存在的实例来返回新的实例,而不是新建实例。被复制的实例就是我们所称的“原型”，这个原型是可定制的。
原型模式多用于创建复杂的或者耗时的实例，因为这种情况下，复制一个已经存在的实例使程序运行更高效；或者创建值相等，只是命名不一样的同类数据。
原型模式的优点

原型模式多用于创建复杂的或者耗时的实例，因为这种情况下，复制一个已经存在的实例使程序运行更高效；或者创建值相等，只是命名不一样的同类数据。
注意：
1.原型模式创建对象不会调用构造函数进行创建。直接从内存去赋值对象的数据，忽略构造函数的限制，他和之前提到的单例模式有所冲突，单例模式会将构造函数设置为私有，而原型模式却可以绕过构造函数去通过内存中的对象的数据区创建对象，所以这个地方就会有所冲突。
2. 注意深拷贝和浅拷贝。对于数组、容器对象、对象等可能需要进行深拷贝。
http://blog.csdn.net/wangyang1354/article/details/51407774

## 适配器模式
在设计模式中，适配器模式（英语：adapter pattern）有时候也称包装样式或者包装(wrapper)。将一个类的接口转接成用户所期待的。一个适配使得因接口不兼容而不能在一起工作的类工作在一起，做法是将类自己的接口包裹在一个已存在的类中。----WIKIPEDIA

个人理解
适配器模式：将两个不一致或者说无法直接使用的类或者接口通过适配器模式进行兼容，使得他们可以在一块使用。适配器模式在之前的项目中我是用于处理数据的不兼容的，对方的数据和我们的数据格式不完全一致，包括，类型的不一致和内容的不一致，类型的不一致比较容易解决，但是内容的不一致比如:对方的数据中存在一个id对应着俩值，而在我们的系统中，一个id只对应一个值，这样的话，显然没办法直接使用，而且，需要对对方的数据进行存储下来，进行了一定的设置后才会将数据存入我们的数据库中，我当时的解决办法是，将存入本地的id设为string类型，然后通过id_** ,id_标识位 进行标识该值属于哪个id以及其代表的意义。为了实现这种目的我采用了适配器模式，对方传递的数据封装好，通过适配器将该封装好的对象转为我们可以进行本地存储的对象。
http://blog.csdn.net/wangyang1354/article/details/51418351

## 代理模式
代理模式（英语：Proxy Pattern）是程序设计中的一种设计模式。
所谓的代理者是指一个类可以作为其它东西的接口。代理者可以作任何东西的接口：网络连接、内存中的大对象、文件或其它昂贵或无法复制的资源。----WIKIPEDIA

个人理解
代理模式就是找另外的一个对象作为代理去为你实施请求，代理模式分为两种，一种是静态代理模式，另外一种是动态代理模式，静态代理模式是代理类为其创建一个对象，将需要代理的类的对象赋予代理类中的该对象，让代理类中该对象去代替需要代理的类的对象去执行一定的任务。动态代理模式采用JDK的动态代理，根据其类加载器以及其实现的接口生成代理对象，通过反射机制实现动态代理。http://blog.csdn.net/wangyang1354/article/details/51438301

## 装饰模式
修饰模式，是面向对象编程领域中，一种动态地往一个类中添加新的行为的设计模式。就功能而言，修饰模式相比生成子类更为灵活，这样可以给某个对象而不是整个类添加一些功能。----WIKIPEDIA

个人理解
相比而言我对装饰模式的理解还不是很深入，在项目中还不知道该怎么去使用它，或许是没有遇到需要装饰模式的情景吧，我对于装饰模式的理解是通过装饰模式可以实现对功能的扩充，由此我想到了面向切面编程，因为我记得AOP在实现的时候，就是对类的功能进行增强，可以在方法调用前执行、调用后、异常时等发生的时候去执行相应的处理，我在想会不会实现的时候采用的模式就是装饰模式呢？这里我先留着这个疑问后期有时间看源码的话再去探讨到底是不是用了这个模式。装饰模式中可以通过构造函数传入要装饰的类的实例，装饰类和被装饰的类要有相同的接口，保证当装饰类没有进行增强处理的时候，依然可以去执行被装饰类应该执行的方法。http://blog.csdn.net/wangyang1354/article/details/51447174

## 外观模式
外观模式（Facade pattern），是软件工程中常用的一种软件设计模式，它为子系统中的一组接口提供一个统一的高层接口，使得子系统更容易使用。----WIKIPEDIA
个人理解
当一个项目中出现比较杂乱的调用关系时，类与类之间的耦合关系过于复杂，为了降低耦合度，我们可以采用一个公共的接口与其他类发生耦合，这样可以尽量大的降低外界与该系统的耦合度，同时降低了整个系统的复杂度，外观模式相当于一个公共的入口一样，为使用者敞开大门，暴漏一些必要的接口，方便外界进行调用。通俗来讲就是，有多个不同的类提供了多个访问的接口，外观模式就是要统一将这些接口进行管理。http://blog.csdn.net/wangyang1354/article/details/51482525

## 桥梁模式
桥接模式是软件设计模式中最复杂的模式之一，它把事物对象和其具体行为、具体特征分离开来，使它们可以各自独立的变化。事物对象仅是一个抽象的概念。如“圆形”、“三角形”归于抽象的“形状”之下，而“画圆”、“画三角”归于实现行为的“画图”类之下，然后由“形状”调用“画图”。----WIKIPEDIA

个人理解
桥梁模式的核心在于解耦，通过抽象化将具体的事物抽象成一般的事物，也就是具有共性的东西，将两个角色之间的继承关系改为聚合关系，就是将它们之间的强关联改换成为弱关联。因此，桥梁模式中的所谓脱耦，就是指在一个软件系统的抽象化和实现化之间使用聚合关系而不是继承关系，从而使两者可以相对独立地变化。这就是桥梁模式的用意。
http://blog.csdn.net/wangyang1354/article/details/51493068

## 组合模式
组合模式也叫合成模式，有时又叫做部分-整体模式，主要是用来描述部分与整体的关系，其定义为：将对象组合成树形结构以表示“整体与部分”的层次结构，使得用户对单个对象和组合对象的使用具有一致性。----设计模式之禅
个人理解
组合模式目的是将整体与部分组合成树形来表示整体与部分的层次，使得用户对单个对象和组合对象的使用具有一致性的接口，也就是通过接口对子对象统一操作。http://blog.csdn.net/wangyang1354/article/details/51500964

## 享元模式
享元模式（英语：Flyweight Pattern）是一种软件设计模式。它使用共享物件，用来尽可能减少内存使用量以及分享资讯给尽可能多的相似物件；它适合用于当大量物件只是重复因而导致无法令人接受的使用大量内存。通常物件中的部分状态是可以分享。常见做法是把它们放在外部数据结构，当需要使用时再将它们传递给享元。----WIKIPEDIA

个人理解
共享，内存消耗大的时候应考虑对象的共享，共享对象可以减少对象的生成数量，这样可以减少内存的消耗，当一个对象和其他的对象存在共性且内容一致的时候，可以将共有的部分抽取出来进行共享，这样生成的所有对象占用内存的总和会减少，这就体现了共享的重要性。http://blog.csdn.net/wangyang1354/article/details/51583620

## 模板方法模式
模板方法模式定义了一个算法的步骤，并允许子类别为一个或多个步骤提供其实践方式。让子类别在不改变算法架构的情况下，重新定义算法中的某些步骤。----WIKIPEDIA

个人理解
模板方法模式相对而言比较简单，一般的都是由抽象类定义好模板方法，然后，子类通过继承并实现其父类中定义好的模板中需要执行的具体的方法，调用子类对象的模板方法时，会执行该类中的具体实现的方法。这个模式我个人的感觉有点像是面向过程的操作，执行完一道工序，接着下一道工序。http://blog.csdn.net/wangyang1354/article/details/51598144

## 观察者模式
观察者模式是软件设计模式的一种。在此种模式中，一个目标对象管理所有相依于它的观察者对象，并且在它本身的状态改变时主动发出通知。这通常透过呼叫各观察者所提供的方法来实现。此种模式通常被用来实时事件处理系统。----WIKIPEDIA
个人理解
观察者模式，就是使得被观察者中持有观察者的对象实例，在发生某些事件的时候，通过notify“通知”观察者，完成相应的操作，他也叫作发布-订阅模式，定义对象间一对多的依赖关系，使得被观察者对象产生动作，即可通知其依赖的对象该被观察者发生了变更。http://blog.csdn.net/wangyang1354/article/details/51614305

## 策略模式
策略模式作为一种软件设计模式，指对象有某个行为，但是在不同的场景中，该行为有不同的实现算法。比如每个人都要“交个人所得税”，但是“在美国交个人所得税”和“在中国交个人所得税”就有不同的算税方法。----WIKIPEDIA

个人理解
策略模式从名字就可以看出，有多种选择，不同的策略对应着不同的实现方式，那么一般的形式为一个接口采用多种实现方式（也就是提供了不同的策略），然后再提供一个策略的选择类即可，定义中：定义一组算法，将每个算法都封装起来，并且使得他们之间可以相互的转换。通过上面我提到的这种方式来看，一组算法就是指的多种的实现方式，而将每个算法都封装起来并使得他们之间可以互换，实现了统一的接口，自然可以实现互换了。
http://blog.csdn.net/wangyang1354/article/details/51647076

## 状态模式
状态模式--允许一个对象在其内部状态改变时改变它的行为。对象看起来似乎修改了它的类。----百度百科

个人理解
状态模式应该说可以理解为某种状态下，程序的执行流程可能会发生变化，类似于交通灯，红灯的时候停下，绿灯行走，黄灯时等一等，这就是三种状态下我们人对其作出的相应的变化。再比如，公交车应该都坐过的，公交车停车的时候，可以上车和下车；公交车行驶的时候，不允许下车和上车，那么，这里公交车停车和行驶是两种状态，这两种状态对于后续人上车下车的行为产生了一定的影响。通俗点就是说，某种状态作为先决条件时，后面的行为受到了前面的这种状态的影响，这种情况比较适合运用状态模式。http://blog.csdn.net/wangyang1354/article/details/51656040

## 责任链模式
责任链模式在面向对象程式设计里是一种软件设计模式，它包含了一些命令对象和一系列的处理对象。每一个处理对象决定它能处理哪些命令对象，它也知道如何将它不能处理的命令对象传递给该链中的下一个处理对象。该模式还描述了往该处理链的末尾添加新的处理对象的方法。----WIKIPEDIA

个人的理解

责任链模式用到了链表的数据结构，存在一定的次序性，A->B->C这样的一条链表，在责任链模式中，请求交给A进行处理，如果A处理不了交给B，B如果处理的了进行处理，否则交给C处理，模式的关键在于构建这样的一个链表，并且完成链表之间这些处理情况的切换，这一点在定义中应该是说可以把不能处理的命令对象传递给链中的下一个处理对象。这么看来的话，我们平时的分层结构是不是可以理解为非纯正的责任链模式呢？但是我们分层的结构中可能每一层都要完成一些自己应该做的事情，那么，这样的话并不是和责任链模式一致，因为在责任链中是将整个的‘责任’推给下一个节点，不过从某种意义上看的话是有点相似的，因为这也是我个人的理解和思考，读者有不同的意见可以评论。
http://blog.csdn.net/wangyang1354/article/details/51701185


## 命令模式
在面向对象程式设计的范畴中，命令模式是一种设计模式，它尝试以物件来代表实际行动。命令物件可以把行动(action) 及其参数封装起来，于是这些行动可以被：

    重复多次
    取消（如果该物件有实作的话）
    取消后又再重做

这些都是现代大型应用程序所必须的功能，即“复原”及“重复”。----WIKIPEDIA

个人理解
命令模式是一个高内聚的模式，它将一个请求封装为一个对象，让你使用不同的请求将客户端参数化，在项目中应用比较广泛，他的封装性比较好，将请求方和接收方分离开来，扩展性较好。命令模式中主要有三种角色，一个是命令的接受者（Receiver），他负责对于收到的命令作出响应。一个是命令（Command）角色，他负责定义接受者需要执行什么样的命令。另一个是调用者（Invoker），接收命令调用并执行命令。但是命令模式也存在不足，如果命令较多的时候那么会存在多个子类，导致臃肿，可以结合其他的模式进行设计，如结合责任链模式实现命令的解析、结合模板方法模式减少子类的膨胀问题。http://blog.csdn.net/wangyang1354/article/details/51758622




