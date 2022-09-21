## 1.数据通信网络基础

### 通信与网络

* 华为设备图标

![image-20220912215211551](https://gitee.com/lynbz1018/image/raw/master/img/20220912215212.png)

* 常见术语
  * 头部 + 数据载荷 + 尾部 =封装> 数据报 =解封装> 数据载荷

![image-20220912220535350](https://gitee.com/lynbz1018/image/raw/master/img/20220912220536.png)

* 数据通信网络基本概念
  * 通过防火墙访问Internet

![image-20220912223415975](https://gitee.com/lynbz1018/image/raw/master/img/20220912223417.png)

* 交换机
  * 是距离终端用户最进的设备
  * 用于终端设备的网络接入
  * 二层交换

![image-20220912223718088](https://gitee.com/lynbz1018/image/raw/master/img/20220912223719.png)

* 路由器

![image-20220912224056508](https://gitee.com/lynbz1018/image/raw/master/img/20220912224057.png)

* 防火墙
  * 网络安全设备

![image-20220912224214523](https://gitee.com/lynbz1018/image/raw/master/img/20220912224215.png)

* 无线设备
  * 无线胖AP
  * 无线瘦AP 更多的功能放到AC上

![image-20220912224354838](https://gitee.com/lynbz1018/image/raw/master/img/20220912224356.png)



### 网络类型与网络拓扑

* 局域网LAN、广域网WAN

![image-20220913233317721](https://gitee.com/lynbz1018/image/raw/master/img/20220913233319.png)

* 局域网组成城域网，然后通过广域网的节点由城域网组成广域网

<img src="https://gitee.com/lynbz1018/image/raw/master/img/20220913233646.png" alt="image-20220913233645628" style="zoom:50%;" />



* 网络拓扑：用传输介质互联各种设备所呈现的结构化布局。

* 全网状型网络：可靠性最高，同时成本也会较高。

![image-20220913235020360](https://gitee.com/lynbz1018/image/raw/master/img/20220913235021.png)



### 网络工程与网络工程师

* 网络工程

机房里的网络设备通过传输介质连接起来

交换机、路由器都属于路由部分

用户通过AP等无线设备连接

![image-20220913235610152](https://gitee.com/lynbz1018/image/raw/master/img/20220913235611.png)

* 网络工程师

<img src="https://gitee.com/lynbz1018/image/raw/master/img/20220913235928.png" alt="image-20220913235927486" style="zoom:50%;" />



## 2.网络参考模型

### 网络参考模型

#### OSI参考模型

![image-20220915173927165](https://gitee.com/lynbz1018/image/raw/master/img/20220915173928.png)

#### TCP/IP参考模型

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220915181108303.png" alt="image-20220915181108303" style="zoom: 67%;" />

<img src="https://gitee.com/lynbz1018/image/raw/master/img/20220915181258.png" alt="image-20220915181256831" style="zoom:67%;" />

##### 应用层

* 应用层的PDU称为数据

<img src="https://gitee.com/lynbz1018/image/raw/master/img/20220915181826.png" alt="image-20220915181825663" style="zoom:67%;" />

##### 传输层

* 传输层的PDU 成为段

![image-20220915183101590](https://gitee.com/lynbz1018/image/raw/master/img/20220915183102.png)

* TCP的三次握手

![image-20220915184129695](https://gitee.com/lynbz1018/image/raw/master/img/20220915184130.png)

* Ack：上一个序列号+数据载荷长度

![image-20220915184738170](https://gitee.com/lynbz1018/image/raw/master/img/20220915184739.png)

​                                                                                                             Ack = a + 13 + 66

* 滑动窗口

![image-20220915190813885](https://gitee.com/lynbz1018/image/raw/master/img/20220915190815.png)

* 四次挥手
  * pc2收到断开请求 并发送收到报文后，会向pc1再发送一个请求断开报文

![image-20220915190948159](https://gitee.com/lynbz1018/image/raw/master/img/20220915190949.png)

##### 网络层

* 网络层中PDU称为包

<img src="https://gitee.com/lynbz1018/image/raw/master/img/20220915192842.png" alt="image-20220915192841274" style="zoom:67%;" />

##### 数据链路层

* 数据链路层的PDU 称为帧

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220915192922828.png" alt="image-20220915192922828" style="zoom:67%;" />

* 每一个网卡都有一个唯一的MAC地址
* 交换机会维护一个MAC地址表

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220915193119184.png" alt="image-20220915193119184" style="zoom: 67%;" />

* ARP地址解析协议

1. 发送一个数据报之前，需要MAC地址，**会先在ARP缓存中查找**
2. 如果缓存中没有，就会发送一个ARP请求报文，**目的地址全F进行广播**，收到MAC地址后再进行发送
3. 接收到arp请求的主机，会对目的ip和自己ip进行比较，相同的主机会**将发送的ip和mac地址存到自己的arp缓存中**
4. 收到arp request 的主机会再发送一个 arp reply

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220915194549465.png" alt="image-20220915194549465" style="zoom:50%;" />

##### 物理层

<img src="https://gitee.com/lynbz1018/image/raw/master/img/20220915195425.png" alt="image-20220915195424590" style="zoom:50%;" />



### 数据通信过程

* 发送方发送数据

![image-20220915201341378](https://gitee.com/lynbz1018/image/raw/master/img/20220915201342.png)

* 中间网络数据传输

发送方封装到物理层 

在交换机中解封到数据链路层获取MAC地址

在路由器中解封装到网络层获取IP地址

最终到目的主机解封装获取数据载荷

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220915202419969.png" alt="image-20220915202419969" style="zoom:67%;" />

* 接收方数据解封装

![image-20220915202950193](https://gitee.com/lynbz1018/image/raw/master/img/20220915202951.png)



  

## 3.华为VRP系统

### 华为VRP系统概述

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220918172310494.png" alt="image-20220918172310494" style="zoom: 67%;" />

* 可以将控制平面和转发平面分离
* 可以解决不同产品在数据链路层使用不同的硬件而对网络层的影响

![image-20220918172823319](https://gitee.com/lynbz1018/image/raw/master/img/20220918172824.png)

* VRP发展进程

<img src="https://gitee.com/lynbz1018/image/raw/master/img/20220918173243.png" alt="image-20220918173242614" style="zoom:67%;" />

* 文件系统

<img src="https://gitee.com/lynbz1018/image/raw/master/img/20220918173517.png" alt="image-20220918173516085" style="zoom:80%;" />

* 存储设备

![image-20220918174018038](https://gitee.com/lynbz1018/image/raw/master/img/20220918174019.png)

#### 设备管理

* 用户界面

![image-20220918174944624](https://gitee.com/lynbz1018/image/raw/master/img/20220918175119.png)

* 用户级别

![image-20220918175135167](https://gitee.com/lynbz1018/image/raw/master/img/20220918175136.png)

* WEB网管理方式
  * 主机和路由器必须网络可达的，即可以ping通

<img src="https://gitee.com/lynbz1018/image/raw/master/img/20220918175445.png" alt="image-20220918175444429" style="zoom:67%;" />

* 命令行-本地登录
  * 网络设备第一次通电配置 需要本地通电
  * console是网络设备上的借口

![image-20220918175803564](https://gitee.com/lynbz1018/image/raw/master/img/20220918175804.png)



<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220918175934145.png" alt="image-20220918175934145" style="zoom:67%;" />

* 远程登录
* ssh是加密登录 会对用户名和密码加密 别人抓包抓到了也不能用加密后的字符用于登录
* 终端和设备之间要可以ping通才可以连接

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220918180520646.png" alt="image-20220918180520646" style="zoom:67%;" />



<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220918221256254.png" alt="image-20220918221256254" style="zoom:80%;" />



### 华为VRP系统基本操作

* 配置任务
* 因为是全新没有配置过的路由器，所以第一次配置要用本地连接，通过串行口和console port

![image-20220918222547159](https://gitee.com/lynbz1018/image/raw/master/img/20220918222548.png)

```markdown
display version  // 查看版本信息
system-view  // 进入系统视图
sysname DAtacom-Router  // 更改设备名称
interface GigabitEthernet 0/0/1  // 进入接口视图
ip address 20.1.1.1 24  // 配置ip
undo ip address  // 删除上次配置
display this  // 查看当前视图的配置
quit  // 退会低级别的视图

save  // 保存
compare configuration  // 比较

save datacom.cfg  // 保存配置文件
dir // 查看
display startup  // 查看启动文件
startup saved-configuration datacom.cfg  // 设置启动文件
reset saved-configuration

reboot  // 重启设备
```

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220918230218348.png" alt="image-20220918230218348" style="zoom:80%;" />



## 4.网络层协议及IP编制

### 4.1网络层协议

* 对网络层的设备提供逻辑地址
* 负责数据报的寻址和转发
* 经常被提及的IP是指直接或者间接与IP协议有关的任何内容

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220918234348824.png" alt="image-20220918234348824" style="zoom:67%;" />

* TTL Time To Life 8bit，0-255
* 协议号指明了数据部分使用了什么样的协议，即指明传输层使用了什么协议。

![image-20220918235128932](https://gitee.com/lynbz1018/image/raw/master/img/20220918235130.png)

### 4.2IPv4地址介绍

#### IPv4地址定义

* 用于在网络中标识一个节点
* 用于IP报文在网络中寻址
* IPv4地址有32bit，用点分十进制表示

* 由 网络位 和 主机位 组成，后边要跟着网络掩码



#### IPv4地址分类方式

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220919001739829.png" alt="image-20220919001739829" style="zoom:80%;" />



* 主机位全为0是网络地址
* 主机位全为1是广播地址
* 可用地址数是2^n - 2

<img src="https://gitee.com/lynbz1018/image/raw/master/img/20220919002010.png" alt="image-20220919002009017" style="zoom:80%;" />

* 私网IP地址

![image-20220919002612105](https://gitee.com/lynbz1018/image/raw/master/img/20220919002613.png)

* 特殊IP地址

<img src="https://gitee.com/lynbz1018/image/raw/master/img/20220919002930.png" alt="image-20220919002929129" style="zoom:80%;" />



### 4.3子网划分

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220919235242825.png" alt="image-20220919235242825" style="zoom:80%;" />

* 在实际网络划分中，常常从主机数多的子网开始划分

### 4.4网际控制信息协议ICMP协议

* 用来在网络设备中传递各种差错和控制信息

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220919235556129.png" alt="image-20220919235556129" style="zoom:80%;" />



<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220920000005619.png" alt="image-20220920000005619" style="zoom:80%;" />

* ICMP 重定向

当路由检测到一台机器使用非最优路由时，回向该主机发送一个ICMP重定向报文，请求主机改变路由。

![image-20220920000324141](https://gitee.com/lynbz1018/image/raw/master/img/20220920000325.png)

* ICMP差错检测

用ping检测到达目的主机的可达性

<img src="https://gitee.com/lynbz1018/image/raw/master/img/20220920000651.png" alt="image-20220920000650834" style="zoom:67%;" />

* ICMP错误报告

Tracert通过每次更改TTL来获取每一条的超时报告报文，来追踪路径和通过时间戳来计算往返时间

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220920001112620.png" alt="image-20220920001112620" style="zoom:67%;" />



### 4.5IPv4地址配置及基本应用



* IP地址规划

应该是自顶向下，规划的目标是易管理、易扩展、利用率高

<img src="https://gitee.com/lynbz1018/image/raw/master/img/20220920001425.png" alt="image-20220920001424680" style="zoom:80%;" />



## 5.以太网交换基础

### 5.1以太网交换协议

* 以太网是当今局域网中最常用的通信协议标准
* 以太网是建立在CSMA/CD（载波监听多路访问/冲突检测）机制上的广播型网络

* 早期的以太网是共享式的发送数据帧前需要对网络进行监听
  * 先在是交换机组网以太网，交换机可以隔离冲突域，但是不能隔离广播域



* 冲突域

冲突域是连接在同一个共享介质上的所有节点的集合。

<img src="https://gitee.com/lynbz1018/image/raw/master/img/20220920225356.png" alt="image-20220920225355017" style="zoom: 50%;" />

* 广播域：广播报文所能到达的整个访问范围称为二层广播域

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220920225725160.png" alt="image-20220920225725160" style="zoom:50%;" />

* 以太网卡

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220920225909967.png" alt="image-20220920225909967" style="zoom:50%;" />



### 5.2以太网帧

* 以太网技术所使用的帧

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220920230359800.png" alt="image-20220920230359800" style="zoom:50%;" />

* 每一个网卡都有一个全球唯一的MAC地址来标识

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220920230728504.png" alt="image-20220920230728504" style="zoom:50%;" />

* MAC地址48bit，用12个十六进制数标识

* 前24位是IEEE分配的厂商代码 后24位是厂商自己分配的代码

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220920231314124.png" alt="image-20220920231314124" style="zoom:50%;" />

* 组播帧的从前开始数第八个是 1

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220920231806036.png" alt="image-20220920231806036" style="zoom:50%;" />

### 5.3以太网交换机介绍

* 二层交换机 工作在TCP/IP对等模型的第二层即数据链路层的交换机

<img src="https://gitee.com/lynbz1018/image/raw/master/img/20220920233801.png" alt="image-20220920233800173" style="zoom:67%;" />

* 交换机接收到数据帧后，会对比该帧的目的地址和mac地址表上的mac地址
* 如果有对应的就从那个接口发送出去；
* 如果没有找到就会采用泛洪方式向除接受口的所有接口发送该报文；
* 目的主机接收到后会发送一个回复报文 交换机接收到后 继续匹配 且会记录这个源mac和端口号到mac地址表

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220921000557023.png" alt="image-20220921000557023" style="zoom:67%;" />

* 单播帧没有匹配到就泛洪发送（出了接收口）
* 广播帧直接泛洪发送

* 如果目的**mac对应的接口和接受的端口一样就丢弃**



<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220921001124041.png" alt="image-20220921001124041" style="zoom:50%;" />

### 5.4同网段数据通信过程

<img src="https://gitee.com/lynbz1018/image/raw/master/img/20220921001715.png" alt="image-20220921001713870" style="zoom:80%;" />

## 6.VLAN原理与配置

### 6.1VLAN基本概念

* 当交换机的mac地址表为空的时候，就会进行泛洪式转发，如果网络过大主机很多就会有很多垃圾流量
* 可以利用VLAN划分多个广播域

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220921172913594.png" alt="image-20220921172913594" style="zoom:67%;" />

* 通过VLAN 标签区分VLAN

![image-20220921191952966](https://gitee.com/lynbz1018/image/raw/master/img/20220921191954.png)

* VLAN数据帧 由交换机打上
* PC处理的数据都是没有标签的
* 交换机将数据帧发送给主机时，会把VLAN标签去掉

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220921192515143.png" alt="image-20220921192515143" style="zoom:67%;" />



#### VLAN 划分方式

* 基于**接口**的划分
* 主机移动了需要重新划分VLAN

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220921193046649.png" alt="image-20220921193046649" style="zoom: 33%;" />

* 基于**MAC地址**划分
* 主机移动了不需要重新配置VLAN

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220921193306072.png" alt="image-20220921193306072" style="zoom: 33%;" />

#### 交换机端口

在交换机处理的帧都必须有vlan标签1

交换机的三种接口 Access Trunk Hybrid

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220921194058113.png" alt="image-20220921194058113" style="zoom: 33%;" />

* 在发送帧时，**只有vlan和pvid相同时才可以脱掉标签**

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220921194431390.png" alt="image-20220921194431390" style="zoom:33%;" />

* 即使主机1发送的是广播，也是只有主机3能发送

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220921195053179.png" alt="image-20220921195053179" style="zoom:33%;" />

* Hybrid相当于是Access和Trunk的杂交

* Hybrid中，在发送时，vid在untagged中就脱掉标签，在tagged中就不能脱掉

<img src="C:%5CUsers%5Clyn95%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20220921195850522.png" alt="image-20220921195850522" style="zoom:33%;" />



## 7.生成树



以太网交换网络中为了进行链路备份，通常会使用冗余链路，这会再交换网络中产生环路。

Spanning Tree Protocol就是用于解决交换网络中二层环路问题。

运行STP协议的设备通过彼此交互信息发现网络中的环路，并且有选择的对某个接口进行阻塞，最终使环形网络变成树形网络。

























## 8.以太网链路聚合与交换机堆叠、集群









## 9.IP路由基础







## 10.OSPF基础





## 12.ACL原理与配置







## 13.AAA原理与配置









## 14.网络地址转换





## 15.网络服务与应用









## 16.WLAN概念









## 17.广域网技术







## 18.网络管理与运维







## 19.IPv6技术









## 20.SDN与NFV概念







## 21.网络编程与自动化