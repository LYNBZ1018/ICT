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