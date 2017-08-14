### I.MVX模式
>M: Model,代表整个webapp所需要的数据模型，含有大量的信息，但是不具有任何行为逻辑，只是数据，不会影响浏览器和如何展示数据。
V: View,用户界面，View是唯一能够和用户交互的地方
ViewModel: 类似controller，主要负责数据转换，业务逻辑处理，将Model的变化反应到View上，而View自身有变化的同事也会同步Model进行改变。

##### 1. MVC: Modal-View-Controller，模型-视图-控制器
>在mvc（如php）模式中，view是可以直接访问model的，view中包含model的信息，不可避免的还要包含一些业务逻辑，mvc关注的是model的不变，因此在mvc模式中，model不依赖于view,但是view依赖与model,其中view层中可能还包含一些业务逻辑，也因此导致更改view比较困难，没有完全实现前后端分离

##### 2. MVP: Model-View-Presenter，数据层-视图层-发布层
>model层和view层不直接通信，它们之间的通信是通过presenter，所有的交互都在presenter内部

##### 2. MVVM : Model-View-ViewModal，有Knockout,Ember.js,Angular.js,Vue.js
>是一种基于MVC的设计，实现数据双向绑定，能在ViewModel和Model保持不变的情况下，很方便的将UI设计与业务逻辑分离，从而大大的减少繁琐的DOM操作
     view和model之间没有联系，而是通过ViewModel进行交互，而且Model和ViewModel之间是双向交互的。
    mvvm在概念上真正将页面与数据逻辑分离 

### Ⅱ.数据双向绑定
>视图View的变化能实时让数据模型Model发生变化，而数据的变化也能实时更新到视图层。[可参考知乎用户@野草](https://zhuanlan.zhihu.com/p/25464162),解释的很详细。
view发生变化更新到model，model变化更新到view
view层（视图层）的变化主要是表单控件的用户输入行为造成的，比如input,select,textarea等，对于view层的变化，我们只需要监听一些事件，如keypress，keydown,keyup,change,然后在事件回调函数中，将变化的值更新到model中，同时model发生了变化，会再次更新下View。

model的变化监听方式有很多种，主要有发布订阅模式（Backbone）,数据劫持（VueJs,AvalonJs）,数据脏检查（AngularJs,RegularJs）,View 抽象的脏检查（ReactJs）

#### 发布订阅模式也称为观察者模式
>直观地说，就是有一家报社和很多用户，报社就是发布者，用户就是订阅者。每当报社有新的报纸时，由于订阅者订阅了报纸，他们能第一时间收到新的报纸。当然订阅者也可以取消订阅。

#### 数据劫持模式
>
#### 脏检查
