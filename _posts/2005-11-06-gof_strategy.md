---
layout: post
title: GoF行为型模式之Strategy
category: GoF_Patterns
---

如果某个类里所使用的算法有多种,而且会有变化和扩展, 这时可以把算法从类里分离出来,并把不同的算法一个个封装成单独的类,算法可以单独变化和扩展,程序在使用时可以从这组算法里选择,对于算法的这种封装方式就是Strategy模式.

Strategy模式结构图:

![](/img/gof/strategy.gif)

Strategy模式中，对象与其行为（behaviour）这本来紧密联系的两部分被解耦，分别放在了不同的类中。这使得对同一个行为，可以方便的在任何时候切换不同的实现算法。而通过对策略的封装，为其提供统一的接口，也可以很容易的引入新的策略。

如果有几个很相似的类，其区别仅仅是在个别行为上的动作不同，这时候就可以考虑使用Strategy模式。这样，通过策略组合，将原来的多个类精简为一个带有多个策略的类。这很符合OO设计的原则：找到变化的部分，并将其封装起来！Strategy模式同样的为子类继承提供了一个好的替代方案，当使用继承机制的时候，行为的改变是静态的，你指能够改变一次--而策略是动态的，可以在任何时候，切换任何次数。更为重要的是，策略对象可以在不同的环境中被不同的对象所共享。

Strategy模式也有一些缺点，比如，应用程序必须知道所有的策略对象，并从中选择其一。而且在策略对象被使用的时候，它和Context对象之间通常是紧耦合的，Context对象必须为策略对象提供与具体算法相关的数据或者其它的东西，而这些数据的传递可能并不能够风装载抽象地策略类中，因为并不是所有的算法都会需要这些数据的。另外，因为策略对象通常由应用程序所创建，Context对象并不能够控制Strategy的生命期，而在概念上，这个策略应该从属于Context对象，其生命期不应该超出Context的范围对象。

通常的，Strategy很容易和Bridge模式相混淆。确实，他们有着很相近的结构，但是，他们却是为解决不同的问题而设计的。Strategy模式注重于算法的封装，而Bridge模式注重于分离抽象和实现，为一个抽象体系提供不同的实现。
