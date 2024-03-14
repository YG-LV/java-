# 设计模式（Design pattern）

## 简介

- 设计模式代表了**最佳的实践**，通常被有经验的面向对象的软件开发人员所采用。

- 设计模式是一套被反复使用的、多数人知晓的、经过分类编目、代码设计经验的总结。

- 使用设计模式是为了重用代码、让代码更容易被让人理解、保证代码可靠性。

- 在1994年，由 Erich Gamma、Richard Helm、Ralph Johnson 和 John Vlissides 四人合著出版了一本名为 **Design Patterns - Elements of Reusable Object-Oriented Software（中文译名：设计模式 - 可复用的面向对象软件元素）** 的书，该书首次提到了软件开发中设计模式的概念。

  四位作者合称 **GOF（四人帮，全拼 Gang of Four）**。他们所提出的设计模式主要是基于以下的面向对象设计原则。

  - 对接口编程而不是对实现编程。

  - 优先使用对象组合而不是继承。

## 设计模式的类型

总共有23种设计模式，可分为3大类，创建型（内含5种）、结构型（内含7种）、行为型（内涵11种），还有一种J2EE模式

常用的设计模式：单例、工厂、建造者、装饰、代理、观察

| 序号 | 模式&描述                                                    |                             包括                             |
| :--: | :----------------------------------------------------------- | :----------------------------------------------------------: |
|  1   | **创建型模式**<br />    这些设计模式提供了一种在创建对象的同时隐藏创建逻辑的方式，而不是使用new运算符直接实例化对象。这使得程序在判断针对某个给定实例需要创建哪些对象时更加灵活。 | 工厂模式（Factory Pattern） <br />抽象工厂模式（Abstract Factory Pattern） <br />单例模式（Singleton Pattern）<br /> 建造者模式（Builder Pattern） <br />原型模式（Prototype Pattern） |
|  2   | **结构型模式**<br />   这些模式关注对象之间的组合和关系，旨在解决如何构建灵活可复用的类和对象结构。 | 适配器模式（Adapter Pattern） <br />桥接模式（Bridge Pattern） <br />过滤器模式（Filter、Criteria Pattern） <br />组合模式（Composite Pattern） <br />装饰器模式（Decorator Pattern）<br /> 外观模式（Facade Pattern） <br />享元模式（Flyweight Pattern） <br />代理模式（Proxy Pattern） |
|  3   | **行为型模式**<br />   这些模式关注对象之间的通信和交互，旨在解决对象之间的责任分配和算法的封装。 | 责任链模式（Chain of Responsibility Pattern）<br /> 命令模式（Command Pattern）<br /> 解释器模式（Interpreter Pattern） <br />迭代器模式（Iterator Pattern） <br />中介者模式（Mediator Pattern）<br /> 备忘录模式（Memento Pattern） <br />观察者模式（Observer Pattern） <br />状态模式（State Pattern） <br />空对象模式（Null Object Pattern） <br />策略模式（Strategy Pattern） <br />模板模式（Template Pattern） <br />访问者模式（Visitor Pattern） |
|  4   | **J2EE模式**<br />   这些模式特别关注表示层。这些模式由Sun Java Center鉴定的。 | MVC 模式（MVC Pattern）<br />业务代表模式（Business Delegate Pattern） <br />组合实体模式（Composite Entity Pattern）<br /> 数据访问对象模式（Data Access Object Pattern）<br /> 前端控制器模式（Front Controller Pattern）<br /> 拦截过滤器模式（Intercepting Filter Pattern）<br /> 服务定位器模式（Service Locator Pattern）<br /> 传输对象模式（Transfer Object Pattern） |

## 设计模式的六大原则

- 开闭原则（Open Close Principle）
  - 开闭原则的意思是：对扩展开放，对修改关闭。在程序需要进行拓展的时候，不能去修改源代码，实现一个热拔插的效果。简言之，是为了使程序的扩展性好，易于维护和升级。想要达到这样的效果，我们需要使用接口和抽象类。

- 里氏代换原则（Liskov Substitution Principle）
  - 
  - 里氏代换原则是面向对象设计的基本原则之一。里氏代换原则中说，任何基类可以出现的地方，子类一定可以出现。
  
- 依赖倒转原则（Dependence Inversion Principle）
  - 这个原则是开闭原则的基础，具体内容：针对接口编程，依赖于抽象而不依赖于具体

- 接口隔离原则（Interface Segregation Principle）
  - 这个原则的意思是：用多个隔离的接口，比使用单个接口要好。它还有另外一个意思是：降低类之间的耦合度。

- 迪米特法则，又称最少知道的原则（Demeter Principle）
  - 最少知道原则是指：一个实体应当尽量少地与其他实体之间发生相互作用，使得系统功能模块相对独立

- 合成复用原则（Composite Reuse Principle）
  - 合成复用原则是指：尽量使用合成/聚合的方式，而不是使用继承。

