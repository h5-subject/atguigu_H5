## 1. vue组件之间的通信？
	1). props
	2). vue自定义事件
	3). 消息订阅与发布
	4). slot
	5). vuex
## 2. vue与react的比较?
	1). 相似处
		功能: 动态构建用户界面
		虚拟DOM: 内部都通过虚拟DOM提高效率
		组件化: 都使用组件化编程思想编写项目
		Props: 组件间通信的基本方式
		构建工具: 脚手架, webpack
		Chrome开发工具: react/redux-dev-tool  vue-dev-tool
	2). 不同点
		界面: JSX与模板
		界面更新: 状态管理 与 对象属性监视
		数据绑定: 单向与双向

## 3. 对于MVVM的理解
	1). MVVM 是 Model-View-ViewModel 的缩写。
	2). Model代表数据模型，也可以在Model中定义数据修改和操作的业务逻辑
	3). View 代表UI 组件，它负责将数据模型转化成UI 展现出来。
	4). ViewModel 监听模型数据的改变和控制视图行为、处理用户交互，简单理解就是一个同步View 和 Model的对象，连接Model和View。
	5). 在MVVM架构下，View 和 Model 之间并没有直接的联系，而是通过ViewModel进行交互，Model 和 ViewModel 之间的交互是双向的， 
		因此View 数据的变化会同步到Model中，而Model 数据的变化也会立即反应到View 上。
	6). ViewModel 通过双向数据绑定把 View 层和 Model 层连接了起来，而View 和 Model 之间的同步工作完全是自动的，
		无需人为干涉，因此开发者只需关注业务逻辑，不需要手动操作DOM, 不需要关注数据状态的同步问题，
		复杂的数据状态维护完全由 MVVM 来统一管理。

## 4. Vue的生命周期
	

## 5. Vue实现数据双向绑定的原理
	1). vue实现数据绑定主要是：采用数据劫持 + 消息订阅发布模式的方式，
	2). 通过Object.defineProperty()来劫持/监视data中的属性，在数据变动时发布消息给所有订阅者，每个订阅者去更新对应的DOM节点。
    3). 双向数据绑定是单向数据绑定的基础上, 给元素绑定input监听, 一旦输入改变了, 将最新的值保存到对应的属性上

## 6. 区别2种路由实现：hash模式 和 history模式
	1). hash模式：
		在浏览器中符号“#”，#以及#后面的字符称之为hash，用window.location.hash读取；
		注意：hash虽然在URL中，但不会提交给服务器端, 只在浏览器端使用
	2). history模式：
		路由路径中没有#, 利用HTML5的新特性: pushState()/replaceState()及popState事件监听
		注意: 路径会提交给后台, 在生产环境下会出现404的问题
		解决404问题: 后台服务器端配置404页面或通过自定义中间件指定404页面为index.html页面

## 7. 什么是vue的计算属性?
	在模板中放入太多的逻辑会让模板过重且难以维护，在需要对数据进行复杂处理，且可能多次使用的情况下，尽量采取计算属性的方式。好处：
		①使得数据处理结构清晰；
		②依赖于数据，数据更新，处理结果自动更新；
		③计算属性内部this指向vm实例；
		④在template调用时，直接写计算属性名即可；
		⑤常用的是getter方法，获取数据，也可以使用set方法改变数据；
		⑥相较于methods，不管依赖的数据变不变，methods都会重新计算，但是依赖数据不变的时候computed从缓存中获取，不会重新计算。

## 8. 区别$route和$router
	$route是“路由信息对象”: 包括path，params，hash，query，meta等路由信息参数。
	$router是“路由实例”对象: 包括了路由的跳转方法，注册全局导航守卫的方法