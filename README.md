# 计算机网络复习题

## Ch1 网络概论

- 计算机网络的简单<mark>定义</mark>是**一些相互连接的、自治的计算机的集合**。

- 计算机网络是**计算机与通信技术结合的产物**。

- 从网络的作用范围进行<mark>分类</mark>，计算机网络可以分为：**LAN（局域网）、WAN（广域网）和MAN（城域网）等**。

- 计算机网络由**负责信息传递的通信子网**和**负责信息处理的资源子网**<mark>组成</mark>。<mark>通信子网</mark>包括**物理层、数据链路层和网络层**。

- 计算机网络通信的一个显著<mark>特点</mark>是**间歇性、突发性**。

- 把网络分按数据交换方式进行<mark>分类</mark>可分为：**电路交换网、报文交换网、分组交换网**。<u>电路交换方法在实时性方面优于其它交换方式。</u>

- <mark>分组交换</mark>采用存储转发基本思想，即先把收到的分组存储起来、处理后再转发出去。

#### 电路交换与分组交换工作原理

> 1.分组交换
> （1）通过通信链路和分组交换机（路由器或链路层交换机）
> （2）存储转发传输和非存储转发传输。前者需要被整个分组存储下来再转发。
> （3）排队时延和分组丢失。
> （4）转发表和路由选择协议。
> 
> 2.电路交换
> 主要特点：预留端系统间通信所需要的资源（缓存，链路传输速率）
> 电路交换链路中的电路是通过频分复用（FDM）和时分复用（TDM）实现的。
> 
> 3.分组交换和电路交换的对比
> （1）分组交换不适合实时服务（电话和视频会议）。因为排队时延的变动和不可预测导致端到端时延是可变和不可预测的。
> （2）提供了比电路交换更好的带宽共享，比电路交换更简单，有效，实现成本更低。

- **网络中各个节点相互连接的形式**，叫做网络的<mark>拓扑结构</mark>。常见的拓扑结构有**层次(树)型、总线型、环型、星型和网型**。

- 随着电信和信息技术的发展，国际上出现了所谓<mark>“三网合一”</mark>的趋势，三网指：**电信网、有线电视网络、计算机网络**。

- 在网络边缘的端系统中运行的程序之间的<mark>通信方式</mark>通常可划分为两大类： **C/S模式 和 P2P模式**。

- <mark>客户</mark>是服务请求方，<mark>服务器</mark>是服务提供方。

- <mark>时延</mark>：是指数据（一个报文或分组，甚至比特）从网络（或链路）的一端传送到另一端所需的时间。也可称为延迟或迟延。

#### 网络体系结构中服务与协议的关系

> 在计算机网络体系结构中，对等实体之间的规则叫<mark>协议</mark>，而上下层通过（层间）<mark>接口</mark>（使用服务原语）传递数据。
> 
> <mark>网络协议</mark>是为网络中的数据交换而建立的规则、标准或约定。由**语法、语义、同步**（时序）三个要素<mark>构成</mark>。
> 
> 在计算机网络的分层体系结构中，**n层是n-1层的用户，又是n+1的服务提供者**。

- 计算机网络体系结构有OSI、TCP/IP等。

#### 写出OSI及TCP/IP的体系结构。要求写出共几层，每层的名称及基本功能。

> <mark>OSI</mark> 物理层 数据链路层 网络层 传输层 会话层 表示层 应用层
> 
> 应用层：和用户产生网络流量的程序
> 
> 表示层：1数据格式变换 2数据加密解密 3数据压缩及恢复
> 
> 会话层：1建立管理终止会话 2使用校验点使通信失效时从校验点/同步点恢复通信     实现数据同步
> 
> 传输层：1可靠传输 2差错控制 3流量控制 4复用分用
> 
> 网络层：1路由选择 2流量控制 3差错控制 4拥塞控制
> 
> 数据链路层：1成帧 2差错控制 3流量控制 4访问控制
> 
> 物理层：1定义接口特性 2定义传输模式 3定义传输速率 4比特同步 5比特编码
> 
> <mark>TCP/IP</mark> 网络接口层 网际层 传输层 应用层
> 
> <mark>五层模型</mark> 物理层 数据链路层 网络层 传输层 应用层

#### TCP/IP每层的典型协议有哪些

> 网络接口层 ARP RARP
> 
> 网际层 IP ICMP IGMP
> 
> 传输层 TCP UDP
> 
> 应用层 HTTP FTP DNS

#### 比较OSI、TCP/IP的优缺点，为什么TCP/IP成为了事实上的标准

> 1) TCP/IP一开始就考虑到多种异构网的互联问题，并将网际协议IP作为TCP/IP的重要组成部门。但ISO最初只考虑到使用一种标准的公用数据网将各种不同的系统互联在一起。  
> 2) TCP/IP一开始就对面向连接各无连接并重，而OSI在开始时只强调面向连接服务。  
> 3) TCP/IP有较好的网络管理功能，而OSI到后来才开始这个问题，在这方面两者有所不同。
> 4) 总之，OSI模型看上去好，但不宜实现，TCP/IP看上去有许多缺点，但应用还是比较成功。

- <mark>OSI参考模型的中文含义</mark>是**开放系统互联参考模型**。

- <mark>表示层</mark>主要用于**处理两个通信系统间信息交换的表示方式**。它包括**数据格式变换、数据加密与解密、数据压缩与恢复**等<mark>功能</mark>。

- OSI的<mark>会话层</mark>处于运输层提供的服务之上，为表示层提供服务，<mark>会话层的主要功能</mark>是**会话管理**。

- <mark>运输层</mark>主要解决进程间端到端的传输

- <mark>物理层</mark>要解决信号（码元）同步的问题。

- 在OSI参考模型中，上层欲使用下层所提供的服务就必须与下层交换一些命令，这些命令在OSI中称为<mark>服务原语</mark>。

- 国际性组织**ISO对Internet进行全面管理**，它下面的技术组织**IAB负责管理有关协议的开发**。所有Internet标准都是以<mark>RFC</mark> `Request For Comments` 的形式在网上发表,它的意思是请求评论。

## Ch2 物理层

- <mark>物理层的主要功能</mark>是**规定了接口的机械特性、电气特性、功能特性和过（规）程特性**。

- 机械特性是关于描述接线器的形状和尺寸的。

- 过（规）程特性，指明不同功能的各种事件的出现顺序；

- 电气特性，指明在接口电缆的各条线上出现的电压的范围等等。

- 异步通信（异步传输）是指以字符为单位进行传输，接收方只要按字符同步即可。

- 当依时间顺序一个码元接着一个码元在信道中传输时，称为<mark>串行传输方式</mark>。

- 从<mark>通信的双方信息交互的方式</mark>来看，通信主要有这样三种方式，即**单工、半双工和双工**

#### 理解单工/半双工/全双工的含义。

> 一、单工
> 
> 1、数据只在一个方向上传输，不能实现双方通信。
> 
> 2、栗子：电视、广播。
> 
> 二、半双工
> 
> 1、允许数据在两个方向上传输，但是同一时间数据只能在一个方向上传输，其实际上是切换的单工。
> 
> 2、栗子：对讲机。
> 
> 三、全双工
> 
> 1、允许数据在两个方向上同时传输。
> 
> 2、栗子：手机通话。

#### 区分比特、比特率，码元率（波特率）。

> 比特率(bit rate)又称传信率、信息传输速率(简称信息速率，information rate)。其定义是：通信线路(或系统)单位时间(每秒)内传输的信息量，即每秒能传输的二进制位数，通常用Rb表示，其单位是比特/秒(bit/s或b/s，英文缩略语为bps)。
> 
> 波特率(Baud rate)又称传码率、码元传输速率(简称码元速率)、信号传输速率(简称信号速率，signaling rate)或调制速率。其定义是：通信线路(或系统)单位时间(每秒)内传输的码元(脉冲)个数；或者表示信号调制过程中，单位时间内调制信号波形的变换次数，通常用RB表示，单位是波特（Bd或Baud）。
> 
> <mark>波特率与比特率的关系为：比特率=波特率X单个调制状态对应的二进制位数</mark>。

#### 几种信道复用方式：FDM，TDM,WDM,CDMA等。

> **频分复用 FDM**
> 
> 频分复用是把线路或空间的频带资源分成多个频段（带）,将其分别分配给多个用户，每个用户终端的数据通过分配给它的子通路（频段）传输
> 
> **时分复用TDM**
> 
> 时分多路复用是将传输信号的时间进行分割，使不同的信号在不同时间内传送  
> 即将整个传输时间分为许多时间间隔（称为时隙、时间片等，slot time）  
> 每个时间片被一路信号占用。  
> 线路上的每一时刻只有一路信号存在。
> 
> **波分复用 WDM**  
> 波分复用WDM (Wavelength Division Multiplexing)就是光的频分复用。  
> 整个波长频带被划分为若干个波长范围，每个用户占用一个波长范围来进行传输。
> 
> **码分复用 CDM**
> 常用的名词是 码分多址 CDMA (Code Division Multiple Access)。
> 各用户使用经过特殊挑选的不同码型，因此彼此不会造成干扰。
> 这种系统发送的信号有很强的抗干扰能力，其频谱类似于白噪声，不易被敌人发现。
> 每一个比特时间划分为 m 个短的间隔，称为码片(chip)。

#### 什么是数据、信号；模拟信号、数字信号。

- <mark>PCM</mark>：数字传输中的一次复用群有两个标准。我国采用的叫E1，它的数据传输率是2.048Mbps，它共有32个信道，其中有两个信道用于控制。T1数率是1.544Mbps。

- <mark>带宽</mark>本身是指信道能传送信号的<u><span><font face="宋体">频率范围</font></span></u>，也就是可以传送信号的高频与低频之差。在计算机网络中，带宽常用来表示网络的通信线路所能传送数据的能力。

- 常用的<mark>有线传输介质</mark>主要有**同轴电缆、双绞线和光缆**等。

- <mark>光纤</mark>优点:**通信容量大，传输损耗小，抗干扰好，保密性好，体积小。但施工时难于将两根光纤精确连接。**

#### 单模光纤和多模光纤区别。

> - **List item单模光纤传输距离远远大于多模光纤**
> - **单模光纤只可以传送一种单一光波**
> - **多模光纤可以传送多种光波**
> - **单模比多模要贵,要好**
> - **如果距离短，首选多模**
> - **如果距离大于5英里，单模光纤最佳**
> - **传输大带宽数据信号，那么单模将是最佳选择**

- 关于<mark>卫星通信</mark>的特点是：**卫星的通信频带宽，通信容量大；卫星的通信距离远，且通信费用与通信距离无关；适合广播通信；但卫星的通信时延较大，保密性较差。**

- <u>用同轴电缆连接LAN经常采用总线拓扑结构，而采用双绞线连接LAN时经常采用星型拓扑结构。</u>

- <mark>FTTx</mark> 是一种实现宽带居民接入网的方案，代表多种宽带光纤接入方式。**光纤到户 FTTH，光纤到大楼 FTTB，光纤到路边 FTTC**。

## Ch3 DL层与LAN

- 数据链路层的<mark>任务</mark>是**将有噪声线路变成无传输差错的通信线路，为达到此目的，数据被分装成帧；为防止发送过快，一般提供流量控制功能**。

- <mark>数据链路的管理</mark>包括**数据链路的建立、维持和链路的释放**。

- 在数据链路层中，<mark>帧是用于描述PDU的单位</mark>。

数据链路

- <mark>透明传输</mark>：**指上层不需要考虑下层的实现机理，无论什么SDU均可传输**。

#### 零比特填充的概念

> 零比特填充法又称零比特插入法。在HDLC的帧结构中，若在两个标志字段之间的比特串中，碰巧出现了和标志字段F（01111110）一样的比特组合，那么就会误认为是帧的边界。为了避免出现这种情况，HDLC采用零比特填充法使一帧中两个F字段之间不会出现6个连续1。

- 当<mark>信息字段中出现和标志字段一样的比特组合时，必须采用一些特定的方法</mark>，**HDLC采用零比特填充法；PPP协议在同步传输时，使用零比特填充法，在异步传输时，使用字节填充法**。

- <u>对于<mark>点对点的链路</mark>，目前使用得最广泛的数据链路层协议是</u>`PPP`。

- <mark>PPP</mark>是**面向字节的点到点传输协议**，所以其**所有帧的长度都必须是以字节为单位的**。

- PPP协议能**协商网络层参数**。

- <mark>HDLC</mark>通常被称为是**面向比特的高级链路控制规程**，而<mark>PPP</mark>主要是**面向字符的**。

- <mark>HDLC有三种不同类型的帧</mark>，分别为**信息帧、监督帧和无编号帧**。

- <mark>CRC</mark>是**一种在计算机网络的差错控制中经常使用的方法，在发送端采用软件编码时，一般使用模二除以生成多项式的系数，得到的余数就是CRC检错编码的结果**。

- <u>在采用CRC差错控制的接收端，当把收到的比特串用模二除以生成多项式时，若除不尽时，则判断传输有错误</u>。

#### <font color='red'>掌握CRC计算。CRC冗余校验的方法，生成多项式。</font>

- IEEE802委员会将局域网的<mark>数据链路层拆分为两个子层</mark>。**其中，与传输媒体有关的内容放在MAC子层，与传输媒体无关的放在LLC子层**。

- <mark>局域网的体系结构</mark>包括**物理层、LLC、MAC**。

- <mark>构建局域网的要素</mark>包括：**速率，时延，拓扑，网间连接设备，价格等**。

- <mark>LAN常用的拓扑结构</mark>有**总线, 环型, 星型**等。

- <u><mark>网卡的功能</mark>覆盖了体系结构的物理层和MAC子层等的功能</u>。

- 目前，<mark>局域网的传输介质</mark>（媒体）主要是**双绞线、同轴电缆和光纤**等。

- <mark>WIFI</mark>：**无线局域网。IEEE制定的标准为IEEE802.11。它使用星型拓扑。拓扑结构中的AP全称是接入点。**

- 以太网的<mark>媒体访问控制方法（即以太网解决信道冲突的方法）</mark>是**CSMA/CD**。

- <mark>CSMA/CD的算法可以简单的概括</mark>为：**载波监听、冲突检测、冲突后用截断二进制指数退避算法**。

- 对于基带CSMA/CD而言，为了确保发送站点在传输时能检测到可能存在的冲突，数据帧的传输时延至少要等于信号传播时延的2倍。

- <mark>IEEE</mark>是**电子电气工程师协会的缩写**，**该组织制定的IEEE802.3协议是目前有线局域网主要使用协议**。

#### 以太网中，有效的MAC帧长度的规定。

![ce7ea5ce279a193cb5ec1575fab93037.png](https://img-blog.csdnimg.cn/img_convert/ce7ea5ce279a193cb5ec1575fab93037.png)

- 随着技术的进步，<u>以太网的带宽从10Mb/s到10Gb/s。Ehternet指10Mb/s, Fast Ethernet 为100Mb/s, Giga Ethernet 为1000Mb/s.</u>

- <u>对于以太网10BASE-T标准，10M bps， BASE表示基带传输，T代表双绞线</u>。

#### MAC地址（另一个名字是物理地址）的格式规定。

> 格式为6个字节的二进制代码（以6组16进制数表示），格式为XX-XX-XX-XX-XX-XX

- <mark>中继器</mark>负责**在物理层间实现透明的二进制比特复制，以补偿信号衰减**。

- <mark>交换机/网桥工作在数据链路层</mark>。

- <mark>使用网桥的好处</mark>：**过滤通讯量，增大吞吐量；扩大了物理范围；提高了可靠性；可互联不同物理层、不同MAC子层和不同速率的以太网**。

#### 透明网桥的工作原理是什么？

> 透明网桥以混杂方式工作。接收连接到该网桥的局域网上传递的所有帧。每个网桥维护一个基于MAC 地址的过滤数据库。数据库中列出了每个可能的目的地（目前的MAC 地址），以及它属于哪一条输出线路（一个端口号，即表示转发给哪个 LAN），同时每个表项还有一个超时。网桥根据这个数据库把接收到的帧向相应的局域网中转发。

#### 交换机/路由器的广播域、冲突域；

> 冲突域（collision domain) 在以太网中，如果某个CSMA/CD网络上的两台计算机在同时通信时会发生冲突，那么这个CSMA/CD网络就是一个冲突域。如果以太网中的各个网段以中继器连接，因为不能避免冲突，所以它们仍然是一个冲突域。
> 
>  使用交换机可有效避免冲突。而集线器则不行！因为交换机可以利用物理地址进行选路，它的每一个端口为一个冲突域。而集线器不具有选路功能，只是将接收到的数据以广播的形式发出，极其容易产生广播风暴。它的所有端口为一个冲突域。
> 
>  广播域(Broadcast Domain)是指网段上所有设备的集合。这些设备收听送往那个网段的所有广播。 冲突域：在同一个冲突域中的每一个节点都能收到所有被发送的帧 广播域：网络中能接收任一设备发出的广播帧的所有设备的集合 冲突域是基于第一层（物理层） 广播域是基于第二层（链路层） 广播域就是说如果站点发出一个广播信号后能接收到这个信号的范围。通常来说一个局域网就是一个广播域。 广播域内所有的设备都必须监听所有的广播包，如果广播域太大了，用户的带宽就小了，并且需要处理更多的广播，网络响应时间将会长到让人无法容忍的地步。 冲突域：一个站点向另一个站点发出信号。除目的站点外，有多少站点能收到这个信号。这些站点就构成一个冲突域。 HUB （集线器）所有端口都在同一个广播域，冲突域内。所以HUB不能分割冲突域和广播域。
> 
> 总结：
> 
> 集线器：纯硬件、用于连接网络终端、不能打破冲突域和广播域。
> 
> 交换机：拥有软件系统、用于连接网络终端、能够打破冲突域，但是不能分割广播域。
> 
> 路由器：拥有软件系统、用于连接网络、可以打破冲突域也可以分割广播域，是连接大型网络的比备设备

#### VLAN。

> VLAN（Virtual Local Area Network）的中文名为"虚拟局域网"。

#### 简述IEEE802.3标准。说明其对应网络体系结构中的哪几层？典型速率有哪些？它如何解决信道争用？

> IEEE802.3 描述物理层和数据链路层的MAC子层的实现方法，在多种物理媒体上以多种速率采用CSMA/CD访问方式，对于快速以太网该标准说明的实现方法有所扩展。

#### <font color='red'>在采用半双工方式的IEEE802.3中，当某站检测到媒体空闲后开始发送MAC帧，为什么还需要边发送边检测是否有冲突？最短帧长是如何确定的?</font>

#### 写出CSMA/CD的全称、作用，并说明其工作机制。

> CSMA/CD即载波侦听多路访问/冲突检测，它的工作原理是: 发送数据前 先侦听信道是否空闲 ,若空闲，则立即发送数据。若信bai道忙碌，则等待一段时间至信道中的信息传输结束后再发送数据；
> 
> 若在上一段信息发送结束后，同时有两个或两个以上的节点都提出发送请求，则判定为冲突。若侦听到冲突,则立即停止发送数据，等待一段随机时间,再重新尝试。其原理简单总结为：先听后发，边发边听，冲突停发，随机延迟后重发。

## Ch4 网络层

- **路由选择**是网络层的<mark>主要功能</mark>。<u>网络层向运输层提供服务</u>，主要<mark>任务</mark>是**为从源点到目的点的信息传送作路由选择**。网络层的<mark>传输单元</mark>是**分组**。

- 网络层<mark>提供两种服务</mark>，即**面向连接的虚电路服务和无连接的数据报服务**。

#### <font color='red'>数据报的基本工作原理是什么？</font>

#### 数据报与虚电路服务的对比。对比的方面(可靠通信由谁来保证（网络/用户主机？）、通信前是否要建立连接、分组是否按顺序到达目的地、数据通信期间每个分组怎样表示目的站点、<font color='red'>典型协议</font>）

|                        | 虚电路服务                   | 数据报服务                     |
| ---------------------- | ----------------------- | ------------------------- |
| 思路                     | 可靠通信应当由网络来保证            | 可靠通讯应当由用户主机来保证            |
| <mark>连接的建立</mark>     | 必须有                     | 不需要                       |
| <mark>终地址</mark>       | 仅在连接建立阶段使用，每个分组使用短的虚电路号 | 每个分组都有终点的完整地址             |
| 分组的转发                  | 属于同一条虚电路的分组均按照同一路由进行转发  | 每个分组独立选择路由进行转发            |
| 当结点出故障时                | 所有通过出故障的结点的虚电路均不能工作     | 出故障的结点可能会丢失分组，一些路由可能会发生变化 |
| <mark>分组的顺序</mark>     | 总是按发送顺序到达终点             | 到达终点时不一定按发送顺序             |
| <mark>差错处理和流量控制</mark> | 由网络负责，也可以由用户主机负责        | 由用户主机负责                   |

- <mark>网络层的互联设备</mark>是**路由器**。**使用路由器设备能够将多个ip子网络互连。路由器隔绝了广播**。

- <mark>VPN</mark>：**虚拟专用网（Virtual Private Network）利用共用的英特网作为本机构各专用网之间的通讯载体**。

#### <font color='red'>掌握IP 地址及其表示方法</font>

- <mark>IP地址长度在IPv4</mark>中为`32比特`。

- <mark>IP地址由两部分组成</mark>，**前面一个字段是网络号 net-id（网络标识），它标志主机（或路由器）所连接到的网络，而另一个字段则是主机号 host-id（主机标识），它标志该主机（或路由器）**。

#### <font color='red'>掌握分类的 IP 地址：A、B、C、D等。</font>

#### 掌握子网的划分和构成超网。要求能根据ip地址及其子网掩码计算net-id、广播地址、网络中可容纳多少计算机。

- 在Internet中，<mark>按IP地址进行主机寻址</mark>。

#### 掌握私有地址。

> 私有IP地址的范围有：   
> A 10.0.0.0-10.255.255.255   
> B 172.16.0.0—172.31.255.255   
> C 192.168.0.0-192.168.255.255   
> 这些的IP地址都是可以使用在局域网中的

#### NAT

> NAT（Network Address Translation），是指网络地址转换

- <mark>下一代的IPv6的地址</mark>是`（128）`位的，**能充分保证地址的分配**。

#### 掌握ip协议。掌握首部各字段的意义作用。

![](https://images2015.cnblogs.com/blog/931732/201608/931732-20160804011001043-230234659.jpg)

> 一、版本 
> 
>      占4位，指IP协议的版本。 
> 
> 二、报头长度 
> 
>      占4位，该字段的单位是32位字（1个32位字长是4字节），所以当IP报头长度为1111时，报头长度就达到最大值60字节。当IP分组的首部长度不是4字节的整数倍是，就须要对填充域加以填充。最经常使用的报头长度为20位(报头长度值为0101)，这时不使用任何选项。 
> 
> 三、区分服务（服务类型） 
> 
>      占8位，在通常状况下都不使用这个字段。 
> 
> 四、总长度 
> 
>      指报头和数据之和的长度，单位是字节。总长度字段为16位，故IP数据报的最大长度为65535。 
> 
>      每一种数据链路层都有其本身的帧格式，其中包括帧格式中的数据字段的最大长度，这称为最大传送单元MTU。当IP数据报封装成链路层的帧时，此数据报的总长度不能超过对应MTU的值。若数据报长度超过对于MTU的值，就将数据报进行分片处理，此时数据报首部中的“总长度“字段是指分片后的每个分片的报头长度和数据长度之和。 
> 
> 五、标识 
> 
>      占16位。IP软件在存储器中维持一个计数器，每产生一个数据报，计数器就加1，并赋给标识字段。当数据报进行分片处理后，每一个分片的标识值都与原数据报的标识值相同，则在接收端具备相同标识值的分片就能最终正确的重装成为原来的数据报。 
> 
> 六、标志 
> 
>      占3位，但目前只有两位有意义。 
> 
> -      最低位记为MF。MF=1即表示后面”还有分片“的数据包。MF=0表示这已经是若干数据包片中的最后一个。
> -      中间位记为DF，意思是”不能分片“。只有当DF=0时才容许分片。
> 
> 七、片偏移 
> 
>      占13位。表示每一个数据报的分片在原数据报中的相对位置。片偏移以8个字节为偏移单位，即每一个分片的长度必定是8字节的整数倍。 
> 
> 八、生存时间 
> 
>      占8位。表示数据报在网络中的寿命。最初以秒为TTL值为单位，如今以跳数为单位，则目前的最大数据为255. 
> 
> 九、协议 
> 
>      占8位，指出此数据报携带的数据是使用何种协议，以便使目的主机的IP层知道应将数据部分上交给那个处理过程。 
> 
>      TCP对应协议字段值6；UDP对应协议字段值17 
> 
> 十、首部校验和 
> 
>      占16位，该字段只校验数据报的报头，但不包括数据部分。 
> 
> 十一、源地址 
> 
>      占32位 
> 
> 十二、目的地址 
> 
>      占32位

#### 数据报片的计算。

> 当一个8192B的UDP数据报通过以太网传送时，导致分片，问需要分成几个数据报片？每个数据报片的长度和偏移是多少？
> 
> 1）首先，计算数据包总长度：
> 数据包总长度=IP头（20字节）+UDP头（8字节）+UDP数据（8192字节）=8220（字节）
> 
> 2）由于你没有提到分片大小，以一般的以太网MTU值（Maximum Transmission Unit，最大传输单元）1500字节计算。
> 因为要考虑20个字节的IP报文头，所以每个数据分片的数据段长度最大为1480字节。
> 
> 3）分片结果，分为6片，具体长度和偏移量（IP报偏移量的单位是8字节，要除以8）如下：
> 第一片用户数据报的数据字段长度1480，偏移量0
> 第二片用户数据报的数据字段长度1480，偏移量1480/8
> 第三片用户数据报的数据字段长度1480，偏移量2960/8
> 第四片用户数据报的数据字段长度1480，偏移量4440/8
> 第五片用户数据报的数据字段长度1480，偏移量5920/8
> 第六片用户数据报的数据字段长度800，偏移量7400/8
> 
> 4)如果分片大小有变化，即MTU值不是1500，请按照设定的MTU值计算即可。

#### 在支持子网划分的因特网中，路由器如何转发IP数据报？

> 使用子网划分后，路由表必须包含以下三项内容：目的网络地址，子网掩码和下一跳地址。路由器转发分组的算法（流程）如下：  
> 
> 1）.从收到的数据报首部提取目的IP地址D  
> 
> 2）.先判断是否为直接交付。对路由器直接相连的网络进行逐个检查：用各网络的子网掩码和D逐位相与，看结果是否和相对应的网络地址匹配。若匹配，则把分组进行直接交付，转发任务结束。否则就是间接交付，执行（3）。  
> 
> 3）.若路由表中有目的地址为D的特定主机路由，则把数据报传送给路由表中所指明的下一跳路由：否则执行（4）。  
> 
> 4）.对路由表的每一行，用其中的子网掩码和D逐位相与，其结果为N。若N与该行的目的网络地址匹配，则把数据报传送给该行指明的下一跳路由器；否则执行（5）。  
> 
> 5）.若路由表中有一个默认路由，则把数据报传送给路由表中所指明的默认路由器；否则执行（6）。  
> 
> 6）.报告转发分组出错。

- <mark>静态路由选择策略</mark>——**即非自适应路由选择，其特点是简单和开销较小，但不能及时适应网络状态的变化**。

- <mark>动态路由选择策略</mark>——**即自适应路由选择，其特点是能较好地适应网络状态的变化，但实现起来较为复杂，开销也比较大**。

- <mark>因特网的路由选择技术</mark>是**分布式的、动态的**。

- <mark>路由协议</mark>主要有：**基于距离向量的路由选择协议RIP、基于链路状态的路由协议 OSPF等**

#### 掌握RIP协议的工作原理。

> RIP协议是一种典型的距离矢量协议，它使用的也是距离矢量算法，该算法可以用一句话来概括：进行路由更新时传递路由表。

#### OSPF协议的工作原理，及OSPF协议相对的优点。

> **OSPF(Open Shortest Path First开放式最短路径优先**)是一个内部网关协议(Interior Gateway Protocol,简称IGP)，用于在单一自治系统(autonomous system,AS)内决策路由。
> 
> 链路是路由器接口的另一种说法，因此OSPF也称为接口状态路由协议。OSPF通过路由器之间通告网络接口的状态来建立链路状态数据库，生成最短路径树，每个OSPF路由器使用这些最短路径构造路由表。
> 
> 优点：无环路，收敛快，支持大中型网络，所有厂家都支持

- Internet网际互联层中使用的<mark>四个重要协议</mark>是**IP、ICMP、ARP、RARP**。

- **无IP地址的站点可以通过**`RARP协议`**获得自己的IP地址**。

- <u>用TCP／IP协议的网络在传输信息时，如果出了错误需要报告</u>，<mark>采用的协议</mark>是`ICMP`。ICMP**允许主机或路由器报告（差错情况）和提供有关异常情况的报告**。<mark>ICMP报文是通过IP报文传输的</mark>。

- 我们常用PING来测试两个主机间的连通性。

#### PING使用了哪个协议，描述其工作过程。

> CMP协议。ICMP 报文的种类有两种，即 ICMP 差错报告报文和 ICMP 询问报文。PING 使用了 ICMP 回送请求与回送回答报文。由主机或路由器向一个特定的目的主机发出的询问。收到此报文的主机必须给源主机或路由器发送ICMP回送回答报文。

## Ch5 运输层

- <mark>拥塞</mark>：<u>若对网络中某一资源的需求超过了该资源所能提供的可用部分，网络的性能就要变坏，这种情况就叫做拥塞（congestion）。到达通信子网中某一部分的分组数量过多，使得该部分乃至整个网络性能下降的现象，称为拥塞现象。严重时甚至导致网络通信业务陷入停顿，即出现死锁现象。</u>

#### 流量控制的概念、基本思想。

> 流量控制（Network traffic control）是利用[软件](https://baike.baidu.com/item/%E8%BD%AF%E4%BB%B6/12053)或[硬件](https://baike.baidu.com/item/%E7%A1%AC%E4%BB%B6/479446)方式来实现对网络数据流量进行控制的一种措施。
> 
> 控制发送端发送的数据流量

- 在计算机通信中，经常采用**自动请求重发方式**（ARQ）进行<mark>差错控制</mark>。<mark>ARQ方式</mark>有：**停止等待、后退N帧、选择重发等方式**。

- <mark>ARQ协议中的窗口</mark>是**一段缓存空间**，**根据窗口的大小，可连续发送多个分组而不需要对方的确认，这样信道利用率就提高了**。<mark>窗口大小的选择</mark>是由**发送方的发送能力、信道传输能力、接收方的接收能力等共同决定**。

#### 序号、发送窗口、接收窗口之间的关系。

> 发送窗口小于等于接受窗口
> 
> *对于选择重传协议,发送窗口大小Wt*、*接收窗口大小Wr和序号比特数n之间的关系是什么*?为什么? 参考答案:Wt、Wr和n必须满足关系式:Wt+Wr<=2n。

- 运输层协议端口： 端口号用来区分上层应用进程。一些常用的应用层程序固定使用熟知端口，如： DNS 53  ;  HTTP: 80；TELNET:23；FTP:21/20；TFTP：69等。

#### 套接字（Socket）

> 所谓套接字(Socket)，就是对网络中不同主机上的应用进程之间进行双向通信的端点的抽象。一个套接字就是网络上进程通信的一端，提供了应用层进程利用网络协议交换数据的机制。从所处的地位来讲，套接字上联应用进程，下联网络协议栈，是应用程序通过网络协议进行通信的接口，是应用程序与网络协议栈进行交互的接口

- <mark>UDP协议</mark>：**UDP协议是无连接的**、掌握UDP首部含义。

- <mark>TCP的主要特点</mark>：**是面向连接的运输层协议；每个TCP连接只能有两个端点；它提供可靠的交付；全双工；面向字节流**。

- <mark>TCP连接的建立</mark>采用**三次握手法**，<mark>释放</mark>时**采用“文雅”释放**。

#### 描述TCP协议的工作原理。

> 1.在源主机上，应用层将一串应用数据流传送给传输层。
> 2.传输层将应用层的数据流截成分组，并加上TCP报头形成TCP段，送交网络层。
> 3.在网络层给TCP段加上包括源、目的主机IP地址的IP报头，生成一个IP数据包，并将IP数据包送交链路
> 层。
> 4.链路层在其MAC帧的数据部分装上IP数据包，再加上源、目的主机的MAC地址和帧头，并根据其目的MAC
> 地址，将MAC帧发往目的主机或IP路由器。
> 5.在目的主机，链路层将MAC帧的帧头去掉，并将IP数据包送交网络层。
> 6.网络层检查IP报头，如果报头中校验和与计算结果不一致，则丢弃该IP数据包；若校验和与计算结果
> 一致，则去掉IP报头，将TCP段送交传输层。
> 7.传输层检查顺序号，判断是否是正确的TCP分组，然后检查TCP报头数据。若正确，则向源主机发确认
> 信息；若不正确或丢包，则向源主机要求重发信息。
> 8.在目的主机，传输层去掉TCP报头，将排好顺序的分组组成应用数据流送给应用程序。这样目的主机接
> 收到的来自源主机的字节流，就像是直接接收来自源主机的字节流一样。

#### 掌握TCP报文段首部各字段的含义、作用。（数据传输阶段，序列号、确认号的含义；控制比特URG、ACK、PSH、SYN、RST、FIN等的含义；数据偏移、校验和的含义； ）

> TCP报文段首部的前20个字节是固定的，后面有4N字节是根据需要而增加的选项（N是整数）。因此TCP首部的最小长度是20字节。
> 首部固定部分各字段的意义如下：
> 源端口和目的端口：各占2个字节，分别写入源端口号和目的端口号。
> 序号：占4个字节。序号使用mod运算。TCP是面向字节流的，在一个TCP连接中传送的字节流中的每一个字节都按顺序编号。故该字段也叫做“报文段序号”。
> 确认序号：占4个字节，是期望收到对方下一个报文段的第一个数据字节的序号。若确认序号=N,则表明：到序号N-1为止的所有数据都已正确收到。
> 数据偏移：占4位，表示TCP报文段的首部长度。注意，“数据偏移”的单位是32位字（即以4字节长的字为计算单位）。故TCP首部的最大长度为60字节。
> 保留：占6位，保留为今后使用，目前置为0；
> 紧急URG：当URG=1，表明紧急指针字段有效。这时发送方TCP就把紧急数据插入到本报文段数据的最前面，而在紧急数据后面的数据仍是普通数据。
> 确认ACK：当ACK=1时，确认字段才有效。当ACK=0时，确认号无效。TCP规定，在连接建立后所有传送的报文段都必须把ACK置1。
> 推送PSH：接收方TCP收到PSH=1的报文段，就尽快地交付给接收应用进程，而不再等到整个缓存都填满了后再向上交付。
> 复位RST：当RST=1时，表明TCP连接中出现严重差错，必须释放连接，然后再重新建立运输连接。
> 同步SYN：在连接建立时用来同步序号。当SYN=1而ACK=0时，表明这是一个连接请求报文段。对方若同意建立连接，则应在响应的报文段中使SYN=1和ACK=1。故SYN置为1，就表示这是一个连接请求和连接接收报文。
> 终止FIN：用来释放连接。当FIN=1时，表明此报文段的发送方的数据已发送完毕，并要求释放运输连接。
> 窗口：占2个字节。窗口值作为接收方让发送方设置其发送窗口的依据。
> 检验和：占2字节。检验和字段检验的范围包括首部和数据这两部分。和UDP数据报一样，在计算检验和时，也要在TCP报文段的前面加上12字节的伪首部。伪首部的格式与UDP用户数据报的伪首部一样，但要将伪首部第四个字段中的17 改为6（协议号），把第5字段中的UDP长度改为TCP长度。
> 紧急指针：占2字节。紧急指针仅在URG=1时才有意义，它指出本报文段中的紧急数据的字节数。

#### 简述TCP协议的流量控制机制。

> tcp是利用滑动窗口机制就可以实施流量控制。原理这就是运用TCP报文段中的窗口大小字段来控制，发送方的发送窗口不可以大于接收方发回的窗口大小。

## Ch6 应用层

#### 应用层介绍的各个协议：缩写对应的中（或英）文名称,及其主要作用：URL、邮局协议、FTP、远程终端协议、SNMP、TFTP

> (1)域名系统(Domain Name System，[DNS](https://baike.baidu.com/item/DNS/427444))：用于实现网络设备名字到IP地址映射的网络服务。
> 
> (2)文件传输协议(File Transfer Protocol，FTP)：用于实现交互式文件传输功能。
> 
> (3)简单邮件传送协议(Simple Mail Transfer Protocol, SMTP)：用于实现电子邮箱传送功能
> 
> (4)超文本传输协议(HyperText Transfer Protocol，[HTTP](https://baike.baidu.com/item/HTTP))：用于实现WWW服务。
> 
> (5)简单网络管理协议(simple Network Management Protocol，SNMP)：用于管理与监视网络设备。
> 
> *TFTP*（Trivial File Transfer Protocol,简单文件传输协议）
> 
> (6)远程终端协议(Telnet)：用于实现远程登录功能。

#### 何为域名系统，域名的命名规则是什么

> 域名系统DNS（Domain Name System）是因特网使用的命名系统，用来把便于人们使用的机器名字转换为IP地址。
> DNS被设计成为一个联机分布式数据库。 
> 
> 命名采用层次树状结构，域可划分为子域，各级间用点隔开，每个标号不超过63个字符，不区分大小写，级别低的在左边，高的在右边。总字符数不能超过255个。域名仅为逻辑概念。域名为分级管理。）

- **从计算机域名到IP地址翻译的过程**称为<mark>域名转换</mark>。

#### 认识常用顶级域名。

> .com-- 用于商业机构。它是最常见的顶级域名。任何人都可以注册.com形式的域名。 .net-- 最初是用于网络组织，例如因特网服务商和维修商。现在任何人都可以注册以.net结尾的域名。 .org-- 是为各种组织包括非盈利组织而定的。现在，任何人都可以注册以.org结尾的域名。 .edu--用于教育机构。 .mil--用于军事部门 .gov--用于政府部门 新顶级域名的形式有： .biz;.info;.name;.pro;.aero; .coop;.museum. .biz----用来替代.com的顶级域，适用于商业公司； (注：biz是business的习惯缩用)； .info---用来替代.com的顶级域，适用于提供信息服务的企业； .name---专用于个人的顶级域； .pro----专用于医生、律师、会计师等专业人员的顶级域; (注：pro是professional的习惯缩用)； .coop---专用于商业合作社的顶级域；（注：coop 是cooperation的习惯缩用）； .aero---专用于航空运输业的顶级域名； .museum---专用于博物馆的顶级域。

#### 电子邮件的基本传输机制（SMTP、POP3、IMAP的功能等）。

> - 发送邮件的协议：SMTP
> - 读取邮件的协议：POP3 和 IMAP
> - MIME支持在邮件中同时传送多种类型的数据。



> **SMTP（Simple Mail Transfer Protocol**），简单邮件传输协议。它是一组用于从源地址到目的地址传输邮件的规范，通过它来控制邮件的中转方式。
> 
> **IMAP（Internet Mail Access Protocol​）**，交互式邮件存取协议，它是跟POP3类似邮件访问标准协议之一。不同的是，开启了IMAP后，您在电子邮件客户端收取的邮件仍然保留在服务器上，同时在客户端上的操作都会反馈到服务器上
> 
> **POP3（Post Office Protocol 3）**，邮局协议的第3个版本，它规定怎样将个人计算机连接到Internet的邮件服务器和下载电子邮件的电子协议。它是因特网电子邮件的第一个离线协议标准，POP3允许用户从服务器上把邮件存储到本地主机（即自己的计算机）上，同时删除保存在邮件服务器上的邮件

#### FTP的全称、作用。

> FTP 是File Transfer Protocol(文件传输协议)的英文简称,而中文简称为“文传协议”。

> 1、连接到FTP服务器并操纵数据和数据的上传下载以及备份，其FTP服务器就是支持FTP协议的服务器；2、可以访问物理远程服务器。

#### 说明电子邮件系统的主要组成构件。

> 用户代理、*邮件*服务器、*邮件*发送协议、*邮件*读取协议。

## Ch7 实验

- 在DTE和DCE中，<mark>DTE（数据终端设备）</mark>指**一般的终端或是计算机**；<mark>DCE（数字通信设备）</mark>，通常指**调制解调器**等。**DCE设备为DTE设备提供时钟，DCE为DTE实现信号的编解码**。

- 双绞线的<mark>RJ45连接器标准</mark>有两个：**EIA/TIA-568A 和EIA/TIA-568B**标准。<u>目前T568B标准接线方法使用较多</u>。

- 在Windows中用于<mark>查看网卡的MAC地址的命令</mark>是`ipconfig /all`。

- 在<mark>华为路由器中查看当前运行的配置的命令</mark> `display current-configuration`

- 在华为路由器中<mark>查看路由表的命令</mark> `display ip routing-table`

- 在华为路由器中<mark>配置静态路由</mark>的命令 `ip route-static`

- 在华为路由器中<mark>查看端口状态</mark>的命令 `display interface brief`

- 掌握在华为路由器中<mark>缺省输入</mark>（不完整关键字输入）:
  
  <u>当输入的字符能够匹配唯一的关键字时，可以不必输入完整的关键字。</u>
  
  <u>例如，当需要输入命令display current-configuration时，可以通过输入d cu、di cu或dis cu来实现，但不能输入d c或dis c等，因为系统内有多条以d c、dis c开头的命令。</u>
