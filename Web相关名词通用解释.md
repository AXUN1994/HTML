## Web 建站技术中，HTML、HTML5、XHTML、CSS、SQL、JavaScript、PHP、ASP.NET、Web Services 是什么？
> 文中内容总结来自于知乎，链接：[https://www.zhihu.com/question/22689579](https://www.zhihu.com/question/22689579)
### 1. 在浏览器地址栏输入地址的访问过程
浏览器和服务器交流，服务器和数据库交流。
### 2. HTML:超文本标记语言
### 3. HTML5：HTML新的标准
### 4. CSS：层叠样式表
### 5. XHTML：XML和HTML的结合体，对语法要求比较严格
### 6. JavaScript:一种脚本语言，用来给页面添加动态效果 
### 7. AJAX：不用刷新就能与服务器进行交互，更新页面的一小部分
### 8. Web Server , Web Service
  要让这些形形色色的机器能够通过网络进行交互，我们就需要指明一种协议（比如 HTTP/HTTPS）和一种数据封装格式（比如 HTML/XML），Web Server 提供的 Web Service，指的就是这种协议+格式的交流体系。不过 Web Service 的生态系统和 HTML 的标准不一样，用户可以选择的协议和数据封装格式更多，普通的网站访问用的 HTTP + HTML 只是其中一种，一些封闭系统内的交流还可以自己定义一个协议和格式来用（比如 QQ）。

  Web Service 传输的数据再经由本地客户端（浏览器、QQ/微信，网游客户端等）的分析渲染，就能够以普通人能够理解的形式展现出来。此外还有一些 Web Service 并不是为普通用户设计的，像前面提到的微博API，是用来给程序猿进行二次开发的~ 

  除了提供 Web Service， Web Server 还会兼顾很多功能，包括提供缓存，平衡负载，这样在访问量比较大的时候能有有条不紊地接客。常见的现成的 Web Server 有开源的 Apache、Nginx和微软的IIS，你也可以用一些工具（比如 Node.js ）自己定制一个。因为 Web Server 需要比较好的性能，所以投产时用的 Web Server 通常是C/C++/Java写的，但是其实很多语言都可以写，而且配合上语言底层的优化和好的模型，其他语言写的 Web Server也可以有不错的表现。
### 9. 服务器脚本:服务器处理用户上传来的文件的，还可以接受用户发过来的各种请求，去操作服务器本地的文件or数据库的代码
### 10. PHP： 就是一种常见的用来写服务器脚本的语言
其实只要是能拿来写大家传输数据的通用接口（CGI）的语言都可以用来写服务器脚本
### 11. ASP.NET
  为了方便，我们在写服务器脚本的时候，通常还会用个同语言写的 Web Framework 来处理各种细节，防御一些常见的攻击，提供跨站认证（比如用已有的微博账号注册其他网站）的接口，利用cookie处理登陆状态和用户设置，生成网页模版之类的。如果你用 C# 或者 Visual Basic 写服务器脚本，就可以用 http://ASP.NET 这个框架实现这些功能，帮你省点麻烦。
### 12. 一个普通网站访问的过程
简单概括一下，对于我们普通的网站访问，涉及到的技术就是：


- 用户操作浏览器访问，浏览器向服务器发出一个 HTTP 请求；


- 服务器接收到 HTTP 请求，Web Server 进行相应的初步处理，使用服务器脚本生成页面；


- 服务器脚本（利用Web Framework）调用本地和客户端传来的数据，生成页面；


- Web Server 将生成的页面作为 HTTP 响应的 body，根据不同的处理结果生成 HTTP header，发回给客户端；


- 客户端（浏览器）接收到 HTTP 响应，通常第一个请求得到的 HTTP 响应的 body 里是 HTML 代码，于是对 HTML 代码开始解析；


- 解析过程中遇到引用的服务器上的资源（额外的 CSS、JS代码，图片、音视频，附件等），再向 Web Server 发送请求，Web Server 找到对应的文件，发送回来；
浏览器解析 HTML 包含的内容，用得到的 CSS 代码进行外观上的进一步渲染，JS 代码也可能会对外观进行一定的处理；


- 用户与页面交互（点击，悬停等等）时，JS 代码对此作出一定的反应，添加特效与动画；
交互的过程中可能需要向服务器索取或提交额外的数据（局部的刷新，类似微博的新消息通知），一般不是跳转就是通过 JS 代码（响应某个动作或者定时）向 Web Server 发送请求，Web Server 再用服务器脚本进行处理（生成资源or写入数据之类的），把资源返回给客户端，客户端用得到的资源来实现动态效果或其他改变。

注意这只是小网站里比较常见的模型，大网站为了解决规模问题还会有很多处理，每个环节都会有一些细微的差异，中间还会使用各种各样的工具减轻服务器的压力，提高效率，方便日常维护~
### 13. 延伸阅读
现在在这方面的应用热起来的语言有

- Python，对应常见的 Framework 包括知乎和Quora有用到的 Tornado（其实是自带 Framework 的 Web Server），社区很成熟的 Django （用户包括 Instagram、Pinterest）等
- Ruby，一般都用 Rails 这个 Framework，用户包括 Github、早期的 Twitter 等
- 逆天的 JavaScript，有了 Node.js 这个平台，Web Server、服务器脚本和浏览器脚本全都可以用 JavaScript 来写……Node.js上最常用的 Framework是Express
- 微软家的则跟着 http://ASP.NET 转移到了C# 或者 Visual Basic
- Erlang，擅长大规模的并发，不少游戏公司拿来写服务器，靠几十个工程师支撑几亿用户的， WhatsApp也是用的这个~

几种常见的架构包括：

- LAMP = Linux + Apache + MySQL + PHP（P还可能是Python或Perl。有时候L会改成W=Windows。），也就是服务器上的操作系统是 Linux，Web Server 用 Apache，数据库用 MySQL，服务器脚本用 PHP，这些都是开源技术，网站起步时用起来的成本会比较低，所以是普通网站里非常常见的架构（虽然对于发展得很大的网站会遇到很多瓶颈），Facebook就是这种，淘宝也曾经是。


- J2EE，Java 世界的架构，通常是企业用的（银行、大型公司,.etc），比较常见地还会搭配一种 UNIX 做操作系统，Apache 做 Web Server，Tomcat 转换 JSP 到 Java 给服务器程序用（其实它也自带 Web Server），Oracle 数据库等等。不一定拿来建站，常常用来提供企业里的各种需要用到网络的业务。我们学校教务系统就是用J2EE做的=。= 淘宝现在也是从LAMP转型到了这个。


- http://ASP.NET，微软家的架构，通常会搭配 Windows Server 操作系统，SQL Server 数据库，IIS 做 Web Server。StackOverflow和京东（曾经）就是这个架构。


- 神奇的MEAN架构，MongoDB做数据库，Express做 Web Framework，Angular 做前端的 JavaScript 框架，Node.js 用于编写 Web Server。神奇之处在于这几个东西的语言都是 JavaScript （MongoDB的实现不是，但与外界沟通用的语言是）。因为是比较新的架构，还有待时间的考验，不过被很多人（尤其是靠 JavaScript 吃饭的前端程序猿们）热切关注。


- 一般来说重点不在技术而且在乎成本的新网站比较喜欢用 LAMP，重视安全稳定和速度的企业和机构喜欢 J2EE，想省事的网站喜欢 http://ASP.NET，比较 Geek 的网站和创业公司喜欢折腾各种 Python、Ruby、Node.js世界的东西，Google 这样现成的技术都解决不了需求的超大型网站就自己折腾解决方案。




