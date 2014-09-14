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
	* 在完成功能的同时精良多考虑性能，安全性，兼容性，代码的扩展性。
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

* 你都使用哪些工具来测试代码的性能？
	* Profiler, JSPerf, Dromaeo

* 如果今年你打算熟练掌握一项新技术，那会是什么？
	* nodejs, Famo.us

* Long-Polling, Websockets, SSE(Server-Sent Event) 之间有什么区别？

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
	* 如果文档不分类型，各浏览器就会形成多种写法，假如IE用<title>标签作为标题、火狐浏览器用\<caption>标签作为标题，而另一种浏览器可能采用\<mytitle>，这对于开发者和用户来说简直是灾难。W3C（万 维网联盟World Wide Web Consortium）制作了对所有方面都平衡的分歧解决方案，并且各浏览器没有异议，于是用\<!doctype>（注意：作为一个特殊的标 签，它是不需要闭合的）标签来引入W3C的dtd文件，以达到规范页面的效果。这为浏览器的文档标准的统一以及开发人员和用户带了了便利。而html5不是基于SGML实现的，因此html不需要引入DTD，所以html5可以简单的声明一下\<!doctype html>。

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

* `data-`属性的作用是什么？
	* data-为前端开发者提供自定义的属性，这些属性集可以通过对象的dataset属性获取，不支持该属性的浏览器可以通过 getAttribute方法获取。

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

* 闭包会带来什么问题？怎么避免？

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