# 第二节 http/dns

## 1  前端基础学习——HTTP图解笔记

**参考网址：http://blog.sina.com.cn/s/blog_920dd2090102wfx0.html**

##2 学习前端前必知的——HTTP协议详解
**参考网址：http://www.cnblogs.com/chaoran/p/4783633.html**

##3 深入理解HTTP协议
**参考网址：http://www.360doc.com/content/10/0930/17/3668821_57590979.shtml**
##4 DNS
DNS（Domain Name System，域名系统），因特网上作为域名和IP地址相互映射的一个分布式数据库，能够使用户更方便的访问互联网，而不用去记住能够被机器直接读取的IP数串。通过主机名，最终得到该主机名对应的IP地址的过程叫做域名解析（或主机名解析）。DNS协议运行在UDP协议之上，使用端口号53。在RFC文档中RFC 2181对DNS有规范说明，RFC 2136对DNS的动态更新进行说明，RFC 2308对DNS查询的反向缓存进行说明。

###4.1DNS冗余
 为保证服务的高可用性，DNS要求使用多台名称服务器冗余支持每个区域。
某个区域的资源记录通过手动或自动方式更新到单个主名称服务器（称为主 DNS服务器）上，主 DNS 服务器可以是一个或几个区域的权威名称服务器。其它冗余名称服务器（称为辅 DNS 服务器）用作同一区域中主服务器的备份服务器，以防主服务器无法访问或宕机。辅 DNS服务器定期与主 DNS 服务器通讯，确保它的区域信息保持最新。如果不是最新信息，辅 DNS服务器就会从主服务器获取最新区域数据文件的副本。这种将区域文件复制到多台名称服务器的过程称为区域复制。
###4.2域名结构
通常 Internet 主机域名的一般结构为：主机名.三级域名.二级域名.顶级域名。 Internet 的顶级域名由 Internet网络协会域名注册查询负责网络地址分配的委员会进行登记和管理，它还为 Internet的每一台主机分配唯一的 IP 地址。全世界现有三个大的网络信息中心： 位于美国的 Inter-NIC，负责美国及其他地区； 位于荷兰的RIPE-NIC，负责欧洲地区；位于日本的APNIC ，负责亚太地区。
###4.3解析器
解析器，或另一台DNS服务器递归代表的情况下，域名解析器，协商使用递归服务，使用查询头位。解析通常需要遍历多个名称服务器，找到所需要的信息。然而，一些解析器的功能更简单地只用一个名称服务器进行通信。这些简单的解析器依赖于一个递归名称服务器（称为“存根解析器”），为他们寻找信息的执行工作。
###4.4DNS服务器
提供DNS服务的是安装了DNS服务器端软件的计算机。服务器端软件既可以是基于类linux操作系统，也可以是基于Windows操作系统的。装好DNS服务器软件后，您就可以在您指定的位置创建区域文件了，所谓区域文件就是包含了此域中名字到IP地址解析记录的一个文件。