# OSI 七层模型指什么

![网络层次介绍](https://sfault-image.b0.upaiyun.com/428/731/4287316384-57465f9fe6045_articlex)

**OSI** *（Open System Interconnection，开放系统互连）*
七层网络模型称为开放式系统互联参考模型 ，是一个逻辑上的定义，一个规范，它把网络从逻辑上分为了7层。每一层都有相关、相对应的物理设备，比如**路由器**_(网络层)_，**交换机**_(数据链路层)_。
OSI 七层模型是一种框架性的设计方法 ，建立七层模型的主要目的是为解决异种网络互连时所遇到的兼容性问题，其最主要的功能就是帮助不同类型的主机实现数据传输。它的最大优点是将**服务**、**接口**和**协议**这三个概念明确地区分开来，通过七个层次化的结构模型使不同的系统不同的网络之间实现可靠的通讯。

**分层的目的**
建立七层模型的主要目的是为解决异种网络互连时所遇到的兼容性问题。它的最大优点是将 **服务**、**接口**和 **协议**这三个概念明确地区分开来：

- 服务
  说明某一层为上一层提供一些什么功能
- 接口
  说明上一层如何使用下层的服务
- 协议
  涉及如何实现本层的服务

这样各层之间具有很强的独立性，互连网络中各实体采用什么样的协议是没有限制的，只要向上提供相同的服务并且不改变相邻层的接口就可以了。网络七层的划分也是为了使网络的不同功能模块（不同层次）分担起不同的职责。

 **分层的益处**
- 减轻问题的复杂程度，一旦网络发生故障，可迅速定位故障所处层次，便于查找和纠错。
- 在各层分别定义标准接口，使具备相同对等层的不同网络设备能实现互操作，各层之间则相对独立，一种高层协议可放在多种低层协议上运行
- 能有效刺激网络技术革新，因为每次更新都可以在小范围内进行，不需对整个网络动大手术

## 1. 物理层

从最底层开始
电脑直接需要相连，需要通过光缆、电缆、双绞线、无线电波等方式。
它主要规定了网络的一些电气特性，作用是负责传送0和1的电信号。

![物理层](http://www.ruanyifeng.com/blogimg/asset/201205/bg2012052903.png)

## 2.数据链路层

单纯的0和1没有任何意义，必须规定解读方式：多少个电信号算一组？每个信号位有何意义？
这就是"链路层"的功能，它在"物理层"的上方，确定了0和1的分组方式。

- **以太网协议**
    早期的时候，每家公司都有自己的电信号分组方式。逐渐地，一种叫做**以太网**_（Ethernet）_的协议，占据了主导地位
    以太网规定，一组电信号构成一个数据包，叫做**帧**_（Frame）_
    每一帧分成两个部分：**标头**_（Head）_和**数据**_（Data）_
    标头长度固定为18字节，数据长度为64~1500字节，如果数据过长，就得分割成多个帧进行发送
![以太网协议](http://www.ruanyifeng.com/blogimg/asset/201205/bg2012052904.png)

- **广播**
    以太网把数据包向本网络中所有计算机发送，让每台计算机自己判断，是否为接收方
    这种发送方式就叫做**广播**_（broadcasting）_

- **MAC地址**
    每一块网卡都有一个独一无二的MAC地址，长度是48个二进制位，通常用12个十六进制数表示。

    ```bash
    MAC Address
    00-B0-D0-86-BB-F7
    ```

 有了数据包的定义、网卡的MAC地址、广播的发送方式，数据链路层就可以在多台计算机之间传送数据了

## 3.网络层

互联网是由无数层级子网络共同组成的巨形网络，以太网协议只能解决子网络直接的传输
![网络层](http://www.ruanyifeng.com/blogimg/asset/201205/bg2012052914.png)
**网络层**的作用就是为了引进一套新地址，让不同子网络之间的计算机也能相互联通

- **IP协议**
  规定网络地址的协议，叫做IP协议。它所定义的地址，就被称为IP地址。
  目前，广泛采用的是IP协议第四版，简称IPv4
  这个版本规定，网络地址由32个二进制位组成

  ```bash
  Ip Address
  172.16.254.1
  10101100.00010000.11111110.00000001
  ```

习惯上，我们用分成四段的十进制数表示IP地址，从0.0.0.0一直到255.255.255.255
ip地址分为**网络**和**主机**两个部分
为了区分两个部分，需要使用**子网掩码**

- **IP数据包**
  根据IP协议发送的数据，就叫做IP数据包
  IP数据包包括**标头**和**数据**，IP数据包的总长度最大为65,535字节
  ，**标头**长度为20到60字节，**数据**部分最长为65,515字节
  ![IP数据包](http://www.ruanyifeng.com/blogimg/asset/201205/bg2012052910.png)

- **ARP协议**
  ARP协议用来从IP地址得到MAC地址，通过ARP协议，可以得到同一个子网络内的主机MAC地址，可以把数据包发送到任意一台主机之上

## 4.传输层

有了MAC地址和IP地址，已经可以在互联网上任意两台主机上建立通信。
一台主机上肯定不会只运行一个程序，数据传输到了电脑，还需要精确到程序，所以需要参数**端口**_(port)_，表示这个数据包到底供哪个程序（进程）使用"**传输层**"的功能，就是建立"端口到端口"的通信。相比之下，"**网络层**"的功能是建立"主机到主机"的通信。只要确定主机和端口，我们就能实现程序之间的交流。

- **UDP协议**
  现在，我们必须在数据包中加入端口信息，这就需要新的协议。最简单的实现叫做**UDP协议**，它的格式几乎就是在数据前面，加上端口号。
  ![UDP协议](http://www.ruanyifeng.com/blogimg/asset/201205/bg2012052912.png)
  
- **TCP协议**
 UDP协议的优点是比较简单，容易实现，但是缺点是可靠性较差，一旦数据包发出，无法知道对方是否收到。

 为了解决这个问题，提高网络可靠性，TCP协议就诞生了。这个协议非常复杂，但可以近似认为，它就是有确认机制的UDP协议，每发出一个数据包都要求确认。如果有一个数据包遗失，就收不到确认，发出方就知道有必要重发这个数据包了。

## 5.会话层

OSI会话层，主要功能是用来管理会话，细分为三大功能：

- 建立连接
  A、B两台电脑要通讯，首先必须建立一条他们之间的连接，OSI会话层会完成这个步骤；

- 保持连接
  连接建立后，当A、B通讯完了，A、B之间的连接不会立刻断开，OSI会话层会将建立好了的连接维持一段时间不中断，当A、B下次还要通讯时，可以直接使用之前建立好的那条连接；

- 断开连接
  一般一条连接有一个维持时间，当这条连接的维持时间到了后，OSI会话层会将该连接自动断开。而且A或者B重启、关机、手动执行断开连接的操作之后，OSI会话层也会将A、B之间的连接断开。

## 6.表示层

OSI表示层功能：数据的编码、翻译、压缩、解压缩、加密、解密，将数据翻译为相对应的编码格式，然后展现到应用程序中。

## 7.应用层

应用层是为用户提供的接口，定义了用户之间的交流方式。应用程序收到"传输层"的数据，接下来就要进行解读。

由于互联网是开放架构，数据来源五花八门，必须事先规定好格式，否则根本无法解读。

"应用层"的作用，就是规定应用程序的数据格式。

举例来说，TCP协议可以为各种各样的程序传递数据，比如Email、WWW、FTP等等。那么，必须有不同协议规定电子邮件、网页、FTP数据的格式，这些应用程序协议就构成了"应用层"。
