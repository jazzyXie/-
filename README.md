## ES6 代码转成 ES5 代码的实现思路是什么

使用 babel 转译

1. 解析：把 es6 代码 转换成 AST 语法树
2. 然后按照一定规则将 es6 AST 转换成 es5 AST
3. 再将 es5 AST 转换成 es5 代码

## 为什么字母占一个字节，汉字占两个字节

ASCII 码的问题，存字母需要 8 位空间，汉字太多，需要 16 位空间

## 函数的柯里化

柯里化是指把接受多个参数的函数转换成多个只接受单一参数的函数

## 进程和线程的区别？

一个进程可以有多个线程
进程是资源分配的基本单位、线程是资源调度的基本单位

## 内存泄漏

内存泄漏指浏览器不能正常回收内存的现象

## 浏览器的垃圾回收机制

垃圾收集器必须跟踪哪个变量没被引用，对于不再有用的变量打上标记，以备将来收回其占用的内存

## 浏览器识别无用变量的两个方法

1. 引用计数法
   跟踪记录每个值被引用的次数。当声明一个变量并将引用类型的值赋给该变量时，则这个值的引用次数就是 1。如果同一个值又被赋给另一个变量，则该值的引用次 数加 1.相反，如果包含对这个值引用的变量又取得另外一个值，则这个值的引用次数减 1.当这个值的引用次数变成 0 时，则说明没有办法访问这个值了，因此就 可以将其占用的内存空间回收回来
2. 标记清除法

## 优雅降级和渐进增强

1. 优雅降级
   优雅降级是指一开始就构建相对完善的网站，然后慢慢兼容低版本的浏览器（向后兼容）
2. 渐进增强
   渐进增强是指在基本功能得到满足的条件下，对支持新特性的浏览器使用新特性（向前兼容）

## 什么是 RESTful API？

1. RESTful URL 中只能有名称不能有动词，操作的表达是使用 HTTP 的动词，GET、POST、PUT、DELETE
2. 将 API 版本号放入 URL（如果有需要的话）
3. 尽量将 API 部署在专用域名下

## AMD/CMD 规范

JavaScript 没有模块化，浏览器引入模块取决于 script 标签的引入顺序

为了提高开发效率，从而引入了模块化开发的概念，也就有了 CMD（commonJS）和 AMD（requireJS）

nodejs 是根据 commonjs 规范而创作的项目，CMD 规范中的模块加载方式是同步的，所以 CMD 规范只适用于服务器端，不适用于浏览器端（服务器端 require 加载速度取决于硬盘读取速度，浏览器端 require 读取速度取决于网速）

所以后来就有了 AMD（requireJS），而 requireJS 是一个库，使用的时候需要引入

## 为什么需要前后端分离？

1. 知识背景，技术栈不同，难以互相理解
2. 前后端是一个依赖的关系，前端需要依赖后端的数据接口

我认为理想的前后端分离方式是
职能上，后端提供纯粹的接口，只需要提供数据-系统的数据或者根据二方库获取数据返回前端，剩下的逻辑前端做。
时间上，前后端可以并行开发，就像下面这张图一样。

## 什么是 RESTful API？

rest 指的是一组架构约束条件和原则，提供了一个新的架构设计思路，满足这些约束条件和原则的应用程序或设计就是 RESTful
接口名称用名词表示，操作用请求方法表示
GET - 查看
POST - 创建
PUT - 编辑
DELETE - 删除

## 为什么选择 iview 而不用 element

无可否认 element 生态更好吧
个人更喜欢 iview 的风格，偏小清新风格，api 比较简洁
在生成类似表格、下拉框这些较复杂的组件时 ， iview 的方式类似于 antdesign , 好处是直接传数据进去，在内部实现了模板生成，高效 快捷。 而 element 则是用到到 v-for vue 指令结合的方式去生成，批量生成元素
表格 操作列 自定义渲染的时 ，iview 使用的是 vue 的 render 函数， element 直接在 template 中插入对应模板

### element 的 bug

1. 表格不能显示 bool 值的 BUG

这是 elementUI 的 bug，单元格什么都不显示。官方说是不推荐直接显示布尔值，说是没什么意义。那么只能格式化了，但是如果你不想转换成什么“YES/NO”,"通过/未通过”，而是直接打印 ture/false 的话。那就是把 bool 值转成字符串返回就可以了。就是利用前面的 formatter。return String(cellValue)

2. 数据绑定带来的问题

对一行数据进行编辑，一般是把这一行数据获取到，然后复制给对话框绑定字段，然后在对话框内修改保存。但是，可能出现这种情况，即操作人修改了内容，但是没有保存而是取消了。由于对象的赋值是引用赋值，修改的就是这一行的绑定数据。这就带来问题了，即我明明没有保存，怎么表格那行数据却变了，这会给用户带来困惑。有一种方法是把这行的每个字段逐个复制给对话框绑定对象，这样比较麻烦，另一种就是深度拷贝，简单的做法就是 JSON.parse(JSON.stringify(xxx))。这样解析出来的就是一个全新的对象

## HTML5 新的特性 标签、API

## Promise try catch 捕获的是哪些类型的异常




面试标准
前端技术能力
沟通能力
学习主动性、培养潜力
通用计算机素养（算法、计算机网络等）
个人定位、职业规划


 面试流程以及各环节评分占比
1. 开场语（5）
2. 基础前端知识，主要考察原生js\html\css等前端知识（50分）
3. 沟通、理解能力、学习主动性、培养潜力（20分）
4. 项目，star法则讲解（15分）
6. 个人定位，职业规划（10分）
 各环节内容
 开场
1. 是如何选择前端这个方向的
2. 平时是如何提高自己技术能力
3. 目前对自己的前端技术评估
4. ...(待补充)

 技术考察
针对不同级别的人员，选择性的提问

1. 垂直水平居中
2. css怎么画不规则图形
3. css 选择器的优先级
4. 引用数据类型的深拷贝方式有哪些？
5. null 和undefined 的区别？
6. 浏览器事件循环机制
7. 前端页面性能优化
8. this、作用域区别
9. es6、es7
10. async\await实现，或者Promise的实现
11. 封装组件：自己封装过什么组件？组件的功能及优化点是什么？
12. 用过哪些第三方库？比如富文本、音视频处理等。
13. webpack打包机制？如何优化打包后资源的大小？
14. cookie前后端交互、localStorage、sessionStorage的区别？
15. http请求方式有哪些？opions是什么情况？
16. 跨域、跨域攻击
16. 前端资源清缓存的方式有哪些？
17. H5移动端适配方式有哪些？
18. vue路由模式、前端单页面路由跳转实现的原理是什么？
19. 线上故障处理：遇到过的已上线版本故障是什么？如何定位排查？如何快速解决？
19. ...(待完善)

项目相关
 1. 成长比较多的项目
 2. 项目解决了什么问题
 3. 遇到的难点
 4. 怎么解决的
 5. 学习和总结
 6. ...（待补充）


[一些面试题](https://zhuanlan.zhihu.com/p/48827292)
[前端面试指南](https://zhuanlan.zhihu.com/p/25859524)
