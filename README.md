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
  1. [其他问题](#other)
  1. [推荐网站](#web)

#### [阿里寒冬面试题](http://blog.csdn.net/dyllove98/article/details/8981433)
#### [视觉格式化模型](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Visual_formatting_model)

####[[⬆]](#toc) <a name='contributors'>最初贡献者</a>

这里大部分的面试题来源于 [darcyclarke/Front-end-Developer-Interview-Questions](https://github.com/darcyclarke/Front-end-Developer-Interview-Questions), 摘抄自 [Paul Irish](http://paulirish.com) ([@paul_irish](http://twitter.com/paul_irish)) 在 [oksoclap](http://oksoclap.com/) 创建的帖子，部分问题由 [博陵](http://崔天泽.中国) 整理而来。

####[[⬆]](#toc) <a name='general'>常见问题：</a>

* 你在昨天/本周学到了什么？

* 编写代码的哪些方面能够使你兴奋或感兴趣？
	* 在完成功能的同时精良多考虑性能，安全性，兼容性，代码的扩展性。

* 线程与进程的区别 
	* 一个程序至少有一个进程,一个进程至少有一个线程. 
	* 线程的划分尺度小于进程，使得多线程程序的并发性高。 
	* 另外，进程在执行过程中拥有独立的内存单元，而多个线程共享内存，从而极大地提高了程序的运行效率。 
	* 线程在执行过程中与进程还是有区别的。每个独立的线程有一个程序运行的入口、顺序执行序列和程序的出口。但是线程不能够独立执行，必须依存在应用程序中，由应用程序提供多个线程执行控制。 
	* 说从逻辑角度来看，多线程的意义在于一个应用程序中，有多个执行部分可以同时执行。但操作系统并没有将多个线程看做多个独立的应用，来实现进程的调度和管理以及资源分配。这就是进程和线程的重要区别。

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
	* Mac(windows),sublime,Chrome, IEtest,xshell

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
	* 巅峰的回答
		* 检测浏览器，渐进增强就是让牛b的浏览器的效果更好
		* 优雅降级就是让2b的浏览器在功能ok的情况下效果一般。
	* 何为渐进增强、优雅降级
		* 常用两种策略：要么优雅降级（graceful degradation，一开始就构建站点的完整功能，然后针对浏览器测试和修复），要么渐进增强（progressive enhancement，一开始只构建站点的最少特性，然后不断针对各浏览器追加功能。
	* 两者间的（微妙）差别
		* 万一你正挠着后脑勺，试图找出“优雅降级”和“渐进增强”之间的差别，那么我可以告诉你：“它们是看待同种事物的两种观点”。“优雅降级”和“渐进 增强”都关注于同一网站在不同设备里不同浏览器下的表现程度。关键的区别则在于它们各自关注于何处，以及这种关注如何影响工作的流程。
	* 如果提到了特性检测，可以加分。

	* 另一种回答
		* 要么优雅降级（graceful degradation，一开始就构建站点的完整功能，然后针对浏览器测试和修复），
		* 要么渐进增强（progressive enhancement，一开始只构建站点的最少特性，然后不断针对各浏览器追加功能。
		* GD和PE的区别在于：功能衰减是从复杂的现状开始，并试图减少用户体验的供给，而渐进增强则是从一个非常基础的，能够起作用的版本开始，并不断扩充，以适应未来环境的需要。功能衰减意味着往回看；而渐进增强则意味着朝前看，同时保证其根基处于安全地带。
		* 特性检测，window.innerWidth/document.documentElement.clientWidth

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
	* 三个最主流的原因: 
		1. CDN缓存更方便
		2. 突破浏览器并发限制 (你随便挑一个 G家的 url: https://lh4.googleusercontent.com/- si4dh2myPWk/T81YkSi__AI/AAAAAAAAQ5o/LlwbBRpp58Q/w497-h373/IMG_20120603_163233.jpg, 把前面的 lh4换成 lh3,lh6 啥的，都照样能够访问，像地图之类的需要大量并发下载图片的站点，这个非常重要。)
		3. Cookieless, 节省带宽，尤其是上行带宽 一般比下行要慢。。。
		还有另外两个非常规原因: 
		4. 对于UGC的内容和主站隔离，防止不必要的安全问题( 上传js窃取主站cookie之类的) 。 
		 正是这个原因要求用户内容的域名必须不是自己主站的子域名，而是一个完全独立的第三方域名。
		5. 数据做了划分，甚至切到了不同的物理集群，通过子域名来分流比较省事. ^_^ 这个可能被用的不多。
		PS: 关于Cookie的问题，带宽是次要的，安全隔离才是主要的。
	* 关于多域名，也不是越多越好，虽然服务器端可以做泛解释，浏览器做dns解释也是耗时间的，而且太多域名，如果要走 https的话，还有要多买证书和部署的问题，^_^。
	* Browser	Max Connections / Host
	* Chrome 1.0	6
	* Chrome 2.0	6
	* Firefox 3.0	6
	* Firefox 3.5	6
	* IE 6	2
	* IE 7	2
	* IE 8	6
	* Safari 3.2	4
	* Safari 4.0	4

* 请说出三种减少页面加载时间的方法。（加载时间指感知的时间或者实际加载时间）
	* 1). 尽量减少页面中重复的HTTP请求数量
    * 2). 服务器开启gzip压缩
    * 3). css样式的定义放置在文件头部
    * 4). Javascript脚本放在文件末尾
    * 5). 压缩Javascript、CSS代码
    * 7). 尽可能减少DCOM元素
    * 8). 使用多域名负载网页内的多个文件、图片
    * 9). 使用CDN
 	* 10). 在服务器端配置control-cache last-modify-date
 	* 11). 在服务器配置Entity-Tag if-none-match

* 23条Web性能优化最佳实践和规则
	* 1.尽可能减少HTTP请求次数
	* 2.使用CDN
	* 3.避免使用src和href标签
	* 4.加入Expires或Cache-Control Header
	* 5.使用Gzip压缩
	* 6.在html文件顶部放置样式表
	* 7.在html文件底部放置Javascript脚本
	* 8.避免使用CSS表达式
	* 9.使用外部Javascript和CSS外部文件
	* 10.减少使用DNS查找次数
	* 11.精简Javascript和CSS
	* 12.避免重定向
	* 13.移除重复的脚本
	* 14.配置ETag
	* 15.缓存AJAX
	* 16.使用GET完成AJAX请求
	* 17.减少DOM元素数量
	* 18.避免404
	* 19.减少Cookie大小
	* 20.使用无Cookie的域
	* 21.避免使用滤镜
	* 22.不要在HTML中缩放图片
	* 23.使用小favicon.ico文件，并让其可缓存

* 衡量网页性能的指标
	* DNS解析时间
	* TCP链接时间
	* HTTP重定向时间
	* 首字节加载时间
	* HTML内容时间
	* 整个页面对象加载时间
	 * 具体说明
	 	* DNS解析时间
			* DNS查找的时间就是将域名翻译成具体IP的时间，大多人数认为，无论DNS是否工作，都不是件简单的事情。
			* 在这个过程中，你可能会遇到许多微妙的问题，比如响应时间太长、超时、无效的缓存等。这些情况下，一个查询便可通过，但它需要花费更多的时间。
			* 通常，如果DNS的查找时间过长，那么意味着你或托管服务商的DNS服务有问题。记住，如果网站与其DNS服务之间距离太远，那么解析时间也会稍微增加，这在一些国际网站上会体现出来，而有效的缓存则会降低时间。
		* TCP链接时间
			* 当URL被解析成一个IP地址后，TCP链接时间表示客户端链接到服务端所花费的时间。监控链接时间有助于开发者发现一些影响响应时间的问题，比如网络延时、路由问题、服务器宽带问题等。
			* 例如，如果宽带服务器不足以处理工作负载，那么客户端要先与服务器端意识到这个问题，当客户端向服务器端发送请求时，可能会被拒绝或者时间超时、响应时间延迟等问题。
		* HTTP重定向时间
			* HTTP重定向时间主要是指TCP链接完成时间，它意味着发送初始通知到重定向网站并且浏览器最终定向到目标网站所花费的时间。如果没有重定向，那么重定向时间就为0。它包括了DNS解析时间、TCP链接等等。
			* HTTP重定向可用于缩短URL、当网页链接移动时，可用于防止链接损坏，或允许多个域名链接到一个网站上。
		* 首字节加载时间
			* 当开发人员思考如何优化网站时，往往会选择优化内容——文件组合、多媒体优化、缓存和压缩文件，但也有需要对服务器进行优化。其中一个最佳指标就是首字节的加载时间，首字节加载时间表示从链接创建到首字节成功转换所花费的时间。这个时间也包括了服务器执行各种协议和计算的时间。
			* 通常服务器端遇到与首字节相关的问题包括内存泄露、程序派生的进程太多——没有完全关闭——低效SQL查询，并且调用外部资源，例如谷歌和Facebook。
		* HTML内容时间
			* HTML内容时间主要包括加载Web页面布局、CSS、JavaScript，这个时间与HTML页面的大小有着直接的关系。HTML内容加载时间通常会作为衡量宽带的一个指标，但也不完全是。
		* 整个页面对象加载时间
			* 一旦整个HTML内容被整个接收，浏览器会解析所有的页面对象，并且直到所有对象加载完毕。这些对象包括图片、JavaScript、CSS、Flas对象、RSS回馈、JavaScript文件等。
			* 衡量全页加载时间对监控第三方内容非常有用，特别是广告，但它并不会告诉你有哪些用户看了这个广告。例如，它不会告诉你第三方内容放在哪加载速度会快些。但站在用户角度来看，这些并不算问题。

* 如果你参与到一个项目中，发现他们使用 Tab 来缩进代码，但是你喜欢空格，你会怎么做？
	* 建议这个项目使用像 EditorConfig (http://editorconfig.org/) 之类的规范
	* 为了保持一致性，接受项目原有的风格
	* 直接使用 VIM 的 retab 命令

* 请写一个简单的幻灯效果页面
	* 如果不使用JS来完成，可以加分。
```html
<!doctype html>
<html>
  <head>
    <style>
    img {
      display: none;
      width: 100px;
      height: 100px;
    }
 
    input:checked + img {
      display: block;
    }
 
    input {
      position: absolute;
      left: -9999px;
    }
 
    label {
      cursor: pointer;
    }
    </style>
  </head>
  <body>
    <div id="cont">
      <input id="img1" name="img" type="radio" checked="checked">
      <img src="a.png">
      <input id="img2" name="img" type="radio">
      <img src="b.png">
    </div>
    <div id="nav">
      <label for="img1">第一张</label>
      <label for="img2">第二张</label>
    </div>
  </body>
</html>
```

	* 还有用hash的方法,就是利用地址后面的#abc。

```html
<!DOCTYPE HTML>
<html>
  <head>
  <style>
 
  #cont {
  position: relative;
  height: 100px;
  }
img {
      position: absolute;
      width: 100px;
      height: 100px;
      z-index: 1;
    }
img:first-child,
img:target {
      z-index: 2;
    }
 
 
  </style>
  </head>
  <body>
  <div id="cont">
      <img id="img1" src="a.jpg">
      <img id="img2" src="b.jpg">
    </div>
    <div>
      <a href="#img1">one</a>
      <a href="#img2">two</a>
    </div>
  </body>
</html>
```

* 你都使用哪些工具来测试代码的性能？
	* [Profiler](http://www.2cto.com/kf/201204/126311.html), [JSPerf](http://jsperf.com/nexttick-vs-setzerotimeout-vs-settimeout), Dromaeo

* 如果今年你打算熟练掌握一项新技术，那会是什么？
	* nodejs, Famo.us

* Long-Polling, Websockets, SSE(Server-Sent Event) 之间有什么区别？
	* [Long-Polling, Websockets, SSE(Server-Sent Event), WebRTC 之间的区别](http://www.vipaq.com/Article/View/blog/419.html)

* 请谈一下你对网页标准和标准制定机构重要性的理解。
	* 让浏览器兼容性的问题尽量小，对浏览器的开发者的约束，也是对web开发者的约束。

* 什么是 FOUC（无样式内容闪烁）？你如何来避免 FOUC？
	* 如果使用import方法对CSS进行导入,会导致某些页面在Windows 下的Internet Explorer出现一些奇怪的现象:以无样式显示页面内容的瞬间闪烁,这种现象称之为文档样式短暂失效(Flash of Unstyled Content),简称为FOUC。
    * 原因大致为：
    	*　1，使用import方法导入样式表。
		* 2，将样式表放在页面底部
		* 3，有几个样式表，放在html结构的不同位置。
	* 其实原理很清楚：
		* 当样式表晚于结构性html加载，当加载到此样式表时，页面将停止之前的渲染。此样式表被下载和解析后，将重新渲染页面，也就出现了短暂的花屏现象。
	* 解决方法：
		* 使用LINK标签将样式表放在文档HEAD中。

* 请尽可能完整得描述下从输入URL到整个网页加载完毕及显示在屏幕上的整个流程
	* 1）把URL分割成几个部分：协议、网络地址、资源路径。其中网络地址指示该连接网络上哪一台计算机，可以是域名或者IP地址，可以包括端口号；协议是从该计算机获取资源的方式，常见的是HTTP、FTP，不同协议有不同的通讯内容格式；资源路径指示从服务器上获取哪一项资源。
	例如：http://www.guokr.com/question/554991/
	协议部分：http
	网络地址：www.guokr.com
	资源路径：/question/554991/
	* 2）如果地址不是一个IP地址，通过DNS（域名系统）将该地址解析成IP地址。IP地址对应着网络上一台计算机，DNS服务器本身也有IP，你的网络设置包含DNS服务器的IP。
	例如：www.guokr.com 不是一个IP，向DNS询问请求www.guokr.com 对应的IP，获得IP： 111.13.57.142。这个过程里，你的电脑直接询问的DNS服务器可能没有www.guokr.com 对应的IP，就会向它的上级服务器询问，上级服务器同样可能没有，就依此一层层向上找，最高可达根节点，找到或者全部找不到为止。
	* 3）如果地址不包含端口号，根据协议的默认端口号确定一个。端口号之于计算机就像窗口号之于银行，一家银行有多个窗口，每个窗口都有个号码，不同窗口可以负责不同的服务。端口只是一个逻辑概念，和计算机硬件没有关系。
	例如：www.guokr.com 不包含端口号，http协议默认端口号是80。如果你输入的url是http://www.guokr.com:8080/ ，那表示不使用默认的端口号，而使用指定的端口号8080。
	* 4）向2和3确定的IP和端口号发起网络连接。
	例如：向111.13.57.142的80端口发起连接
	* 5）根据http协议要求，组织一个请求的数据包，里面包含大量请求信息，包括请求的资源路径、你的身份
	例如：用自然语言来表达这个数据包，大概就是：请求 /question/554991/ ，我的身份是xxxxxxx。
	* 6）服务器响应请求，将数据返回给浏览器。数据可能是根据HTML协议组织的网页，里面包含页面的布局、文字。数据也可能是图片、脚本程序等。现在你可以用浏览器的“查看源代码”功能，感受一下服务器返回的是什么东东。如果资源路径指示的资源不存在，服务器就会返回著名的404错误。
	* 7）如果（6）返回的是一个页面，根据页面里一些外链的URL，例如图片的地址，按照（1）－（6）再次获取。
	* 8）开始根据资源的类型，将资源组织成屏幕上显示的图像，这个过程叫渲染，网页渲染是浏览器最复杂、最核心的功能。
	* 9）将渲染好的页面图像显示出来，并开始响应用户的操作。
	以上只是最基本的步骤，实际不可能就这么简单，一些可选的步骤例如网页缓存、连接池、加载策略、加密解密、代理中转等等都没有提及。即使基本步骤本身也有很复杂的子步骤，TCP/IP、DNS、HTTP、HTML：每一个都可以展开成庞大的课题，而浏览器的基础——操作系统、编译器、硬件等更是一个比一个复杂。不是计算机专业的同学看了上面的解释完全不明白是很正常的，可能会问为什么要搞得那么复杂，但我保证这每一个步骤都经过深思熟虑和时间的考验。你输入URL即可浏览互联网，而计算机系统在背后做了无数你看不到的工作，计算机各个子领域无数工程师为此付出你难以想象的努力。

####[[⬆]](#toc) <a name='html'>HTML相关问题：</a>

* `doctype`（文档类型）的作用是什么？
	* doctype是DocumentType的简称即文档类型，doctype声明位于文档中最前面的位置，处于标签之前，告知浏览器使用的是哪种规范。

* 有多少种文档类型？
    * 常见的文档类型有 Strict、Transitional 以及 Frameset 三种。

* 文档为什么要分类型？
	* 如果文档不分类型，各浏览器就会形成多种写法，假如IE用`<title>`标签作为标题、火狐浏览器用`<caption>`标签作为标题，而另一种浏览器可能采用`<mytitle>`，这对于开发者和用户来说简直是灾难。W3C（万 维网联盟World Wide Web Consortium）制作了对所有方面都平衡的分歧解决方案，并且各浏览器没有异议，于是用`<!doctype>`（注意：作为一个特殊的标 签，它是不需要闭合的）标签来引入W3C的dtd文件，以达到规范页面的效果。这为浏览器的文档标准的统一以及开发人员和用户带了了便利。而html5不是基于SGML实现的，因此html不需要引入DTD，所以html5可以简单的声明一下`<!doctype html>`。

* 如果不声明doctype？
	* 不写doctype，浏览器会进入quirks mode （混杂模式）。即，如果不声明doctype，浏览器不引入w3c的标准，那么早期的浏览器会按照自己的解析方式渲染页面。浏览器采用自身方式解析页面的行为称为"quirks mode（混杂模式也称怪异模式）"；采用w3c方式解析就是"strict mode（标准模式）"。 如果完全采用strictmode就不会出任何的差错，但这样会降低程序的容错率，加重开发人员的难度，因此在standards mode 里面分出来 Almost Standards Mode(接近标准模式）。

* 浏览器标准模式和怪异模式之间的区别是什么？
	* 标准模式：浏览器根据规范呈现页面
	* 混杂模式（怪异模式）：页面以一种比较宽松的兼容方式显示。
		* 他们最大的不同是对盒模型的解析。
			* 如：在strict mode中 ：width是内容宽度 ，也就是说,元素真正的宽度 = margin-left + border-left-width + padding-left + width + padding-right + border-right- width +  margin-right;
			* 在quirks mode中 ：width则是元素的实际宽度 ，内容宽度 = width - (margin-left + margin-right + padding-left + padding-right + border-left-width + 　border-right-width)

* 使用 XHTML 的局限有哪些？
	* XHTML较为严格，标签必须闭合，必须要body，head等
* 如果页面使用 'application/xhtml+xml' 会有什么问题吗？
	* 一些老的浏览器并不兼容，IE876不支持。

* 如果网页内容需要支持多语言，你会怎么做？
	* 采用统一编码UTF-8模式
	* 在设计和开发多语言网站时，有哪些问题你必须要考虑？
		*  
			1、应用字符集的选择
			2、语言书写习惯&导航结构 
			3、数据库驱动型网站
	    1、应用字符集的选择
		    一个定位于不同语言国家的企业网站势必需要提供多种语言版本的产品和销售信息来满足其世界各地使用不同语言的客户和合作伙伴，其中包括法语、德语、意大利语、葡萄牙语、西班牙语、阿拉伯语等等。但有一个问题却极易被网站设计者们所忽略。这就是网站的字符集设置问题。
		    一般我们使用的是简体中文(GB2312)字符集，而对多语言网站来说，中文字符集却可能会使你辛辛苦苦的努力功亏一篑。原因很简单：就是这个毫不起眼的小小字符集在作怪。
		    计算机应用领域中存在着几十种互不相同的字符集，而不同语言客户在浏览不同语言网页时，往往会因为相互间所使用字符集无法兼容而出现乱码情况。我们在浏览国外一些网站时，往往也会出现为了能正常地看到网站上的信息而不得不在各种字符集之间来回切换的情况。
		    试想一下：如果一个网站提供了中、英、法、德等多种语言版本的内容，内容全之又全，设计美仑美奂。我们在中文编码环境下浏览这些非中文版本的页面觉得非常完美，现在一个法国客户对你的产品发生了兴趣，当他进到法语版面一看，乱码多多，甚至可能整个版面都一塌里糊涂。你的网站再下大工夫又有什么意义呢?
		    所以对提供了多语言版本的网站来说，Unicode字符集应该是最理想的选择。它是一种双字节编码机制的字符集，不管是东方文字还是西方文字，在Unicode中一律用两个字节来表示，因而至少可以定义65536个不同的字符，几乎可以涵盖世界上目前所有通用的语言的每一种字符。所以在设计和开发多语言网站时，一定要注意先把非中文页面的字符集定义为“utf-8”格式，即：
		    √: <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
		    ×: <meta http-equiv="Content-Type" content="text/html; charset=gb2312"> 
		    这一步非常重要，原因在于若等页面做好之后再更改字符集设置，可说是一件非常非常吃力不讨好的工作，有时候甚至可能需要从头再来，重新输入网站的文字内容。
		* 2、语言书写习惯&导航结构
		    有些国家的语言书写习惯是从右到左，例如许多中东地区所使用的阿拉伯语，波斯语和希伯来语等等。如果你的市场目标是这些语言的国家，那么在网站设计中就需要考虑这些特殊的语言书写习惯。而且如果你在网站导航结构设计中使用的是一个竖直导航栏，这时候就应该把它放在右边，而不是象我们习惯的那样放在左边了。
		* 3、数据库驱动型网站
		    对一个数据库驱动型的网站，尤其是当客户可以留言并向数据库添加信息时，则应当考虑如何从技术上实现对不同语言数据信息的收集和检索。

* `data-`属性的作用是什么？
	* data-为前端开发者提供自定义的属性，这些属性集可以通过对象的dataset属性获取，不支持该属性的浏览器可以通过 getAttribute方法获取。ppk提到过使用rel属性，lightbox库推广了rel属性，HTML5提供了data-做替代，这样可以更好 地使用自定义的属性。
```html
<div data-author="david" data-time="2011-06-20"
          data-comment-num="10"  data-category="javascript">
....
</div>
```

	* 上面HTML代码提供了单个文章所拥有的一些属性。通过JS代码可以获得这些自定义的属性。

```html
	var post = document.getElementsByTagName('div')[0];
	post.dataset; // DOMStringMap
	post.dataset.commentNum; // 10
```	


* 如果把 HTML5 看作做一个开放平台，那它的构建模块有哪些？
	*　\<nav>, \<header>, \<section>, \<footer>
	* 必须知道的html相关特性：http://www.camnpr.com/archives/must-know-the-seven-html5-features.html

* 请描述一下 cookies，sessionStorage 和 localStorage 的区别？ 
	* 概念：
		* sessionStorage 和 localStorage 是HTML5 Web Storage API 提供的，可以方便的在web请求之间保存数据。有了本地数据，就可以避免数据在浏览器和服务器间不必要地来回传递。
		* sessionStorage、localStorage、cookie都是在浏览器端存储的数据，其中sessionStorage的概念很特别，引入了一个“浏览器窗口”的概念。sessionStorage是在同源的同窗口（或tab）中，始终存在的数据。也就是说只要这个浏览器窗口没有关闭，即使刷新页面或进入同源另一页面，数据仍然存在。关闭窗口后，sessionStorage即被销毁。同时“独立”打开的不同窗口，即使是同一页面，sessionStorage对象也是不同的。
	* 共同点：都是保存在浏览器端，且同源的。
	* 区别：
		* 1. cookie数据始终在同源的http请求中携带（即使不需要），即cookie在浏览器和服务器间来回传递。而sessionStorage和localStorage不会自动把数据发给服务器，仅在本地保存。cookie数据还有路径（path）的概念，可以限制cookie只属于某个路径下。
		* 2. 存储大小限制也不同，cookie数据不能超过4k，同时因为每次http请求都会携带cookie，所以cookie只适合保存很小的数据，如会话标识。sessionStorage和localStorage 虽然也有存储大小的限制，但比cookie大得多，可以达到5M或更大。
		* 3. 数据有效期不同，sessionStorage：仅在当前浏览器窗口关闭前有效，自然也就不可能持久保持；localStorage：始终有效，窗口或浏览器关闭也一直保存，因此用作持久数据；cookie只在设置的cookie过期时间之前一直有效，即使窗口或浏览器关闭。
		* 4. 作用域不同，sessionStorage不在不同的浏览器窗口中共享，即使是同一个页面；localStorage 在所有同源窗口中都是共享的；cookie也是在所有同源窗口中都是共享的。
		* 5. Web Storage 支持事件通知机制，可以将数据更新的通知发送给监听者。
		* 6. Web Storage 的 api 接口使用更方便。

* sessionStorage与页面 js 数据对象的区别
	* 页面中一般的 js 对象或数据的生存期是仅在当前页面有效，因此刷新页面或转到另一页面这样的重新加载页面的情况，数据就不存在了。
	* 而sessionStorage 只要同源的同窗口（或tab）中，刷新页面或进入同源的不同页面，数据始终存在。也就是说只要这个浏览器窗口没有关闭，加载新页面或重新加载，数据仍然存在

* Web Storage带来的好处：
	* 减少网络流量：一旦数据保存在本地后，就可以避免再向服务器请求数据，因此减少不必要的数据请求，减少数据在浏览器和服务器间不必要地来回传递。
	* 快速显示数据：性能好，从本地读数据比通过网络从服务器获得数据快得多，本地数据可以即时获得。再加上网页本身也可以有缓存，因此整个页面和数据都在本地的话，可以立即显示。
	* 临时存储：很多时候数据只需要在用户浏览一组页面期间使用，关闭窗口后数据就可以丢弃了，这种情况使用sessionStorage非常方便。

* 浏览器本地存储与服务器端存储之间的区别
	* 其实数据既可以在浏览器本地存储，也可以在服务器端存储。
	* 浏览器端可以保存一些数据，需要的时候直接从本地获取，sessionStorage、localStorage和cookie都由浏览器存储在本地的数据。
	* 服务器端也可以保存所有用户的所有数据，但需要的时候浏览器要向服务器请求数据。
		* 1.服务器端可以保存用户的持久数据，如数据库和云存储将用户的大量数据保存在服务器端。
		* 2.服务器端也可以保存用户的临时会话数据。服务器端的session机制，如jsp的 session 对象，数据保存在服务器上。实现上，服务器和浏览器之间仅需传递session id即可，服务器根据session id找到对应用户的session对象。会话数据仅在一段时间内有效，这个时间就是server端设置的session有效期。
	* 服务器端保存所有的用户的数据，所以服务器端的开销较大，而浏览器端保存则把不同用户需要的数据分布保存在用户各自的浏览器中。
	* 浏览器端一般只用来存储小数据，而服务器可以存储大数据或小数据。
	* 服务器存储数据安全一些，浏览器只适合存储一般数据。

* 请描述一下 `GET` 和 `POST` 的区别?	 
	* 1、 get是从服务器获取数据 -----"取"; post是向服务器提交数据 -----“发” 
	* 2、 form表单默认的method为"GET" 
	* 3、 get将数据按照variable = value 的形式，加上URL的后面，中间用"?"连接，各个变量之间用"&"连接; post将数据不像get方式那样 
  	* 4、 参数上面3的数据传输方式，可以得出：post安全性比get方式要高   
	* 5、 
		* URL不存在参数上限的问题，HTTP协议没有对URL长度进行限制，限制的是部分浏览器和服务器的限制。
     	* IE对URL长度的限制为2083KB
     	* get方式是通过URL传输的数据的，数据量一般在2KB左右，但是执行效率比post高
     	* 理论上post方式没有大小限制，HTTP协议规范也没进行大小限制。post数据没有限制，限制的是服务器处理程序的能力

* js如何判断浏览器正在以何种方式解析？
	* 使用 document.compatMode来判断浏览器的解析方式。
		* 例如：
```javascript
	function getMode{
	    var _cm = docoment.compatMode;
	    if(_cm == 'CSS1Compat'){
	         return "strict"
	    } 
	    if(_cm == 'BackCompat' ){
	         return  'quirks'
	    } 
	}
```


- Doctype作用? 严格模式与混杂模式如何区分？它们有何意义? 

		（1）、<!DOCTYPE> 声明位于文档中的最前面，处于 <html> 标签之前。告知浏览器的解析器，
              用什么文档类型 规范来解析这个文档。 
		
		（2）、严格模式的排版和 JS 运作模式是  以该浏览器支持的最高标准运行。
		
		（3）、在混杂模式中，页面以宽松的向后兼容的方式显示。模拟老式浏览器的行为以防止站点无法工作。
		
		（4）、DOCTYPE不存在或格式不正确会导致文档以混杂模式呈现。

- 行内元素有哪些？块级元素有哪些？ 空(void)元素有那些？

		（1）CSS规范规定，每个元素都有display属性，确定该元素的类型，每个元素都有默认的display值，
		  比如div默认display属性值为“block”，成为“块级”元素；
		  span默认display属性值为“inline”，是“行内”元素。  

		（2）行内元素有：a b span img input select strong（强调的语气） 
		 块级元素有：div ul ol li dl dt dd h1 h2 h3 h4…p  
	
		（3）知名的空元素： 
		<br> <hr> <img> <input> <link> <meta> 
		鲜为人知的是： 
		<area> <base> <col> <command> <embed> <keygen> <param> <source> <track> <wbr>


- link 和@import 的区别是？

	
		（1）link属于XHTML标签，而@import是CSS提供的;

		（2）页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载;

		（3）import只在IE5以上才能识别，而link是XHTML标签，无兼容问题;

		（4）link方式的样式的权重 高于@import的权重.	

- 浏览器的内核分别是什么?
	
	     * IE浏览器的内核Trident、Mozilla的Gecko、Chrome的Blink（WebKit的分支）、Opera内核原为Presto，现为Blink；


- 常见兼容性问题？

	    * png24位的图片在iE6浏览器上出现背景，解决方案是做成PNG8.
	
		* 浏览器默认的margin和padding不同。解决方案是加一个全局的*{margin:0;padding:0;}来统一。
		 
		* IE6双边距bug:块属性标签float后，又有横行的margin情况下，在ie6显示margin比设置的大。 
	       
		  浮动ie产生的双倍距离 #box{ float:left; width:10px; margin:0 0 0 100px;} 
	    
	     这种情况之下IE会产生20px的距离，解决方案是在float的标签样式控制中加入 ——_display:inline;将其转化为行内属性。(_这个符号只有ie6会识别)
	
		  渐进识别的方式，从总体中逐渐排除局部。 
	  
		  首先，巧妙的使用“\9”这一标记，将IE游览器从所有情况中分离出来。 
		  接着，再次使用“+”将IE8和IE7、IE6分离开来，这样IE8已经独立识别。
         
          css
	          .bb{
	           background-color:#f1ee18;/*所有识别*/
	          .background-color:#00deff\9; /*IE6、7、8识别*/
	          +background-color:#a200ff;/*IE6、7识别*/
	          _background-color:#1e0bd1;/*IE6识别*/ 
	          } 
  
		*  IE下,可以使用获取常规属性的方法来获取自定义属性,
		   也可以使用getAttribute()获取自定义属性;
           Firefox下,只能使用getAttribute()获取自定义属性. 
           解决方法:统一通过getAttribute()获取自定义属性.
          
		* IE下,even对象有x,y属性,但是没有pageX,pageY属性; 
          Firefox下,event对象有pageX,pageY属性,但是没有x,y属性.
		  
		* 解决方法：（条件注释）缺点是在IE浏览器下可能会增加额外的HTTP请求数。
		
		* Chrome 中文界面下默认会将小于 12px 的文本强制按照 12px 显示, 
		  可通过加入 CSS 属性 -webkit-text-size-adjust: none; 解决.

		超链接访问过后hover样式就不出现了 被点击访问过的超链接样式不在具有hover和active了解决方法是改变CSS属性的排列顺序:
	    L-V-H-A :  a:link {} a:visited {} a:hover {} a:active {}



- html5有哪些新特性、移除了那些元素？如何处理HTML5新标签的浏览器兼容问题？如何区分 HTML 和 
HTML5？
	
	
		* HTML5 现在已经不是 SGML 的子集，主要是关于图像，位置，存储，多任务等功能的增加。

		* 绘画 canvas  
		  用于媒介回放的 video 和 audio 元素 
		  本地离线存储 localStorage 长期存储数据，浏览器关闭后数据不丢失；
          sessionStorage 的数据在浏览器关闭后自动删除
		  
		  语意化更好的内容元素，比如 article、footer、header、nav、section 
		  表单控件，calendar、date、time、email、url、search  
		  新的技术webworker, websockt, Geolocation

		* 移除的元素
		
		纯表现的元素：basefont，big，center，font, s，strike，tt，u；
		
		对可用性产生负面影响的元素：frame，frameset，noframes；

	    支持HTML5新标签：
		
		* IE8/IE7/IE6支持通过document.createElement方法产生的标签，
		  可以利用这一特性让这些浏览器支持HTML5新标签，
  
          浏览器支持新标签后，还需要添加标签默认的样式：
	   
		* 当然最好的方式是直接使用成熟的框架、使用最多的是html5shim框架
		   <!--[if lt IE 9]> 
		   <script> src="http://html5shim.googlecode.com/svn/trunk/html5.js"</script> 
		   <![endif]--> 
		如何区分： DOCTYPE声明\新增的结构元素\功能元素
	

- 语义化的理解？ 
	
		用正确的标签做正确的事情！
	    html语义化就是让页面的内容结构化，便于对浏览器、搜索引擎解析；
	    在没有样式CCS情况下也以一种文档格式显示，并且是容易阅读的。
	    搜索引擎的爬虫依赖于标记来确定上下文和各个关键字的权重，利于 SEO。
	    使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。

- HTML5的离线储存？

	    localStorage    长期存储数据，浏览器关闭后数据不丢失；
        sessionStorage  数据在浏览器关闭后自动删除。

- (写)描述一段语义的html代码吧。

	    （HTML5中新增加的很多标签（如：<article>、<nav>、<header>和<footer>等）
         就是基于语义化设计原则）  
			< div id="header"> 
			< h1>标题< /h1> 
			< h2>专注Web前端技术< /h2> 
			< /div>


- iframe有那些缺点？ 

		*iframe会阻塞主页面的Onload事件；

		*iframe和主页面共享连接池，而浏览器对相同域的连接有限制，所以会影响页面的并行加载。
        使用iframe之前需要考虑这两个缺点。如果需要使用iframe，最好是通过javascript
        动态给iframe添加src属性值，这样可以可以绕开以上两个问题。

- 请描述一下 cookies，sessionStorage 和 localStorage 的区别？ 

 		cookie在浏览器和服务器间来回传递。 sessionStorage和localStorage不会
		sessionStorage和localStorage的存储空间更大；
		sessionStorage和localStorage有更多丰富易用的接口；
		sessionStorage和localStorage各自独立的存储空间；
		
- 如何实现浏览器内多个标签页之间的通信? (阿里)
		
		调用localstorge、cookies等本地存储方式

- webSocket如何兼容低浏览器？(阿里)
		
		Adobe Flash Socket 、 ActiveX HTMLFile (IE) 、 基于 multipart 编码发送 XHR 、 基于长轮询的 XHR

####[[⬆]](#toc) <a name='css'>CSS 相关问题：</a>

* 描述下 “reset” CSS 文件的作用和使用它的好处。
- 为什么要初始化CSS样式。

		- 因为浏览器的兼容问题，不同浏览器对有些标签的默认值是不同的，如果没对CSS初始化往往会出现浏览器之间的页面显示差异。
	
		- 当然，初始化样式会对SEO有一定的影响，但鱼和熊掌不可兼得，但力求影响最小的情况下初始化。

		*最简单的初始化方法就是： * {padding: 0; margin: 0;} （不建议）
	
		淘宝的样式初始化： 
		body, h1, h2, h3, h4, h5, h6, hr, p, blockquote, dl, dt, dd, ul, ol, li, pre, form, fieldset, legend, button, input, textarea, th, td { margin:0; padding:0; }
		body, button, input, select, textarea { font:12px/1.5tahoma, arial, \5b8b\4f53; }
		h1, h2, h3, h4, h5, h6{ font-size:100%; }
		address, cite, dfn, em, var { font-style:normal; }
		code, kbd, pre, samp { font-family:couriernew, courier, monospace; }
		small{ font-size:12px; }
		ul, ol { list-style:none; }
		a { text-decoration:none; }
		a:hover { text-decoration:underline; }
		sup { vertical-align:text-top; }
		sub{ vertical-align:text-bottom; }
		legend { color:#000; }
		fieldset, img { border:0; }
		button, input, select, textarea { font-size:100%; }
		table { border-collapse:collapse; border-spacing:0; } 

* 解释下浮动和它的工作原理。
	* 浮动元素脱离文档流，不占据空间。浮动元素碰到包含它的边框或者浮动元素的边框停留。[link](http://blog.sina.com.cn/s/blog_5809ec9801009dku.html)

* 列举不同的清除浮动的技巧，并指出它们各自适用的使用场景。
	* 1.使用空标签清除浮动。
	   * 这种方法是在所有浮动标签后面添加一个空标签 定义css clear:both. 弊端就是增加了无意义标签。
	* 2.使用overflow。
	  *  给包含浮动元素的父标签添加css属性 overflow:auto; zoom:1; zoom:1用于兼容IE6。
	* 3.使用after伪对象清除浮动。
	   * 该方法只适用于非IE浏览器。具体写法可参照以下示例。使用中需注意以下几点。一、该方法中必须为需要清除浮动元素的伪对象中设置 height:0，否则该元素会比实际高出若干像素；二、content属性是必须的，但其值可以为空，蓝色理想讨论该方法的时候content属性的值 设为”.”，但我发现为空亦是可以的。
```html	  
	<style type=”text/css”>
	<!–
	    *{margin:0;padding:0;}
	    body{font:36px bold; color:#F00; text-align:center;}
	    #layout{background:#FF9;}
	    #layout:after{display:block;clear:both;content:”";visibility:hidden;height:0;}
	    #left{float:left;width:20%;height:200px;background:#DDD;line-height:200px;}
	    #right{float:right;width:30%;height:80px;background:#DDD;line-height:80px;}
	–>
	</style>
	<div id=”layout”>
	    <div id=”left”>Left</div>
	    <div id=”right”>Right</div>
	</div>
```

	* 此三种方法各有利弊，使用时应择优选择，比较之下第二种方法更为可取

* 解释下 CSS sprites，以及你要如何在页面或网站中使用它。
	* CSS Sprites其实就是把网页中一些背景图片整合到一张图片文件中，再利用CSS的“background-image”，“background- repeat”，“background-position”的组合进行背景定位，background-position可以用数字能精确的定位出背景图片的位置。

* 你最喜欢的图片替换方法是什么，你如何选择使用。
```html
	<h2> <span 图片丢这里></span>Hello World </h2> 
```
	* 把span背景设成文字内容，这样又可以保证seo，也有图片的效果在上面。
	*  一般都是：alt，title，onerror

* 讨论CSS hacks，条件引用或者其他。
	* 在这个浏览器百花争鸣的时代，作为前端开发的我们为了我们漂亮的设计能适应各个浏览器可为煞费苦心，主要体现在javascript和css上面。javascript我这次就不谈了，先说说css。
    * 为了适应不同浏览器不同的版本（版本主要就ie来说），ie这朵奇葩现在我们要兼容6-9，它的10也快出来了。。。在ie下我们可以写条件注释来区分ie和其他浏览器，以及ie的版本，这些请大家自行google。这篇文章主要讨论的是css hack。下面废话补多说了，直接上代码
```html
<!DOCTYPE html>  
<html>  
<head>  
    <title>Css Hack</title>  
    <style>  
    #test   
    {   
        width:300px;   
        height:300px;   
          
        background-color:blue;      /*firefox*/
        background-color:red\9;      /*all ie*/
        background-color:yellow\0;    /*ie8*/
        +background-color:pink;        /*ie7*/
        _background-color:orange;       /*ie6*/
    }  
    :root #test { background-color:purple\9; }  /*ie9*/
    @media all and (min-width:0px){ #test {background-color:black\0;} }  /*opera*/
    @media screen and (-webkit-min-device-pixel-ratio:0){ #test {background-color:gray;} }  /*chrome and safari*/
    </style>  
</head>  
<body>  
    <div id="test">test</div>  
</body>  
</html> 
```

* 如何为有功能限制的浏览器提供网页？
  * 你会使用哪些技术和处理方法？
  
* 有哪些的隐藏内容的方法（如果同时还要保证屏幕阅读器可用呢？）
	* 1. display:none; 有缺陷
		* 搜索引擎可能认为被隐藏的文字属于垃圾信息而忽略
	* 2. visibility:　hidden; 有缺陷
		* 隐藏的内容会占据他所应占据的物理空间
```css
.textHidden {
	display: block; /*统一转化为块级元素*/
	overflow: hidden;
	width: 0;
	height: 0;
}
```
* 你用过栅格系统吗？如果使用过，你最喜欢哪种？
	* 比如：Bootstrap，流式栅格系统，http://960.gs/ ，[栅格系统延续美学](http://mux.baidu.com/?p=1550)

* 你用过媒体查询，或针对移动端的布局/CSS 吗？
	* @media screen and (min-width: 400px) and (max-width: 700px) { … }
 	* @media handheld and (min-width: 20em), screen and (min-width: 20em) { … }

* 你熟悉 SVG 样式的书写吗？
```SVG
<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"> 
 <circle cx="40" cy="40" r="24" style="stroke:#006600; fill:#00cc00"/>
 <text x="250" y="150" font-family="Verdana" font-size="10px" fill="blue">Hello, out there</text>
 <defs><style type="text/css"> <![CDATA[.sample{stroke:blue;fill:#0080FF;opacity:1;}]]></style></defs>
 <use xlink:href="#sample1" class="sample"/>
 </svg>
```

* 如何优化网页的打印样式？
```html
	 <link rel="stylesheet" type="text/css" media="screen" href="xxx.css" />
```	
	 * 其中media指定的属性就是设备，显示器上就是screen，打印机则是print，电视是tv，投影仪是projection。
```html	 
	 <link rel="stylesheet" type="text/css" media="print" href="yyy.css" />
```
	 * 但打印样式表也应有些注意事项：
		 1、打印样式表中最好不要用背景图片，因为打印机不能打印CSS中的背景。如要显示图片，请使用html插入到页面中。
		 2、最好不要使用像素作为单位，因为打印样式表要打印出来的会是实物，所以建议使用pt和cm。
		 3、隐藏掉不必要的内容。（@print div{display:none;}）
		 4、打印样式表中最好少用浮动属性，因为它们会消失。
		 如果想要知道打印样式表的效果如何，直接在浏览器上选择打印预览就可以了。
	* CSS控制网页打印样式： 
		* media 定义和用法： 
		* media 属性规定被链接文档将显示在什么设备上。 
		* media 属性用于为不同的媒介类型规定不同的样式。 
		* 用到media来指定css的媒体类型，它的语法格式有这样几种： 
		* @media screen | print | projection | braille | aural | tv | handheld | all 
	* 参数说明： 
		* screen：指计算机屏幕。 
		* print：指用于打印机的不透明介质。 
		* projection：指用于显示的项目。 
		* braille：盲文系统，指有触觉效果的印刷品。 
		* aural：指语音电子合成器。 
		* tv：电视类型的媒体。 
		* handheld：指手持式显示设备。 
		*all：用于所有媒体。 
	* 只要导入将不想打印的东西加入下面这CSS样式声明中，将在打印的页面不会出现： 
	* 代码如下:
```html
　 <link rel="stylesheet" media="print" type="text/css" /> 
```
	* 例如：
	
```html
	<style media="print"> <!-- media必须声明，不然无效了 -->
		#my_hidden{display:none;} 	
	</style>
```

* 在书写高效 CSS 时会有哪些问题需要考虑？
	* 1. 样式是：从右向左的解析一个选择器
	* 2. ID最快，Universal最慢 有四种类型的key selector，解析速度由快到慢依次是：ID、class、tag和universal
	* 3. 不要tag-qualify （永远不要这样做 ul#main-navigation { } ID已经是唯一的，不需要Tag来标识，这样做会让选择器变慢。）
	* 4. 后代选择器最糟糕（换句话说，下面这个选择器是很低效的： html body ul li a { }）
	* 5. 想清楚你为什么这样写
	* 6. CSS3的效率问题（CSS3选择器（比如 :nth-child）能够漂亮的定位我们想要的元素，又能保证我们的CSS整洁易读。但是这些神奇的选择器会浪费很多的浏览器资源。）
	* 7. 我们知道#ID速度是最快的，那么我们都用ID，是不是很快。但是我们不应该为了效率而牺牲可读性和可维护性

* 使用 CSS 预处理器的优缺点有哪些？(SASS，Compass，Stylus，LESS)
  * 描述下你曾经使用过的 CSS 预处理的优缺点。
  
* 如果设计中使用了非标准的字体，你该如何去实现？
  * Webfonts (字体服务例如：Google Webfonts，Typekit 等等。)
  
* 解释下浏览器是如何判断元素是否匹配某个 CSS 选择器？

* 怎么样实现垂直居中？

* 请解释一下 ```* { box-sizing: border-box; }``` 的作用, 并且说明使用它有什么好处？

* 请罗列出你所知道的 display 属性的全部值
  * block 像块类型元素一样显示。
  * none 缺省值。向行内元素类型一样显示。
  * inline-block 像行内元素一样显示，但其内容象块类型元素一样显示。
  * list-item 象块类型元素一样显示，并添加样式列表标记。

* 请解释一下 inline 和 inline-block 的区别？
	* inline-block可以设置行高

* 请解释一下 relative、fixed、absolute 和 static 元素的区别
	* inherit 规定从父元素继承 position 属性的值。
	* 1）static：默认值。没有定位，元素出现在正常的流中（忽略 top, bottom, left, right 或者 z-index 声明）。
	* 2）relative：生成相对定位的元素，通过top,bottom,left,right的设置相对于其正常位置进行定位。可通过z-index进行层次分级。relative的元素脱离正常的文本流中，但其在文本流中的位置依然存在。
	* 3）absolute：生成绝对定位的元素，相对于 static 定位以外的第一个父元素进行定位。元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。可通过z-index进行层次分级。与relative的区别是其在正常流中的位置不在存在。
	*　4）fixed：生成绝对定位的元素，相对于浏览器窗口进行定位。元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。可通过z-index进行层次分级。

* 你目前在使用哪一套CSS框架，或者在产品线上使用过哪一套？(Bootstrap, PureCSS, Foundation 等等)
  * 如果有，请问是哪一套？如果可以，你如何改善CSS框架？

* 请问你有使用过 CSS Flexbox 或者 Grid specs 吗？
  * 如果有，请问在性能和效率的方面你是怎么看的？
  * [深入了解 Flexbox 伸缩盒模型](http://www.w3cplus.com/blog/666.html)

- 介绍一下CSS的盒子模型？

		（1）有两种， IE 盒子模型、标准 W3C 盒子模型；IE的content部分包含了 border 和 pading;

		（2）盒模型： 内容(content)、填充(padding)、边界(margin)、 边框(border).



- CSS 选择符有哪些？哪些属性可以继承？优先级算法如何计算？ CSS3新增伪类有那些？

		*   1.id选择器（ # myid）
			2.类选择器（.myclassname）
			3.标签选择器（div, h1, p）
			4.相邻选择器（h1 + p）
			5.子选择器（ul < li）
			6.后代选择器（li a）
			7.通配符选择器（ * ）
			8.属性选择器（a[rel = "external"]）
			9.伪类选择器（a: hover, li: nth - child）
		  
		*   可继承的样式： font-size font-family color, UL LI DL DD DT;

		*   不可继承的样式：border padding margin width height ;
		  
		*   优先级就近原则，同权重情况下样式定义最近者为准;

		*   载入样式以最后载入的定位为准;

	优先级为:
		  
		   !important >  id > class > tag  
		  
		   important 比 内联优先级高

	CSS3新增伪类举例：

		p:first-of-type	选择属于其父元素的首个 <p> 元素的每个 <p> 元素。
		p:last-of-type	选择属于其父元素的最后 <p> 元素的每个 <p> 元素。
        p:only-of-type	选择属于其父元素唯一的 <p> 元素的每个 <p> 元素。
		p:only-child	选择属于其父元素的唯一子元素的每个 <p> 元素。
		p:nth-child(2)	选择属于其父元素的第二个子元素的每个 <p> 元素。
 	    :enabled  :disabled 控制表单控件的禁用状态。
		:checked        单选框或复选框被选中。


- 如何居中div？如何居中一个浮动元素？


	*  给div设置一个宽度，然后添加margin:0 auto属性
		 
			div{
				width:200px;
				margin:0 auto;
			 }  

			 
	*  居中一个浮动元素
  
			  确定容器的宽高 宽500 高 300 的层
			  设置层的外边距
			 
		     .div { 
			  Width:500px ; height:300px;//高度可以不设
			  Margin: -150px 0 0 -250px;
			  position:relative;相对定位
              background-color:pink;//方便看效果
			  left:50%;
			  top:50%;
			} 


- 列出display的值，说明他们的作用。position的值， relative和absolute定位原点是？
 
	
	      1.   
	      block 象块类型元素一样显示。
		  none 缺省值。象行内元素类型一样显示。
		  inline-block 象行内元素一样显示，但其内容象块类型元素一样显示。
		  list-item 象块类型元素一样显示，并添加样式列表标记。
	  
	      2. 
		  *absolute	
				生成绝对定位的元素，相对于 static 定位以外的第一个父元素进行定位。 
	
		  *fixed （老IE不支持）
				生成绝对定位的元素，相对于浏览器窗口进行定位。 
	
		  *relative	
				生成相对定位的元素，相对于其正常位置进行定位。 
	
		  * static	默认值。没有定位，元素出现在正常的流中
		  *（忽略 top, bottom, left, right z-index 声明）。
	
		  * inherit	规定从父元素继承 position 属性的值。
	  
- CSS3有哪些新特性？

  		  CSS3实现圆角（border-radius:8px），阴影（box-shadow:10px），
		  对文字加特效（text-shadow、），线性渐变（gradient），旋转（transform）
          transform:rotate(9deg) scale(0.85,0.90) translate(0px,-30px) skew(-9deg,0deg);//旋转,缩放,定位,倾斜
          增加了更多的CSS选择器  多背景 rgba 

- 一个满屏 品 字布局 如何设计?
	* 首先划分成头部、body、脚部

- 经常遇到的CSS的兼容性有哪些？原因，解决方法是什么？
	* [CSS兼容性常见问题总结](http://www.zhufengpeixun.cn/CSS/2011-08-25/142.html)

- absolute的containing block计算方式跟正常流有什么不同？
	* [视觉格式化模型](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Visual_formatting_model)

- position跟display、margin collapse、overflow、float这些特性相互叠加后会怎么样？
	* [http://www.th7.cn/web/html-css/201405/37444.shtml](http://www.th7.cn/web/html-css/201405/37444.shtml)

- 对BFC规范的理解？

		* （W3C CSS 2.1 规范中的一个概念,它决定了元素如何对其内容进行定位,以及与其他元素的关 系和相互作用。）

- css定义的权重

		以下是权重的规则：标签的权重为1，class的权重为10，id的权重为100，以下例子是演示各种定义的权重值：
	 
		/*权重为1*/
		div{
		}
		/*权重为10*/
		.class1{
		}
		/*权重为100*/
		#id1{
		}
		/*权重为100+1=101*/
		#id1 div{
		}
		/*权重为10+1=11*/
		.class1 div{
		}
		/*权重为10+10+1=21*/
		.class1 .class2 div{
		} 
		
		如果权重相同，则最后定义的样式会起作用，但是应该避免这种情况出现

- 如果需要手动写动画，你认为最小时间间隔是多久，为什么？（阿里）

		多数显示器默认频率是60Hz，即1秒刷新60次，所以理论上最小间隔为1/60＊1000ms ＝ 16.7ms


- display:inline-block 什么时候会显示间隙？(携程)

		移除空格、使用margin负值、使用font-size:0、letter-spacing、word-spacing

* css规范
	[css规范](http://willhamlam.gitbooks.io/a_better_front-end_guideline/index.html)
 
####[[⬆]](#toc) <a name='js'>JS相关问题：</a>

* use strict
```
	[javascript] 
	"use strict"; 

	这样很巧妙地兼容了那些不支持strict mode老的浏览器，不会报错。
	使用 strict mode 有以下几个好处：

	防止意外定义的全局变量
	[javascript]
	"use strict"; 
	x = 5; // 没有事先声明，会报错 

	取消this值的自动转换
	[javascript] view plaincopy
	window.hi= "Hi"; 
	 
	function sayHi() { 
	    alert(this.hi); // 报错 
	} 

	防止重复定义
	[javascript] 
	var someObject = { 
	    prop: "test", 
	    prop: "test2"  //报错 
	}; 

	此外，strict mode 还去掉了对with 语句的支持； eval 中声明的变量也不会在包含域中创建。
	最后，建议大家开始在JS代码中使用strict mode，更早发现隐藏的错误。
```
```
	(function() {
		"use strict";
		function doSomething() {
			// 运行于严格模式
		}
		function doSomethindElse() {
			// 同样运行于严格模式
		}
	}());
```
	* 强烈建议你从现在开始就启用JavaScript严格模式,它能帮你发现代码中未曾注意到的错误。
	* 不要在全局环境中启用,但你能尽量多的使用IIFE(立即执行函数表达式)来把严格模式作用到多个函数范围内。
	* 一开始,你会遇到之前未曾碰到过的错误提示,这是正常的。当启用严格模式后,请确保在支持的浏览器中做了测试,以发现新的潜在问题。
	* 一定不要仅仅在代码中添加一行”use strict”就假定余下的代码能正常工作。最后,请在严格模式下开始编写更好的代码。

 [JavaScript严谨模式(Strict Mode)提升开发效率和质量](http://flandycheng.blog.51cto.com/855176/982719)

* javascript的__proto__（注意前后都是两条下划线）和prototype都可以访问对象的原型对象，那么他们之间有什么不同吗？

* __proto__是只能用 对象. 来访问，而prototype则只能是 类. 来访问

```
/**
    * 利用原型模式实现简单继承
    */
   function per(){
       this.getName = function(str){
           alert(str);
       }
   }
   per.prototype.getAge = function(age){
       alert(age);
   }
   var a = {};
   a.__proto__ = per.prototype;
   //a.getAge(2);
  // a.getName("a");
   /**
    * 简单方式实现继承
    */
   var b = {};
   b.__proto__ = new per();
   b.__proto__.constructor = b;
   b.getAge("1");
   b.getName("a");
 
   /**
    * 串联继承
    */
   function A(){
       this.getA = "a";
   }
   function B(){
       this.getB = "b";
   }
   function K(){}
   B.prototype = new A();
   B.prototype.constructor = B;
 
   K.prototype = new B();
   K.prototype.constructor = K;
 
   var test = new K();
   alert(test.getA);
   alert(test.getB);
```


* 解释下事件代理。
	* JavaScript事件代理则是一种简单的技巧，通过它你可以把事件处理器添加到一个父级元素上，这样就避免了把事件处理器添加到多个子级元素上。
	* 当我们需要对很多元素添加事件的时候，可以通过将事件添加到它们的父节点而将事件委托给父节点来触发处理函数。这主要得益于浏览器的事件冒泡机制。
 	* 事件代理用到了两个在JavaSciprt事件中常被忽略的特性：事件冒泡以及目标元素。
```javascript 	
 function getEventTarget(e) {
 e = e || window.event;
 return e.target || e.srcElement;
 }
 ```
 	* 事件代理，比如，我要点一个table中的td时编辑，那么我们会在td上绑定事件呢还是table上，如果在td上绑定，会产生非常多的事件，对内存来说是个不小的考验，所以我们选择在table中绑定。因为js中有些事件是冒泡的，比如onclick。


* 解释下 JavaScript 中 `this` 是如何工作的。
	* this永远指向函数运行时所在的对象，
	* 而不是函数被创建时所在的对象。匿名函数和不处于任何对象中的函数指向window。
	* call,apply,with指的this是谁就是谁。
	* 普通的函数调用，函数调用被谁调用，this指的就是谁。

* 解释下原型继承的原理。
	* [JavaScript原型继承工作原理](http://developer.51cto.com/art/201309/410991.htm)
	* [理解Javascript_05_原型继承原理](http://www.cnblogs.com/fool/archive/2010/10/13/1849734.html)
	* 当查找一个对象的属性时，JavaScript 会向上遍历原型链，直到找到给定名称的属性为止。(大多数JavaScript的实现用 __proto__ 属性来表示一个对象的原型链。)

	* 以下代码展示了JS引擎如何查找属性：

```javascript
function getProperty(obj, prop) {

    if (obj.hasOwnProperty(prop))

        return obj[prop]

    else if (obj.__proto__ !== null)

        return getProperty(obj.__proto__, prop)

    else

        return undefined

}
```
	* 注：__proto__ 是一个不应在你代码中出现的非正规的用法，这里仅仅用它来解释JavaScript原型继承的工作原理。

* 你是如何测试JavaScript代码的？
	* [如何用Qunit测试你的JavaScript代码](http://www.woiweb.net/how-to-test-your-javascript-code-with-qunit.html)

* AMD vs. CommonJS？
	* AMD是依赖提前加载,CMD是依赖延时加载
	* [JavaScript模块化编程 - CommonJS, AMD 和 RequireJS之间的关系](http://www.2cto.com/kf/201401/270303.html)

* 什么是哈希表？
	* 哈希表（Hash table，也叫散列表），是根据关键码值(Key value)而直接进行访问的数据结构。也就是说，它通过把关键码值映射到表中一个位置来访问记录，以加快查找的速度。这个映射函数叫做散列函数，存放记录的数组叫做散列表。说白了哈希表的原理其实就是通过空间换取时间的做法。。
    * 哈希表的做法其实很简单，就是把Key通过一个固定的算法函数既所谓的哈希函数转换成一个整型数字，然后就将该数字对数组长度进行取余，取余结果就当作数组的下标，将value存储在以该数字为下标的数组空间里。
    *  而当使用哈希表进行查询的时候，就是再次使用哈希函数将key转换为对应的数组下标，并定位到该空间获取value，如此一来，就可以充分利用到数组的定位性能进行数据定位。。

* 解释下为什么接下来这段代码不是 IIFE(立即调用的函数表达式)：`function foo(){ }();`. 
  * 要做哪些改动使它变成 IIFE?
  	* function foo(){ }()解析器会把function foo(){ }当作一个函数声明，（）没有实际意义的函数表达式。分组操作需要包含表达式。给加上括号就行
  
* 描述以下变量的区别：`null`，`undefined` 或 `undeclared`？
  * 该如何检测它们？
  	* undefined :js语言类型，有申明，没有初始化。
  	* undeclared：js语法错误，没有申明直接使用，js无法找到对应的上下文。
  	* null：是空值。
  	* 用typeof判断undefined，==，！=null判断Null..

* 什么是闭包，如何使用它，为什么要使用它？
	* [JS 闭包是什么，如何使用它，为什么要使用它？ 你喜欢的使用闭包的模式是什么？](http://bbs.blueidea.com/home.php?mod=space&uid=351999&do=blog&id=29210)
	* [学习Javascript闭包（Closure） 阮一峰](http://www.ruanyifeng.com/blog/2009/08/learning_javascript_closures.html)
	* 闭包就是能够读取其他函数内部变量的函数。
	* 闭包可以用在许多地方。它的最大用处有两个，一个是前面提到的可以读取函数内部的变量，另一个就是让这些变量的值始终保持在内存中。

	* 函数数再定义一个函数，用于返回里面的值，

	* 你喜欢的使用闭包的模式是什么？
		* 两种模式用在不同场合。参见jQuery源码，立即调用模式，把$的jQuery源码放在了全局作用域下。返回函数类型的，制作一个随时可以使用的函数。
	　　* 闭包与设计模式
		* 单例模式，例如要做一个荫罩层，这个时候我们需要一个全局变量来判断页面是否已经存在这样一个东西，如果就用一个var a 定义，那么就会污染全局命名空间。最好的作法，就是把这样一个变旦放在一个函数里面，然后通过函数内的函数去判断调用写它的逻辑。

* 闭包会带来什么问题？怎么避免？
	* 使用闭包的注意点
		1）由于闭包会使得函数中的变量都被保存在内存中，内存消耗很大，所以不能滥用闭包，否则会造成网页的性能问题，在IE中可能导致内存泄露。解决方法是，在退出函数之前，将不使用的局部变量全部删除。
		2）闭包会在父函数外部，改变父函数内部变量的值。所以，如果你把父函数当作对象（object）使用，把闭包当作它的公用方法（Public Method），把内部变量当作它的私有属性（private value），这时一定要小心，不要随便改变父函数内部变量的值。

* 请举出一个匿名函数的典型用例？
```javascript
$.("input").each(function(e){this.val('OK')});
```

* 解释 “JavaScript 模块模式” 以及你在何时使用它。
	* 我们在做radf库的时候，把所有的函数写在var function =  radf(){}里，为的是在全局作用域下，只有一个radf对象，所有的属性和方法全在radf命名空间下面。这样就是一个无污染的环境。
  * 如果有提到无污染的命名空间，可以考虑加分。
  * 如果你的模块没有自己的命名空间会怎么样？
  
* 你是如何组织自己的代码？是使用模块模式，还是使用经典继承的方法？
	* 在模块模式中使用继承。例如我们的库中有pannel布局型组件和data型组件，其余都依照这两个基本组件继承而来。

* 请指出 JavaScript 宿主对象和原生对象的区别？
	* 浏览器环境就是一个宿主，例如ie和ff就是两个不同的宿主环境，里面有一些方法和解释编译的差异性。document、body就是这样的对象。
	* 内置对象就是w3c那个啥组织规定的一些对象，不管任何浏览器都应该有的，例如Array、Object等，当然ie6这种水货很有可能没有。！！！

* 指出下列代码的区别：
```javascript
function Person(){} 
var person = Person(); 
var person = new Person();
```
	* 1、定义一个函数为Person()　　2、定义一个匿名函数指向person　　3、实例化一个person、原型来自于函数Person

* `.call` 和 `.apply` 的区别是什么？
	* 参数不同。call是给每个argument，.apply是給一个参数组数。

* 请解释 `Function.prototype.bind` 的作用？

* 你何时优化自己的代码？
	* [JavaScript代码优化](http://www.lyblog.net/2013/209.html)

* 你能解释一下 JavaScript 中的继承是如何工作的吗？
	* [原型继承](http://www.2cto.com/kf/201404/296276.html)
	* 创建了一个实例。这个实例是一个具有__proto__属性的空对象，并且__proto__指向F.prototype
	* 初始化实例。将arguments 和 this赋予函数F。
	* 返回这个实例。

* 在什么时候你会使用 `document.write()`？
	* 大多数生成的广告代码依旧使用 `document.write()`，虽然这种用法会让人很不爽。

* 请指出浏览器特性检测，特性推断和浏览器 UA 字符串嗅探的区别？

* 请尽可能详尽的解释 AJAX 的工作原理。
	* 非ajax是把要提交的内容放在submit里面，浏览器刷新提交数据。ajax即异步数据刷新，将要提交的数据与服务器接口交换数据，将得到的数据返回用于重组dom元素，以及改变一些页面效果。
	* 动态添加script标签，script是不存在跨域问题的，所以可以跨域以get方式访问异域的数据。要跨域以post方式，需要使用iframe标签。ajax是使用XMLHttpRequest来和服务器进行异步通信，所以原理完全不同。

* 请解释 JSONP 的工作原理，以及它为什么不是真正的 AJAX。
	* JSON是一种数据交换格式，而JSONP是一种依靠开发人员的聪明才智创造出的一种非官方跨域数据交互协议。我们拿最近比较火的谍战片来打个比方，JSON是地下党们用来书写和交换情报的“暗号”，而JSONP则是把用暗号书写的情报传递给自己同志时使用的接头方式。看到没？一个是描述信息的格式，一个是信息传递双方约定的方法。

* 你使用过 JavaScript 模板系统吗？
	* 如有使用过，请谈谈你都使用过哪些库，比如 Mustache.js，Handlebars 等等。
	* 大量的正则表达式用于替换掉html中代表数据的内容。生成静态的html页面

* 请解释变量声明提升。
	* 在中间声明的函数，会提升到最先去声明，但是赋值位置不会提升。

* 请描述下事件冒泡机制。
	* 点击document中的div ，也会触发到document的click事件，这就是冒泡啦，！如果要停止冒泡，ie下e.returnValue = false。ff下,stop啥的。

* "attribute" 和 "property" 的区别是什么？
	* DOM元素含有的这两个东西，虽然完全不是一回事，但却又紧密联系在一体，不细细体会，还真不好分清。Property-属性，就像C#等高级语言可以.(dot)获取或者设置其值；Attribute-特性，每一个dom元素都有一个attributes属性来存放所有的attribute节点，通过getAttribute()和setAttribute()方法来进行获取和操作。
	* [js中Property和Attribute的区别是什么](http://www.kqiqi.com/knowledge/program/1078.html)

* 为什么扩展 JavaScript 内置对象不是好的做法？
	* 每一个对象都有这个方法，有时候是多余的。

* 为什么扩展 JavaScript 内置对象是好的做法？
	* 方便使用，不用记新的命名空间，直接在对象后面点就行了。

* 请指出 document load 和 document ready 两个事件的区别。
	* ready是在dom加载之后，图片加载之前，load是所有东西准备就绪之后。

* `==` 和 `===` 有什么不同？
	* 三个等的话，是要求类型也相同，1==true是ok的，但是1===true是false;

* 你如何从浏览器的 URL 中获取查询字符串参数。
	* location.href就是地址。再用正则或substring提取。

* 请解释一下 JavaScript 的同源策略。
	* 域名，协议，端口相同才能被执行。防止其它网页对不同域不同协议不同端口网页的修改。

* 请描述一下JavaScript的继承模式。
	* 我只用一种哈。就是把子类的prototype继承父类。   例 ： children.prototype = new perent();

* 如何实现下列代码：
```javascript
[1,2,3,4,5].duplicator(); // [1,2,3,4,5,1,2,3,4,5]
```
```javascript 
	Array.prototype.duplicator = function(){
	　　var l = this.length,i;
	　　for(i=0;i<l;i++){
	　　　this.push(this[i])　
   		}
	}
```

* 描述一种 JavaScript 中实现 memoization(避免重复运算)的策略。
	* 开定时器

* 什么是三元表达式？“三元” 表示什么意思？
	* a>b?a:b

* 函数的参数元是什么？

* 什么是 `"use strict";` ? 使用它的好处和坏处分别是什么？
	* 严格模式会导致出现错误就终止了。 开发时候使用一下可以防bug.

	* 如果给JavaScript代码标志为“严格模式”，则其中运行的所有代码都必然是严格模式下的。
	* 其一：如果在语法检测时发现语法问题，则整个代码块失效，并导致一个语法异常。
	* 其二：如果在运行期出现了违反严格模式的代码，则抛出执行异常。
	* 注：经过测试IE6,7,8,9均不支持严格模式。
	* JavaScript代码“严格模式”使用方法：
	* 严格模式需要使用字符串序列：
	* "use strict"
	* 在如下位置加入可以开启相应代码块中的严格模式：
	* 1.必须在全局代码的开始处加入。
	* 2.在eval代码开始处加入。
	* 3.在函数声明代码开始处加入。
	* 4.在new Function()所传入的body参数块开始加入。
	* 例1：
	* var num =012;alert(num);
	* 在非严格模式下，可以使用0（零）开头前缀声明8进制。显示10。
	* 但是在严格模式下，会产生错误。
	* "use strict";
	* var num =012;
	* alert(num);
	* 测试结果：
	* IE6,7,8,9均显示10。
	* FF报错：octal literals and octal escape sequences are deprecated
	* Chrome报错：Uncaught SyntaxError: Octal literals are not allowed in strict mode.
	* Opera报错：Syntax error at line 3 while loading: Invalid character var num = 012;
	* 如果使用严格模式，除了0（零）开头前缀8进制以外还有：
	* 1.在代码中不能使用一些扩展的保留字：
	* implements,interface,let,package,private,public,static,yield
	* 2.with语句也不能使用。
	* 3.不能声明或重写eval和arguments两个标识符。
	* 4.不能用delete 删除显式声明的标识符，名称或具名函数。

-  eval是做什么的？ 

		它的功能是把对应的字符串解析成JS代码并运行；
		应该避免使用eval，不安全，非常耗性能（2次，一次解析成js语句，一次执行）。


-  写一个通用的事件侦听器函数。

			// event(事件)工具集，来源：github.com/markyun
			markyun.Event = {
				// 页面加载完成后
				readyEvent : function(fn) {
					if (fn==null) {
						fn=document;
					}
					var oldonload = window.onload;
					if (typeof window.onload != 'function') {
						window.onload = fn;
					} else {
						window.onload = function() {
							oldonload();
							fn();
						};
					}
				},
				// 视能力分别使用dom0||dom2||IE方式 来绑定事件
				// 参数： 操作的元素,事件名称 ,事件处理程序
				addEvent : function(element, type, handler) {
					if (element.addEventListener) {
						//事件类型、需要执行的函数、是否捕捉
						element.addEventListener(type, handler, false);
					} else if (element.attachEvent) {
						element.attachEvent('on' + type, function() {
							handler.call(element);
						});
					} else {
						element['on' + type] = handler;
					}
				},
				// 移除事件
				removeEvent : function(element, type, handler) {
					if (element.removeEnentListener) {
						element.removeEnentListener(type, handler, false);
					} else if (element.datachEvent) {
						element.detachEvent('on' + type, handler);
					} else {
						element['on' + type] = null;
					}
				}, 
				// 阻止事件 (主要是事件冒泡，因为IE不支持事件捕获)
				stopPropagation : function(ev) {
					if (ev.stopPropagation) {
						ev.stopPropagation();
					} else {
						ev.cancelBubble = true;
					}
				},
				// 取消事件的默认行为
				preventDefault : function(event) {
					if (event.preventDefault) {
						event.preventDefault();
					} else {
						event.returnValue = false;
					}
				},
				// 获取事件目标
				getTarget : function(event) {
					return event.target || event.srcElement;
				},
				// 获取event对象的引用，取到事件的所有信息，确保随时能使用event；
				getEvent : function(e) {
					var ev = e || window.event;
					if (!ev) {
						var c = this.getEvent.caller;
						while (c) {
							ev = c.arguments[0];
							if (ev && Event == ev.constructor) {
								break;
							}
							c = c.caller;
						}
					}
					return ev;
				}
			}; 



-  Node.js的适用场景？

		高并发、聊天、实时消息推送

-  介绍js的基本数据类型。

		number,string,boolean,object,undefined
	
-  Javascript如何实现继承？

		通过原型和构造器
	
-  ["1", "2", "3"].map(parseInt) 答案是多少？

		 [1, NaN, NaN] 因为 parseInt 需要两个参数 (val, radix) 但 map 传了 3 个 (element, index, array)

-  如何创建一个对象? （画出此对象的内存图）

		  function Person(name, age) {
		    this.name = name;
		    this.age = age;
		    this.sing = function() { alert(this.name) } 
		  } 


-  谈谈This对象的理解。

		this是js的一个关键字，随着函数使用场合不同，this的值会发生变化。
	
	    但是有一个总原则，那就是this指的是调用函数的那个对象。
		
	    this一般情况下：是全局对象Global。 作为方法调用，那么this就是指这个对象	

-  事件是？IE与火狐的事件机制有什么区别？ 如何阻止冒泡？ 

		 1. 我们在网页中的某个操作（有的操作对应多个事件）。例如：当我们点击一个按钮就会产生一个事件。是可以被 JavaScript 侦测到的行为。  
		 2. 事件处理机制：IE是事件冒泡、火狐是 事件捕获；
		 3. ev.stopPropagation();

-  什么是闭包（closure），为什么要用它？


		执行say667()后,say667()闭包内部变量会存在,而闭包内部函数的内部变量不会存在.使得Javascript的垃圾回收机制GC不会收回say667()所占用的资源，因为say667()的内部函数的执行需要依赖say667()中的变量。这是对闭包作用的非常直白的描述.
  
		  function say667() {
			// Local variable that ends up within closure
			var num = 666;
			var sayAlert = function() { alert(num); }
			num++;
			return sayAlert;
		}
		 
		 var sayAlert = say667();
		 sayAlert()//执行结果应该弹出的667  

-  如何判断一个对象是否属于某个类？
		
 		  使用instanceof （待完善）

	       if(a instanceof Person){
	           alert('yes');
	       }

-  new操作符具体干了什么呢?

			 1、创建一个空对象，并且 this 变量引用该对象，同时还继承了该函数的原型。
	  	  	 2、属性和方法被加入到 this 引用的对象中。
	 		 3、新创建的对象由 this 所引用，并且最后隐式的返回 this 。
		    
		var obj  = {};
		obj.__proto__ = Base.prototype;
		Base.call(obj); 

-  Javascript中，有一个函数，执行时对象查找时，永远不会去查找原型，这个函数是？
  
		hasOwnProperty

-  JSON 的了解？
		
		JSON(JavaScript Object Notation) 是一种轻量级的数据交换格式。
		它是基于JavaScript的一个子集。数据格式简单, 易于读写, 占用带宽小
        {'age':'12', 'name':'back'}

-  js延迟加载的方式有哪些？
		
		defer和async、动态创建DOM方式（用得最多）、按需异步载入js


-  同步和异步的区别?
	* javascript 异步表示async，指：代码执行不按顺序，‘跳过’执行，待其他某些代码执行完后，再来执行，称为“异步”。
 
	* javascript同步表示sync，指：代码依次执行。
 
	* javascript所谓的“线程”，就是这样一种概念
 
	* 这种情况容易出现在 ajax 当中，因为ajax最可能，也最多用到async 或者 sync的概念属性。

-  如何解决跨域问题?	 
		jsonp、 iframe、window.name、window.postMessage、服务器上设置代理页面

-  模块化怎么做？
		
	 [ 立即执行函数](http://benalman.com/news/2010/11/immediately-invoked-function-expression/),不暴露私有成员
		
		    var module1 = (function(){
		    　　　　var _count = 0;
		    　　　　var m1 = function(){
		    　　　　　　//...
		    　　　　};
		    　　　　var m2 = function(){
		    　　　　　　//...
		    　　　　};
		    　　　　return {
		    　　　　　　m1 : m1,
		    　　　　　　m2 : m2
		    　　　　};
		    　　})(); 

-  AMD（Modules/Asynchronous-Definition）、CMD（Common Module Definition）规范区别？

-  异步加载的方式有哪些？

			
	      (1) defer，只支持IE
	      
	      (2) async：
	      
	      (3) 创建script，插入到DOM中，加载完毕后callBack
	  
- documen.write和 innerHTML的区别
			  
document.write只能重绘整个页面

innerHTML可以重绘页面的一部分
		  

-  .call() 和 .apply() 的区别？

						
		  例子中用 add 来替换 sub，add.call(sub,3,1) == add(3,1) ，所以运行结果为：alert(4); 
		
		  注意：js 中的函数其实是对象，函数名是对 Function 对象的引用。
		 
			function add(a,b)
			{
			    alert(a+b);
			}
			
			function sub(a,b)
			{
			    alert(a-b);
			}
			
			add.call(sub,3,1);  

####[[⬆]](#toc) <a name='jquery'>jQuery 相关问题：</a>

* 解释"chaining"。
	* 通过 jQuery，您可以把动作/方法链接起来。
	* Chaining 允许我们在一条语句中允许多个 jQuery 方法（在相同的元素上）。


* 解释"deferreds"。
	* [jQuery的deferred对象详解](http://www.ruanyifeng.com/blog/2011/08/a_detailed_explanation_of_jquery_deferred_object.html)

* 你知道哪些针对 jQuery 的优化方法。
	* [jQuery的性能优化](http://www.open-open.com/lib/view/open1388202452360.html)

* 请解释 `.end()` 的用途。
	* 可以一次操作多个元素，而且end( )就是要返回前一个对象，重新再选择一次

* 你如何给一个事件处理函数命名空间，为什么要这样做？

* 请说出你可以传递给 jQuery 方法的四种不同值。
	* 选择器（字符串），HTML（字符串），回调函数，HTML元素，对象，数组，元素数组，jQuery对象等。

* 什么是效果队列？

* 请指出 `.get()`，`[]`，`eq()` 的区别。
	* eq返回的是一个jquery对象 [],get返回的是一个html 对象数组
返回的是jQuery对象，就可以继续调用其他方法，返回的是html数组就不能调用jQuery的其他方法

* 请指出 `.bind()`，`.live()` 和 `.delegate()` 的区别。
	* [Query的.bind()、.live()和.delegate()之间区别](http://www.cnblogs.com/leejersey/archive/2013/08/12/3253964.html)

* 请指出 `$` 和 `$.fn` 的区别，或者说出 `$.fn` 的用途。
	* jQuery.extend() 的调用并不会把方法扩展到对象的实例上，引用它的方法也需要通过jQuery类来实现，如jQuery.init()
	*而 jQuery.fn.extend()的调用把方法扩展到了对象的prototype上，所以实例化一个jQuery对象的时候，它就具有了这些方法，这是很重要的

* 请优化下列选择器：
```javascript
$(".foo div#bar:eq(0)")
```

-  Jquery与jQuery UI 有啥区别？ 

			
		*jQuery是一个js库，主要提供的功能是选择器，属性修改和事件绑定等等。

		*jQuery UI则是在jQuery的基础上，利用jQuery的扩展性，设计的插件。
         提供了一些常用的界面元素，诸如对话框、拖动行为、改变大小行为等等


-  JQuery的源码看过吗？能不能简单说一下它的实现原理？
	* 在 jQuery 中， jQuery 对象实际上是一个仿数组的对象，代表通过选择器得到的所有 DOM 对象的集合，它像数组一样有 length 属性，表示代表的 DOM 对象的个数，还可以通过下标进行遍历。 
	* 95 行的 jQuery.each 是 jQuery 中用来遍历这个仿数组，对其中的每个元素进行遍历处理的基本方法，callback 表示处理这个 DOM 对象的函数。通常情况下，我们并不使用这个方法，而是使用 jQuery 对象的 each 方法进行遍历。jQuery 对象的 css 和 text 方法在内部实际上使用 jQuery 对象的 each 方法对所选择的元素进行处理。 

-  jquery 中如何将数组转化为json字符串，然后再转化回来？
	* [知乎](http://www.zhihu.com/question/22443850)
			
	* jQuery中没有提供这个功能，所以你需要先编写两个jQuery的扩展：
 
		$.fn.stringifyArray = function(array) {
		    return JSON.stringify(array)
		}
		
		$.fn.parseArray = function(array) {
		    return JSON.parse(array)
		} 

		然后调用：
		$("").stringifyArray(array)


-  针对 jQuery 的优化方法？

		*基于Class的选择性的性能相对于Id选择器开销很大，因为需遍历所有DOM元素。

		*频繁操作的DOM，先缓存起来再操作。用Jquery的链式调用更好。   
         比如：var str=$("a").attr("href");

		*for (var i = size; i < arr.length; i++) {}
         for 循环每一次循环都查找了数组 (arr) 的.length 属性，在开始循环的时候设置一个变量来存储这个数字，可以让循环跑得更快： 
         for (var i = size, length = arr.length; i < length; i++) {}



-  如何编写高性能的Javascript？
	* [编写高性能JavaScript](http://www.topthink.com/topic/3316.html)
	* [浅谈编写高性能的Javascript代码](http://developer.51cto.com/art/200906/131335.htm)

-  那些操作会造成内存泄漏？
			 
	    内存泄漏指任何对象在您不再拥有或需要它之后仍然存在。
        垃圾回收器定期扫描对象，并计算引用了每个对象的其他对象的数量。如果一个对象的引用数量为 0（没有其他对象引用过该对象），或对该对象的惟一引用是循环的，那么该对象的内存即可回收。

        setTimeout 的第一个参数使用字符串而非函数的话，会引发内存泄漏。
		闭包、控制台日志、循环（在两个对象彼此引用且彼此保留时，就会产生一个循环）

-  JQuery一个对象可以同时绑定多个事件，这是如何实现的？
	1、jQuery("#id").click(func1).mouseover(func2)//方法连写，func为方法的名字
	2、jQuery("#id").click(function(){//你的具体方法实现}),mouser(function(){//你的具体方法实现});
	3、jQuery("#id").bind("click mouseover",func)//两个事件中间有空格 ，func为方法的名字
	4、jQuery("#id").bind("load scroll",function(){//你的具体方法实现});

- 如何判断当前脚本运行在浏览器还是node环境中？（阿里）
			
		通过判断Global对象是否为window，如果不为window，当前脚本没有运行在浏览器中

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

####[[⬆]](#toc) <a name='other'>其他问题：</a>


- 你遇到过比较难的技术问题是？你是如何解决的？

- 常使用的库有哪些？常用的前端开发工具？开发过什么应用或组件？

- 页面重构怎么操作？
	* 编写 CSS、让页面结构更合理化，提升用户体验，实现良好的页面效果和提升性能。

- 列举IE 与其他浏览器不一样的特性？

- 99%的网站都需要被重构是那本书上写的？
	* 《重构之美》

- WEB应用从服务器主动推送Data到客户端有那些方式？
	* [Web端服务器推送技术原理分析及dwr框架简单的使用](http://blog.csdn.net/wiki2star/article/details/17306607)

- 对Node的优点和缺点提出了自己的看法？

		
		*（优点）因为Node是基于事件驱动和无阻塞的，所以非常适合处理并发请求，
          因此构建在Node上的代理服务器相比其他技术实现（如Ruby）的服务器表现要好得多。
		  此外，与Node代理服务器交互的客户端代码是由javascript语言编写的，
	      因此客户端和服务器端都用同一种语言编写，这是非常美妙的事情。

		*（缺点）Node是一个相对新的开源项目，所以不太稳定，它总是一直在变，
          而且缺少足够多的第三方库支持。看起来，就像是Ruby/Rails当年的样子。


- 你有哪些性能优化的方法？

		 （看雅虎14条性能优化原则）。
	
		  （1） 减少http请求次数：CSS Sprites, JS、CSS源码压缩、图片大小控制合适；网页Gzip，CDN托管，data缓存 ，图片服务器。
		
		  （2） 前端模板 JS+数据，减少由于HTML标签导致的带宽浪费，前端用变量保存AJAX请求结果，每次操作本地变量，不用请求，减少请求次数
		
		  （3） 用innerHTML代替DOM操作，减少DOM操作次数，优化javascript性能。
		
		  （4） 当需要设置的样式很多时设置className而不是直接操作style。
		
		  （5） 少用全局变量、缓存DOM节点查找的结果。减少IO读取操作。
		
		  （6） 避免使用CSS Expression（css表达式)又称Dynamic properties(动态属性)。
		
		  （7） 图片预加载，将样式表放在顶部，将脚本放在底部  加上时间戳。
		
		  （8） 避免在页面的主体布局中使用table，table要等其中的内容完全下载之后才会显示出来，显示比div+css布局慢。

- http状态码有那些？分别代表是什么意思？

		100-199 用于指定客户端应相应的某些动作。 
		200-299 用于表示请求成功。 
		300-399 用于已经移动的文件并且常被包含在定位头信息中指定新的地址信息。 
		400-499 用于指出客户端的错误。400	1、语义有误，当前请求无法被服务器理解。401	当前请求需要用户验证 403	服务器已经理解请求，但是拒绝执行它。
		500-599 用于支持服务器错误。 503 – 服务不可用

- 一个页面从输入 URL 到页面加载显示完成，这个过程中都发生了什么？（流程说的越详细越好）

			查找浏览器缓存 
		    DNS解析、查找该域名对应的IP地址、重定向（301）、发出第二个GET请求
		    进行HTTP协议会话
		    客户端发送报头(请求报头)
		    服务器回馈报头(响应报头)
		    html文档开始下载
		    文档树建立，根据标记请求所需指定MIME类型的文件
		    文件显示
			[
			浏览器这边做的工作大致分为以下几步：
			
			加载：根据请求的URL进行域名解析，向服务器发起请求，接收文件（HTML、JS、CSS、图象等）。
			
			解析：对加载到的资源（HTML、JS、CSS等）进行语法解析，建议相应的内部数据结构（比如HTML的DOM树，JS的（对象）属性表，CSS的样式规则等等）
			}

- 除了前端以外还了解什么其它技术么？你最最厉害的技能是什么？

- 你常用的开发工具是什么，为什么？ sublime

- 对前端界面工程师这个职位是怎么样理解的？它的前景会怎么样？

		     前端是最贴近用户的程序员，比后端、数据库、产品经理、运营、安全都近。
			1、实现界面交互
			2、提升用户体验
			3、有了Node.js，前端可以实现服务端的一些事情
			

		前端是最贴近用户的程序员，前端的能力就是能让产品从 90分进化到 100 分，甚至更好，
        
         参与项目，快速高质量完成实现效果图，精确到1px；
        
         与团队成员，UI设计，产品经理的沟通；
        
         做好的页面结构，页面重构和用户体验；
        
         处理hack，兼容、写出优美的代码格式；
        
         针对服务器的优化、拥抱最新前端技术。

- 加班的看法？


   		加班就像借钱，原则应当是------救急不救穷
	


- 平时如何管理你的项目？

				先期团队必须确定好全局样式（globe.css），编码模式(utf-8) 等；

				编写习惯必须一致（例如都是采用继承式的写法，单样式都写成一行）；
			
				标注样式编写人，各模块都及时标注（标注关键样式调用的地方）；
			
				页面进行标注（例如 页面 模块 开始和结束）；
			
				CSS跟HTML 分文件夹并行存放，命名都得统一（例如style.css）；
			
				JS 分文件夹存放 命名以该JS功能为准的英文翻译。
			
				图片采用整合的 images.png png8 格式文件使用 尽量整合在一起使用方便将来的管理

- 如何设计突发大规模并发架构？


- 说说最近最流行的一些东西吧？常去哪些网站？ 

			Node.js、Mongodb、npm、MVVM、MEAN、three.js 

- 移动端（Android IOS）怎么做好用户体验?

			清晰的视觉纵线、信息的分组、极致的减法、
			利用选择代替输入、标签及文字的排布方式、
			依靠明文确认密码、合理的键盘利用、


- 你认为怎样才是全端工程师（Full Stack developer）？ 



- 想问公司的问题？
		
			问公司问题：
			目前关注哪些最新的Web前端技术（未来的发展方向）？
			前端团队如何工作的（实现一个产品的流程）？
			公司的薪资结构是什么样子的？


####[[⬆]](#toc) <a name='web'>优质网站推荐：</a>

1. 极客标签：		 http://www.gbtags.com/


2. 码农周刊：		 http://weekly.manong.io/issues/


3. 前端周刊：		 http://www.feweekly.com/issues


9. 极客头条： 	 http://geek.csdn.net/


3. Startup News：http://news.dbanotes.net/


4. Hacker News： https://news.ycombinator.com/news  


7. InfoQ：  		 http://www.infoq.com/ 


10. w3cplus：     http://www.w3cplus.com/


10. Stack Overflow： http://stackoverflow.com/ 


6. Atp：  		 http://atp-posts.b0.upaiyun.com/posts/ 


