#### nginx

查看本机是否安装nginx:
ps -A |grep nginx 
sudo netstat -n -t -p -l

安装nginx：
sudo apt-get install nginx-extras


本地文件的配置？？？

是轻量级的 Web服务器、反向代理服务器、电子邮件（IMAP/POP3）代理服务器
占有内存少，并发能力强。

浏览器请求web服务器如nginx，如果请求的是静态的index.html，则nginx可以直接返回。但是如果请求的是index.php或者jsp，nginx根据配置发现不是静态资源，需要请求后端的服务。
后端服务器就充当反向代理的作用。????????
那么，nginx在请求后端服务时，需要以什么样的格式、发送给后端服务什么样的数据呢？CGI就是定义格式、数据的协议。

反向代理？？？
FCG-I->php：

cgi common gateway interface,接口协议
CGI 的一个进程处理完一个请求后退出，下一个请求来时再创建新进程。当访问量增大，并发存在，这种方式就不适合了。于是就有了fastcgi。

fastcgi（进程管理器） 像是一个常驻(long-live)型的CGI，它可以一直执行着，只要激活后，不会每次都要花费时间去fork一次。

一般情况下，FastCGI的整个工作流程是这样的：
1.Web Server启动时载入FastCGI进程管理器（IIS ISAPI或Apache Module)
2.FastCGI进程管理器自身初始化，启动多个CGI解释器进程(可见多个php-cgi)并等待来自Web Server的连接。
3.当客户端请求到达Web Server时，FastCGI进程管理器选择并连接到一个CGI解释器。 Web server将CGI环境变量和标准输入发送到FastCGI子进程php-cgi。
4.FastCGI 子进程完成处理后将标准输出和错误信息从同一连接返回Web Server。当FastCGI子进程关闭连接时， 请求便告处理完成。FastCGI子进程接着等待并处理来自FastCGI进程管理器(运行在Web Server中)的下一个连接。 在CGI模式中，php-cgi在此便退出了。

正则？？

grep命令行资料

文件搜索