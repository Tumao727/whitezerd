---
title: 谈谈前端框架
date: "2020-02-16"
description: "尤大不吹不黑聊聊前端框架知乎live笔记"
---

### 前言

很久之前知乎live出过一个前端集合大礼包，里面有一堆前端相关live，本着囤货心理入手后断断续续基本都听了。前端三大框架里，自己用过，或是比较感兴趣的是 React 和 Angular，因此原本对这个live兴趣不大（喂），在通勤路上打发时间当背景音乐。但当时听完就惊了，觉得收获颇丰，可能是我见识短浅吧，live里很多地方都有启发。今天又重听了一遍，顺带记了下重点ww

以下就是听了[不吹不黑聊聊前端框架](https://www.zhihu.com/lives/846356429794336768)后做的笔记ww

---

![前端三大框架](https://miro.medium.com/max/2568/1*GEVBYK_t2QirtIhCJwrxvA.jpeg)

### 组件的理解与分类

1. 以组件为基础单位进行开发，React 告诉人们组件不仅仅对应用于展示的静态页面，还可以是函数

2. 组件的分类：
   1. 纯展示型组件。
   2. 接入型组件。典型如 container 组件，与数据层 service 打交道，再传给下层纯展示型组件
   3. 交互型组件。典型如表单类封装组件，强调复用
   4. 功能型组件。比较抽象。例如 router components，本身不渲染内容，作为一个扩展或抽象机制存在

3. templates 与 JSX
   * JSX 在书写功能型组件时远超 templates，但在书写纯展示型时，templates 用着更爽

4. collocation？
把应该放一起的东西放一起。例如把 html，css，js文件放一起。传统以语言为标准切分，组件化一般以组件本身为单位切分

### 渲染机制

* 声明式与命令式
* view = render(state)
* virtual DOM（可以去 [github](https://github.com/search?q=Virtual+dom)上搜搜实现）

### 变化监测机制

* 响应式 [Reactivity in Frontend JavaScript Frameworks - Google 幻灯片](https://docs.google.com/presentation/d/1_BlJxudppfKmAtfbNIcqNwzrC5vLrR_h1e09apcpdNY/edit#slide=id.p)
* 变化监测主要分为 push 和 pull 两种
* pull：React 的 setState 与 Angular.js 的脏值检查。暴力遍历比对，来发现 diff
* push：RxJS 等响应式，可以进行更细粒的更新。可是每一次变动都有一个 observer 或 watcher，会更耗费内存，带来更大依赖追踪的开销

### 状态管理

1. Redux，MobX，Vuex等
   * 事件源 ==> state 状态改变 ==> DOM 的 UI 改变
   * Redux：数据不可变，纯函数
   * MobX：数据可变，响应式
   * 问题：都没有解决异步
   * 建议：简单 CRUD 也不会有复杂异步，在有复杂异步操作时，用 RxJS 来做
   * 可以思考改进点：组件状态与全局状态如何区分？全局状态与服务端数据如何同步？

### 路由

1. 组件与路由可以解耦
2. 路径 url 映射到组件
3. web 路由与 app 路由的区别

### CSS方案

1. 与 JS 完全解耦，靠预处理器和如 BEM 这样的规范保持可维护性
2. CSS Modules，通过编译避免类名的全局冲突
3. CSS in JS，比较激进
   * 参考资料：
      * [React: CSS in JS - Speaker Deck](https://speakerdeck.com/vjeux/react-css-in-js)
      * [A Unified Styling Language - SEEK blog - Medium](https://medium.com/seek-blog/a-unified-styling-language-d0c208de2660)
4. 与组件相绑定，限定作用域，如 Vue 单文件组件 CSS，Angular 写在装饰器里的 CSS，比较折中
5. 传统 CSS 问题：作用域，服务端渲染时的 critical CSS，atomic CSS（把共享的规则拆成更小的类，优化尺寸），分发复用，跨平台复用
6. 关注 shadow DOM 与 web components

### 构建工具

1. web能做的东西越来越多，需求越来越复杂，因此构建工具也愈加复杂
2. 解决的问题：
   1. 任务自动化
   2. 开发体验与效率（新的语言特性，语法糖，hot reload等）
   3. 部署相关需求
      * 参考资料：[大公司里怎样开发和部署前端代码？ - 知乎](https://www.zhihu.com/question/20790576)
   4. 编译优化

### 服务端通信

1. 数据之间有复杂嵌套关联
   * GraphQL
2. 需要实时

### 服务端渲染与跨平台渲染

参考资料： [Vue SSR Guide](ssr.vuejs.org)

### 新规范

1. web components
   * 参考资料：[Web Component 和类 React、Angular、Vue 组件化技术谁会成为未来？ - 知乎](https://www.zhihu.com/question/58731753)
2. webassembly

### 问答

1. 如何阅读源码？
   * 参考资料：[Vue2.1.7源码学习 | HcySunYang](http://hcysun.me/2017/03/03/Vue%E6%BA%90%E7%A0%81%E5%AD%A6%E4%B9%A0/)

2. 框架选型如何抉择？
   * 几大框架适用场景相差不大，可以更多从团队角度出发选择，例如人员水平喜好，后续招聘等
