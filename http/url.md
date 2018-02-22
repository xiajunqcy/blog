# URI 
### URI 基础知识
**URI**：统一资源标志符（Uniform Resource Identifier）
**URL**：统一资源定位符（uniform resource location）
URI与URL都是定位资源位置的，就是表示这个资源的位置信息，就像经纬度一样可以表示你在世界的哪个角落。URI是一种宽泛的含义更广的定义，而URL则是URI的一个子集，就是说URL是URI的一部分

### URI格式
URL与URI很像，两者的格式几乎差不多，但是我们接触的还是URL比较多，就以URL为例说明
URL提供了一种访问定位因特网上任意资源的手段，但是这些资源可以通过不同的方法（例如HTTP、FTP、SMTP）来访问，不管怎样，他都基本上由9个部分构成：
```
<scheme>://<user>:<password>@<host>:<port>/<path>;<params>?<query>#<fragment>
```
- **scheme**：获取资源使用的协议，例如http、ftp等，没有默认值
- **user:password**：用户名与密码，这个是一个特殊的存在，一般访问ftp时会用到，他显示的表明了访问资源的用户名与密码。但是这个可以不写，不写的话可能会让你输入用户名密码
- **host**：主机，访问那台主机，有时候可以是IP，有时候是主机名，例如www.baidu.com
- **port**：端口，访问主机时的端口，如果http访问默认80，可以省略。
- **path**：通过host:port我们能找到主机，但是主机上文件很多，通过path则可以定位具体文件。例如www.baidu.com/file/index.html。则path是/file/index.html，表示我们访问/file/index.html这个文件，他很像linux上的路径。
- **params**：这个很少见，主要作用就是像服务器提供额外的参数，用来表示本次请求的一些特性。例如ftp传输模式有两种，二进制和文本，你肯定不希望使用文本形式传输二进制图片，这样你的图片下载下来后可能没法看了。为了向应用程序提供更丰富的信息，URL中有个专门的部分来表示这种参数。例如ftp://file.qiandu.com/pub/guid.pdf;type=d其中的type=d就是params
- **query**：通过get方式请求的参数，例如：www.qiandu.com/index.html?username=dgh&passwd=123
- **fragment**：例如www.qiandu.com/index.html#1。当html页面比较长时，我们通常会将其分为好几段，#1就可以 快速定位到某一段

### URI常见的协议有哪些
常见的协议：

|协议|描述|
|-|-|
|data|链接中直接包含的Base64编码数据|
|file|本地磁盘的文件|
|ftp|FTP服务器|
|http|使用超文本传输协议的国际互联网服务器|
|mailto|电子邮件地址|
|magnet|可以通过对等网络下载的资源|
|telnet|与基于Telnet的服务连接|