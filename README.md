# 技巧

1. 遇到比较抽象的题目就具体化（举例），遇到比较具体的题目就抽象化（阐述）
2. 抽象题目搜知乎，代码题目搜Stackoverflow或博客
3. 「xxx的原理」这种题目一般都是说源代码思路，但你不需要看源代码，直接看别人的博客即可（不要用百度）

为什么要反着答呢？因为可以差异化，使你和别人不一样。

## HTML

1. 必考：你是如何理解HTML语义化的

荒野阶段：

后端来写HTML，table标签布局，导致页面虽然做出来很快，但是后期维护很难，往往会出现table套table的窘境

美工阶段：

有一部分人来专门来写html和css，DIV+CSS布局，在div上加class
这种方式没问题，但是不够语义化，不知道这个div和那个div有什么区别

前端阶段：

有一帮人以前端号称用正确的标签，该用h1用h1该用article用article

我呢就是了解了这三种之后，觉得前面这种不够正确，div+css还是不够语义化，只有第三种用合适地标签来描述内容才是正确的写法


2. meta viewport是做什么用的，怎么写？


3. 你用过那些HTML5标签？

布局：header、 main、 footer、 article
功能：canvas、video、audio（会被问一连续的问题，找MDN）

4. H5是什么？

反正指的不是HTML5


## CSS

1.必考： 两种盒模型分别说一下

border-box和content-box

拔高：为什么会有新的盒模型？（关键词，更方便）

2. 必考：如何垂直居中？

分情况讨论

参考答案：https://jscode.me/t/topic/1936/2

3. 必考：flex怎么用，常用属性有哪些？


4. 必考：BFC是什么？

举例子，举几个含有BFC的例子

5. CSS选择器优先级

- 越具体优先级越高
- 写在后面的覆盖写在前面的
- !important 最高，少用

6. 清除浮动说一下

```css
.clearfix::after {
  display: block;
  content: '';
  clear: both;
}
```

## 原生JS

1. 必考：ES6语法有哪些，分别怎么用？

举例：let、const、class、展开运算符等

2.必考Promise、Promise.all、Promise.race分别怎么用

举例：

3. 必考：手写函数防抖和函数节流

代码：https://github.com/kuanglinfeng/interview-questions/blob/master/code/%E5%87%BD%E6%95%B0%E9%98%B2%E6%8A%96%E5%92%8C%E8%8A%82%E6%B5%81.html

4. 必考：手写AJAX

代码：https://github.com/kuanglinfeng/interview-questions/blob/master/code/%E5%B0%81%E8%A3%85ajax.html

5. 必考：这段代码里的this是什么？

6. 必考：闭包/立即执行函数是什么？

7. 必考：什么是JSONP，什么是CORS，什么是跨域？

8. 常考：async/await怎么用，如何捕获异常？

9. 常考：如何实现深拷贝？

10. 常考：如何用正则实现trim() ?

```ts
String.prototype.myTrim = function (string) {
  return this.replace(/^\s+|\s+$/g, '')
}
```

11. 常考：不用class如何实现继承？用class又如何实现？

- 不使用class（ES5）

```ts
function Father(lastName) {
  this.lastName = lastName
}

Father.prototype.walk = function () {
  console.log('walk in park')
}

function Son(firstName, lastName) {
  Father.call(this, lastName)
  this.firstName = firstName
}

const F =  function () {}
F.prototype = Father.prototype
Son.prototype = new F()
Son.prototype.constructor = Son

Son.prototype.say = function () {
  console.log(`my name is ${this.firstName} ${this.lastName}`)
}
const son = new Son('Flinn', 'Kuang')
son.walk()
son.say()
```

- 使用class（ES6）

```ts
class Father {
  constructor(lastName) {
    this.lastName = lastName
  }
  walk() {
    console.log('walk in park')
  }
}

class Son extends Father {
  constructor(firstName, lastName) {
    super(lastName)
    this.firstName = firstName
  }
  say() {
    console.log(`my name is ${this.firstName} ${this.lastName}`)
  }
}

const son = new Son('Flinn', 'Kuang')
son.walk()
son.say()
```

12. 常考：如何实现数组去重？

13. 放弃：== 相关题目（反着答）

14. 送命题：手写一个Promise


## DOM 

1. 必考：事件委托

代码：https://github.com/kuanglinfeng/interview-questions/blob/master/code/%E5%B0%81%E8%A3%85%E4%BA%8B%E4%BB%B6%E5%A7%94%E6%89%98.html

2. 曾考：用mouse事件写一个可拖动的div

代码：https://github.com/kuanglinfeng/interview-questions/blob/master/code/%E5%8F%AF%E6%8B%96%E5%8A%A8%E7%9A%84div.html

## HTTP

1. 必考：HTTP状态码有哪些？分别什么意思？

2. 必考：HTTP缓存有哪几种？

Etag：MD5
Expire：日期，有bug，受用户本机时间控制，用户如果调了本机时间，就容易有bug
Cache-Control：max-age=600

Expire和Cache-Control，一个是某个时间点过期，一个是过了某段时间后过期
ETag和Cache-Control：一个有请求（304），一个无请求

3. 必考：GET 和 POST的区别

错误答案（95%以上面试认可）：
1. post 安全 get 不安全
2. get有长度限制 post没有长度限制
3. get参数是放在url里面，post是放在消息体里面
4. get只需要一个报文，post需要两个以上
5. get幂等，post是不幂等的

正确答案：
语义：get是获取数据，post是提交数据

4. Cookie VS LocalStorage VS SessionStorage VS Session

cookie: 服务器发给浏览器的一段字符串，浏览器在每次访问服务器时要带上这段字符串
session：会话，表示浏览器与服务器一段时间内的会话
区别：session在服务器上，cookie在浏览器上，session一般是基于cookie来实现的，session-id放到cookie里面

cookie 和 LocalStorage区别：

- 大小限制：cookie 4k，LocalStorage 5M
- cookie用来存用户信息，localStorage存一些无关紧要的信息
- cookie发送到服务器上，localStorage不发送到服务器上

sessionStorage 和 LocalStorage

- sessionStorage在会话接收的时候过期，localStorage不会过期

## Vue

1. 必考：watch和computed的区别？

一个监听属性，记个计算属性
watch没有缓存，computed有缓存


2. 必考：Vue有哪些生命周期钩子函数？分别有什么用？


3. 必考：Vue如何实现组件间通信？

- 父子组件：$emit('xxx', data) $on('xxx', () => {})
- 爷孙组件、兄弟组件：eventBus
- 更复杂的情况：vuex

4. 必考：Vue数据响应式是怎么做到的

5. 必考：Vue.set是做什么用的？

6. Vuex你怎么用的？

7. VueRouter你怎么用的?

8. 路由守卫是什么？

## 框架React

1. 必考：受控组件 vs 非受控组件

2. 必考：React有哪些生命周期函数？分别有什么用？

3. 必考：React如何实现组件间通信？

4. 必考：shouldComponentUpdate有什么用？

5. 必考：虚拟DOM是什么？

6. 必考：什么是高阶组件？

7. React diff的原理是什么？

8. 必考：Redux是什么？

9. connect的原理是什么？

## TypeScript

1. never类型是什么？
2. TypeScript比起JavaScript有什么优势？

## Webpack

相关面试题答案链接：https://zhuanlan.zhihu.com/p/44438844

1. 必考：有哪些常见loader和plugin，你用过哪些？

loader：

html: pug-loader markdown-loader
css: postcss-loader scss-loader less-loader style-loader
js: babel-loader eslint-loader
图片：svg-sprite-loader

plugin:

html: html-webpack-plugin
css: extract-text-plugin


2. 英语题：loader和plugin的区别是什么？

loader一般用来加载文件
plugin添加一些附加功能

3. 必考：如何按需加载代码？

import()

4. 必考：如何提高构建速度？

loader：happypack 可以进行多核cpu进行打包
plugin: DllPlugin

5. 转义出的文件过大怎么办？

提取通用模块代码
压缩js、css、图片
按需加载

## 安全

1. 必考：什么是XSS？如何预防？
2. 必考：什么是CSRF？如何预防？

## 开放题

1. 必考：你遇到最难的问题是怎样的？
2. 你在团队的突出贡献是什么？
3. 最近在关注什么新技术？
4. 有没有看什么源码，看了后有什么记忆深刻的地方，有什么收获？

## 刁钻题
1. 代码
```js
[1, 2, 3].map(parseInt)
//[ 1,NaN, NaN]
// parseInt(1, 0)  以0进制将1转为数字
// parseInt(2, 1)  以1进制将2转为数字
// parseInt(3, 2)  以2进制将3转为数字
```
 
2. 代码
```js
var a = {name: 'a'}
a.x = a = {}
// a.x是多少？
// 答案：undefined
// a.x中的a指向的是{name: 'a'}的地址
// a = {} 是新的地址
```

3. 代码
```js
// (a == 1 && a == 2 && a == 3)可能为ture吗？重写toString
```

## 超纲题

1. JS垃圾回收机制

- 什么是垃圾

一般来说，没有被引用的对象就是垃圾，有一个例外是如果某几个对象互相引用成环但是这个环没有被全局变量引用，那么这整个环的对象都是垃圾

- 如何捡垃圾（遍历和计数，只是不同的算法而已）

算法有很多，其中的两种是：标记清除算法，引用计数算法

标记清除算法：从全局变量开始一层一层往下标记，所有被标记到的就是不要清除的，没有被标记的就是要被清除的

引用计数算法：一个对象每次被创建一个引用时就加1，再创建时就再加1，移除一个引用时就减1，如果最后引用数为0，那么就会被清除

- 前端又有其特性（JS进程和DOM进程）

```js
const div = document.querySelector('xxx')

div.onclick = function () {}

// 仅删除dom对象
setTimeout(() => {
  div.remove() // 只是页面上的dom被移除，js进程依然可以引用
  // console.log(div.onclick) // 依然可以输出
}, 1000)

// 仅删除js对象
setTimeout(() => {
  div = null // 只是div所有指向的对象被移除，dom依然可以被点击，说明div.onclick没有被清除
}, 1000)

// 同时删除js和dom对象
setTimeout(() => {
  div.remove()
  div = null // 按理说应该div.onclick应该被清除了，但是ie有bug，ie必须 div.onclick = null 才认
}, 1000)
```

2. EventLoop

面试题：

```js
async function async1() {
  console.log(1)
  await async2() // Promise.resolve(async2())
  console.log(2)
}
async function async2() {
  console.log(3)
  // 相当于
  // return new Promise((resolve, reject) => {
  //  console.log(3)
  //  resolve(undefined)
  // })
}
async1()

new Promise((resolve) => {
  console.log(4)
  resolve()
}).then(() => {
  console.log(5)
})
// 1 3 4 2 5
```




