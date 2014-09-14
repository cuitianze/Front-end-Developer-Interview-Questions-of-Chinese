#前端工作面试问题

[Rebecca Murphey](http://rmurphey.com/) 的 [Baseline For Front-End Developers](http://rmurphey.com/blog/2012/04/12/a-baseline-for-front-end-developers/) 是在准备面试前应该阅读的绝佳资源。

## <a name='toc'>目录</a>

  1. [最初的贡献者](#contributors)
  1. [常见问题](#general)
  1. [HTML 相关问题](#html)
  1. [CSS 相关问题](#css)
  1. [JS 相关问题](#js)
  1. [jQuery 相关问题](#jquery)
  1. [代码相关的问题](#jscode)
  1. [有趣的问题](#fun)
  1. [其他参考资料](#references)

####[[⬆]](#toc) <a name='contributors'>最初贡献者</a>

这里大部分的面试题来源于 [darcyclarke/Front-end-Developer-Interview-Questions](https://github.com/darcyclarke/Front-end-Developer-Interview-Questions), 摘抄自 [Paul Irish](http://paulirish.com) ([@paul_irish](http://twitter.com/paul_irish)) 在 [oksoclap](http://oksoclap.com/) 创建的帖子，部分问题由 [博陵](http://崔天泽.中国) 整理而来。

####[[⬆]](#toc) <a name='general'>常见问题：</a>

* 你在昨天/本周学到了什么？

* 编写代码的哪些方面能够使你兴奋或感兴趣？

* 在制作一个Web应用或Web站点的过程中，你是如何考虑他的UI、安全性、高性能、SEO、可维护性以及技术因素的？
	* UI：界面美观，要有个性，考虑用户使用的逻辑要简单，用起来舒适自由。使用习惯要符合大部分用户的习惯，比如少让用户输入，采用选择的方式，提供搜索和提示功能。
	* 安全性：对输入进行有效性验证（非法字符，特殊字符）如PHP中的方法htmlspecialchars()将特殊字符（>）转化为html实体，trim()去掉用户输入的不必要字符，stripslashes()去掉用户输入的反斜杠等等。
	* 对交互操作进行身份验证和授权（api-key,authtoken）,异常错误处理（向用户反馈单额错误提示不要让攻击者分析出一些网络环境和配置），内存溢出，注入攻击等。
	* 高性能：
		* DNS负载均衡
		* HTTP重定向（通过使客户端重定向，来分散和转移请求压力，比如一些下载服务通常都有几个镜像服务器）
	    * 分布式缓存
	    * 负载均衡：反向代理负载均衡,
	    * 数据库扩展：读写分离，垂直分区，水平分区。
	    * SEO:选好关键字，描述语言，修饰性图片换成文本，合理使用h1-h6，对图片添加alt属性，链接添加target属性。
	    * 可维护性：代码是否容易被理解，是否容易被修改和增加新的功能，当出现问题时是否能快速定位到问题代码。

* 谈谈你喜欢的开发环境。(例如操作系统，编辑器，浏览器，工具等等。)

* 你最熟悉哪一套版本控制系统？
	* GIT 版本控制常用命令汇总
		* git version 查看当前git版本信息
		* git help 获取全部命令帮助信息
		* git help \<command> 获取指定命令帮助信息
		* git config user.name "Your Name Comes Here"  设置当前项目git用户名
		* git config --global user.name "Your Name Comes Here"  设置全局项目git用户名
		* git config user.email you@yourdomain.example.com 设置当前项目git电子邮件
		* git config --global user.email you@yourdomain.example.com 设置全局项目git电子邮件
		* git config --list 显示当前项目设置参数
		* git config --global --list 显示全局项目设置参数
		* git init 初始化git仓库
		* git add \<fileName1> \<fileName2> ... 添加指定文件到索引
		* git add \<folderPath> 添加指定目录到索引
		* git add . 添加git目录下的所有文件到索引
		* git add --all 添加所有文件到索引
		* git rm \<folderPath/fileName> 删除指定文件
		* git status 查看当前本地库状态
		* git commit -m "commit message" 提交当前工作目录的修改内容，使用前需要先使用 
		* git status查看当前分支状态
		* git log 打印历史日志
		* git reset -hard \<branchName/tag/commitID> 返回指定的commit状态，包括本地文件
		* git reset -soft \<branchName/tag/commitID> 返回指定的commit状态，不包括本地文件
		* git branch 查看现在本地分支情况
		* git branch -r 查看服务器端分支情况
		* git branch \<branchName> 创建一个名为branchName的新分支
		* git branch -d \<branchName> 删除一个名为branchName的旧分支
		* git branch -m \<oldBranchName> <newBranchName> 将名为oldBranchName的分支名称修改为newBranchName
		* git branch -m \<newBranchName> 将正在工作分支名称修改为newBranchName
		* git checkout \<localBranchName> 切换到名为localBranchName的本地分支上		
		* git checkout \<remoteBranchName> 切换到名为remoteBranchName的远程分支上，此时未新建分支，而是处于一个名为no 
		* branch的临时分支上，还需要使用git branch -b 来创建一个新分支并将该临时分支挂接到新分支上
		* git checkout -b \<branchName> 创建一个名为branchName的新分支，并切换到该分支上
		* git merge \<branchName> 将名为branchName的分支合并到当前所处在的分支上
		* git pull 从服务器的仓库中获取代码，和本地代码合并
		* git push 将本地代码推送到服务器的仓库中
		* git push -f 强制将本地代码推送到服务器的仓库中，用来推送本地index和服务器index有矛盾的分支
		* git push origin --delete \<branchName> 删除名为branchName的远程分支
		* git clone \<userName>@\<serviceAddress>:\<serviceProjectDirectory/projectName> \<localProjectDirectory>/ 从服务器端克隆项目到本地

* 你能描述一下当你制作一个网页的工作流程吗？
	* 内容分析：分清展现在网络中内容的层次和逻辑关系
	* 结构设计：写出合理的html结构代码
	* 布局设计：使用html+css进行布局
	* 样式设计：首先要使用reset.css
	* 交互设计：鼠标特效。行为设计：js代码，ajax页面行为和从服务器获取数据。最后测试兼容性。优化性能

* 你能描述一下渐进增强和优雅降级之间的不同吗?
	* 何为渐进增强、优雅降级
		* 常用两种策略：要么优雅降级（graceful degradation，一开始就构建站点的完整功能，然后针对浏览器测试和修复），要么渐进增强（progressive enhancement，一开始只构建站点的最少特性，然后不断针对各浏览器追加功能。
	* 两者间的（微妙）差别
		* 万一你正挠着后脑勺，试图找出“优雅降级”和“渐进增强”之间的差别，那么我可以告诉你：“它们是看待同种事物的两种观点”。“优雅降级”和“渐进 增强”都关注于同一网站在不同设备里不同浏览器下的表现程度。关键的区别则在于它们各自关注于何处，以及这种关注如何影响工作的流程。
	* 如果提到了特性检测，可以加分。

* 请解释一下什么是“语义化的 HTML”。
	* 分离结构与表现的另一个重要方面是使用语义化的标记来构造文档内容。一个 XHTML 元素的存在就意味被标记内容的那部分有相应的结构化的意义，没有理由使用其他的标记。换句话说，不要让 CSS 使一个 HTML 元素看起来就像另一个 HTML 元素，比如用\<div>来代替\<p>标记标题。
	* 首先是关于语义（Semantics）和默认样式的区别，默认样式是浏览器设定的一些常用tag的表现形式，个人认为他的主要目的就是让大家直观的 认识标签(markup)和属性(attribute)的用途和作用，很明显Hx系列看起来很像标题，因为拥有粗体和较大的字号。\<strong>,\<em>用来区别于其他文字，起到了强调的作用。至于列表和表格很明显的告诉你他们是做什么的。
	* 其次，语义化的网页的好处，最主要的就是对搜索引擎友好，又了良好的结构和语义你的网页内容自然容易被搜索引擎抓取，你网站的推广便可以省下不少的功夫。

* 你如何对网站的文件和资源进行优化？
	* 期待的解决方案包括：
		* 文件合并
		* 文件最小化/文件压缩
		* 使用 CDN 托管
		* 缓存的使用
		* 其他

* 为什么利用多个域名来提供网站资源会更有效？
	* 浏览器同一时间可以从一个域名下载多少资源？

* 请说出三种减少页面加载时间的方法。（加载时间指感知的时间或者实际加载时间）

* 如果你参与到一个项目中，发现他们使用 Tab 来缩进代码，但是你喜欢空格，你会怎么做？
	* 建议这个项目使用像 EditorConfig (http://editorconfig.org/) 之类的规范
	* 为了保持一致性，接受项目原有的风格
	* 直接使用 VIM 的 retab 命令

* 请写一个简单的幻灯效果页面
	* 如果不使用JS来完成，可以加分。

* 你都使用哪些工具来测试代码的性能？
	* Profiler, JSPerf, Dromaeo

* 如果今年你打算熟练掌握一项新技术，那会是什么？

* Long-Polling, Websockets, SSE(Server-Sent Event) 之间有什么区别？

* 请谈一下你对网页标准和标准制定机构重要性的理解。

* 什么是 FOUC（无样式内容闪烁）？你如何来避免 FOUC？

* 请尽可能完整得描述下从输入URL到整个网页加载完毕及显示在屏幕上的整个流程

####[[⬆]](#toc) <a name='html'>HTML相关问题：</a>

* `doctype`（文档类型）的作用是什么？

* 浏览器标准模式和怪异模式之间的区别是什么？

* 使用 XHTML 的局限有哪些？
	* 如果页面使用 'application/xhtml+xml' 会有什么问题吗？

* 如果网页内容需要支持多语言，你会怎么做？
	* 在设计和开发多语言网站时，有哪些问题你必须要考虑？

* `data-`属性的作用是什么？

* 如果把 HTML5 看作做一个开放平台，那它的构建模块有哪些？

* 请描述一下 cookies，sessionStorage 和 localStorage 的区别？ 

* 请描述一下 `GET` 和 `POST` 的区别?

####[[⬆]](#toc) <a name='css'>CSS 相关问题：</a>

* 描述下 “reset” CSS 文件的作用和使用它的好处。

* 解释下浮动和它的工作原理。

* 列举不同的清除浮动的技巧，并指出它们各自适用的使用场景。

* 解释下 CSS sprites，以及你要如何在页面或网站中使用它。

* 你最喜欢的图片替换方法是什么，你如何选择使用。

* 讨论CSS hacks，条件引用或者其他。

* 如何为有功能限制的浏览器提供网页？
  * 你会使用哪些技术和处理方法？
  
* 有哪些的隐藏内容的方法（如果同时还要保证屏幕阅读器可用呢？）

* 你用过栅格系统吗？如果使用过，你最喜欢哪种？

* 你用过媒体查询，或针对移动端的布局/CSS 吗？

* 你熟悉 SVG 样式的书写吗？

* 如何优化网页的打印样式？

* 在书写高效 CSS 时会有哪些问题需要考虑？

* 使用 CSS 预处理器的优缺点有哪些？(SASS，Compass，Stylus，LESS)
  * 描述下你曾经使用过的 CSS 预处理的优缺点。
  
* 如果设计中使用了非标准的字体，你该如何去实现？
  * Webfonts (字体服务例如：Google Webfonts，Typekit 等等。)
  
* 解释下浏览器是如何判断元素是否匹配某个 CSS 选择器？

* 解释一下你对盒模型的理解，以及如何在 CSS 中告诉浏览器使用不同的盒模型来渲染你的布局。

* 请解释一下 ```* { box-sizing: border-box; }``` 的作用, 并且说明使用它有什么好处？

* 请罗列出你所知道的 display 属性的全部值

* 请解释一下 inline 和 inline-block 的区别？

* 请解释一下 relative、fixed、absolute 和 static 元素的区别

* 你目前在使用哪一套CSS框架，或者在产品线上使用过哪一套？(Bootstrap, PureCSS, Foundation 等等)
  * 如果有，请问是哪一套？如果可以，你如何改善CSS框架？

* 请问你有使用过 CSS Flexbox 或者 Grid specs 吗？
  * 如果有，请问在性能和效率的方面你是怎么看的？

####[[⬆]](#toc) <a name='js'>JS相关问题：</a>

* 解释下事件代理。

* 解释下 JavaScript 中 `this` 是如何工作的。

* 解释下原型继承的原理。

* 你是如何测试JavaScript代码的？

* AMD vs. CommonJS？

* 什么是哈希表？

* 解释下为什么接下来这段代码不是 IIFE(立即调用的函数表达式)：`function foo(){ }();`. 
  * 要做哪些改动使它变成 IIFE?
  
* 描述以下变量的区别：`null`，`undefined` 或 `undeclared`？
  * 该如何检测它们？
  
* 什么是闭包，如何使用它，为什么要使用它？

* 请举出一个匿名函数的典型用例？

* 解释 “JavaScript 模块模式” 以及你在何时使用它。
  * 如果有提到无污染的命名空间，可以考虑加分。
  * 如果你的模块没有自己的命名空间会怎么样？
  
* 你是如何组织自己的代码？是使用模块模式，还是使用经典继承的方法？

* 请指出 JavaScript 宿主对象和原生对象的区别？

* 指出下列代码的区别：
```javascript
function Person(){} 
var person = Person(); 
var person = new Person();
```

* `.call` 和 `.apply` 的区别是什么？

* 请解释 `Function.prototype.bind` 的作用？

* 你何时优化自己的代码？

* 你能解释一下 JavaScript 中的继承是如何工作的吗？

* 在什么时候你会使用 `document.write()`？
	* 大多数生成的广告代码依旧使用 `document.write()`，虽然这种用法会让人很不爽。

* 请指出浏览器特性检测，特性推断和浏览器 UA 字符串嗅探的区别？

* 请尽可能详尽的解释 AJAX 的工作原理。

* 请解释 JSONP 的工作原理，以及它为什么不是真正的 AJAX。

* 你使用过 JavaScript 模板系统吗？
	* 如有使用过，请谈谈你都使用过哪些库，比如 Mustache.js，Handlebars 等等。

* 请解释变量声明提升。

* 请描述下事件冒泡机制。

* "attribute" 和 "property" 的区别是什么？

* 为什么扩展 JavaScript 内置对象不是好的做法？

* 为什么扩展 JavaScript 内置对象是好的做法？

* 请指出 document load 和 document ready 两个事件的区别。

* `==` 和 `===` 有什么不同？

* 你如何从浏览器的 URL 中获取查询字符串参数。

* 请解释一下 JavaScript 的同源策略。

* 请描述一下 JavaScript 的继承模式。

* 如何实现下列代码：
```javascript
[1,2,3,4,5].duplicator(); // [1,2,3,4,5,1,2,3,4,5]
```

* 描述一种 JavaScript 中实现 memoization(避免重复运算)的策略。

* 什么是三元表达式？“三元” 表示什么意思？

* 函数的参数元是什么？

* 什么是 `"use strict";` ? 使用它的好处和坏处分别是什么？

####[[⬆]](#toc) <a name='jquery'>jQuery 相关问题：</a>

* 解释"chaining"。

* 解释"deferreds"。

* 你知道哪些针对 jQuery 的优化方法。

* 请解释 `.end()` 的用途。

* 你如何给一个事件处理函数命名空间，为什么要这样做？

* 请说出你可以传递给 jQuery 方法的四种不同值。
	* 选择器（字符串），HTML（字符串），回调函数，HTML元素，对象，数组，元素数组，jQuery对象等。

* 什么是效果队列？

* 请指出 `.get()`，`[]`，`eq()` 的区别。

* 请指出 `.bind()`，`.live()` 和 `.delegate()` 的区别。

* 请指出 `$` 和 `$.fn` 的区别，或者说出 `$.fn` 的用途。

* 请优化下列选择器：
```javascript
$(".foo div#bar:eq(0)")
```

####[[⬆]](#toc) <a name='jscode'>代码相关的问题：</a>

```javascript
modulo(12, 5) // 2
```

问题：实现满足上述结果的modulo函数

```javascript
"i'm a lasagna hog".split("").reverse().join("");
```

问题：上面的语句的返回值是什么？
**答案："goh angasal a m'i"** 

```javascript
( window.foo || ( window.foo = "bar" ) );
```

问题：window.foo 的值是什么？
**答案："bar"**
只有 window.foo 为假时的才是上面答案，否则就是它本身的值。

```javascript
var foo = "Hello"; (function() { var bar = " World"; alert(foo + bar); })(); alert(foo + bar);
```

问题：上面两个 alert 的结果是什么
**答案: "Hello World" 和 ReferenceError: bar is not defined** 

```javascript
var foo = [];
foo.push(1);
foo.push(2);
```

问题：foo.length 的值是什么？
**答案：`2`**

####[[⬆]](#toc) <a name='fun'>有趣的问题：</a>

* 你编写过的最酷的代码是什么？其中你最自豪的是什么？

* 在你使用过的开发工具中，最喜欢哪个？

* 你有什么业余项目吗？是哪种类型的？

* 你最爱的 IE 特性是什么？

####[[⬆]](#toc) <a name='references'>其他参考资料：</a>

* http://programmers.stackexchange.com/questions/46716/what-technical-details-should-a-programmer-of-a-web-application-consider-before
* http://www.nczonline.net/blog/2010/01/05/interviewing-the-front-end-engineer/
* http://css-tricks.com/interview-questions-css/
* http://davidshariff.com/quiz/
* http://blog.sourcing.io/interview-questions