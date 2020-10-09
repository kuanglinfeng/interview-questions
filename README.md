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

```ts
var request = new XMLHttpRequest()
request.open('GET', '/xxx')
request.onreadystatechange = function () {
  if (request.readyState === 4) {
    console.log('请求完成')
    // ...
  }
}
request.send()
```

5. 必考：这段代码里的this是什么？

6. 必考：闭包/立即执行函数是什么？

7. 必考：什么是JSONP，什么是CORS，什么是跨域？

8. 常考：async/await怎么用，如何捕获异常？

9. 常考：如何实现深拷贝？

10. 常考：如何用正则实现trim() ?

11. 常考：不用class如何实现继承？用class又如何实现？

12. 常考：如何实现数组去重？

13. 放弃：== 相关题目（反着答）

14. 送命题：手写一个Promise


## DOM 

1. 必考：事件委托

代码：https://github.com/kuanglinfeng/interview-questions/blob/master/code/%E5%B0%81%E8%A3%85%E4%BA%8B%E4%BB%B6%E5%A7%94%E6%89%98.html

2. 曾考：用mouse事件写一个可拖动的div

代码：https://github.com/kuanglinfeng/interview-questions/blob/master/code/%E5%8F%AF%E6%8B%96%E5%8A%A8%E7%9A%84div.html




