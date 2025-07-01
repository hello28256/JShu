# Linux 课堂笔记

## 就业班的整体安排

4大阶段：

- 大数据分布式入门（离线数仓阶段）、Linux操作系统、Hadoop技术栈、Hive数仓、数据仓库项目和实战
- 大数据运维方向（Linux加强、大数据集群管理、数据库开发、监控报警项目）、数据分析向（Python、Excel、Pandas、BI报表、ETL数据处理）
- 内存计算阶段（Spark计算框架、用户画像项目）
- 实时计算阶段（Apache Kafka、Flume、阿里云Flink+项目）



## 初识Linux

### 计算机的原理

#### 冯诺依曼体系

![image-20220711091035348](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/07/20240407232609.png)

冯诺依曼在1946年的时候，提出来计算机的基础5大组成部分，称之为：冯诺依曼计算机结构体系

> 这个体系到目前依旧在使用，我们现在所用的电脑，都是冯诺依曼体系结构的。



冯诺依曼体系结构包含五大组件（如上图）：

- 输入设备（Input Device）
- 输出设备（Output Device）
- 控制器
- 运算器
- 存储器



经过多年的发展，目前的计算机依旧是冯诺依曼体系，但是部分组件的叫法不太一样：

- CPU（控制器、运算器）：控制并运算计算机的计算指令（说白了就是干活的）

- 内存（存储器）：存储计算机需要运算的数据，以及CPU的运算指令

- 输入设备：指令的输入设备，常见的有：`键盘`、`鼠标`、`手柄`、`摄像头`、`麦克风`。。。。。。

  > 通俗来说：将指令（数据）输入给计算机的，都算作输入设备

- 输出设备：常见的有：`显示器`、`音响`、`打印机`



> 经过这几大部分的组成，一个基础的计算机就出现了：
>
> - 通过键盘、鼠标、麦克风等进行控制指令、数据的输入
> - 通过CPU、内存来完成程序的运行
> - 通过显示器、音响、打印机等将程序运行的结果输出出来



##### 计算机的基础执行流程

基于冯诺依曼体系的计算机结构，基础运行流程如下：

1. 通过输入设备进行输入
2. 通过CPU和内存（控制器、运算器、存储器）进行搭配，完成计算工作
3. 通过输出设备将计算结果进行输出



比如打游戏：

通过键盘鼠标完成操作的输入 -> 通过CPU、内存、显卡、声卡等完成指令操作的计算 -> 通过显示器、音响等给你输出画面。



总结：指令输入 -> 指令计算 -> 结果输出





### 操作系统

一台可以运行的电脑，100%是由如下2部分组成：

- 硬件部分(冯诺依曼体系：键盘鼠标、CPU、内存、显卡、声卡、显示器、音响)，能看到的都算是硬件部分
- 软件部分（操作系统：Windows、MacOS、Linux、安卓、IOS）



硬件部分的功能： 为计算机提供输入功能、计算功能、输出功能

软件部分的功能： 软件就是让硬件好好干活



#### 操作系统的主要功能

==调度、管理硬件，让计算机的硬件可以正常工作。==

> 硬件是肉体、软件（操作系统）是灵魂
>
> 没有操作系统，硬件就是一堆废铁

#### 操作系统的工作模式

![image-20220711093008338](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/07/20240407232610.png)

如图：

1. 用户（使用者）通过硬件的输入设备，将指令输入到操作系统中
2. 操作系统接收到用户的指定输入，去要求CPU干活、要求内存存数据、要求声卡工作、要求显卡运算
3. 指令运算完成后，又操作系统去控制显示器显示画面、音响输出声音、打印机打印文字......





#### 操作系统的分类

- 桌面操作系统：工作用的，常见的有：

  - Windows（Windows7、Windows10）
  - MacOS（MacOS 14、MacOS15)
  - Linux（Ubuntu、Debian、国产的麒麟）

- `服务器操作系统`：用于企业的应用服务器的，比如WEB服务器、数据库服务器等

  - Windows（Windows Server 2008、Windows Server 2016）
  - `Linux`（Redhat、`CentOS`、Ubuntu Server)

- 嵌入式操作系统：主要用于一些嵌入式的设备的，比如汽车的中控、汽车的空调控制系统、电梯的调度系统、门禁卡系统、食堂刷卡机.....

  嵌入式的功能是非常单一的，只针对单一功能使用

- 移动操作系统：Android安卓、IOS、华为鸿蒙系统



> 当前课程，就是学习的：
>
> - 服务器操作系统（Linux）、CentOS发行版



#### Linux的起源和发展

1. 在上世纪70年代开始，操作系统比较火的是`Unix`操作系统。
2. Unix操作系统虽然比较火，但是有一系列的问题（版权、开放源码等）
3. 在市面上就有许多的公司或个人，基于Unix去进行`二次开发`
4. 在1991年的时候，芬兰的一个大学生：`林纳斯托瓦兹`（Linus Torvalds)，在大学中基于Unix操作系统，二次开发出了一个Linux操作系统，并且向全世界开发（源码公开、免费使用）
5. 一经发布，就受到了许多的开发者的喜爱，由于源代码是公开的，所以很多的开发者就向Linux操作系统去贡献代码
6. 经过到目前的发展，Linux操作系统，是服务器领域：当之无愧的Top1顶级操作系统。

Linux操作系统之父：

![image-20220711100656880](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/07/20240407232610.png)

> Linus Torvalds至今仍在管理整个Linux操作系统的开源项目。



> Linus Torvalds在1991年所开发的，就是Linux的第一版内核（不包含系统级软件）



#### Linux内核

##### 内核

一个操作系统，主要分为2部分：

- 内核（核心功能）

  提供了对硬件的管理、调度能力：

  - 操作CPU干活
  - 操作内存干活
  - 操作输入输出设备进行工作

- 系统级软件

  - 文件管理服务
  - 网络管理服务
  - 内存管理服务



通过Windows系统举例：

```shell
Windows系统也是由：
- Windows系统内核（Windows NT）
- Windows系统级软件

我们目前使用的Windows XP、Windows 7、Windows 10、Windows11，都是基于Windows NT内核

Windows的系统级软件：
- 文件管理器
- 任务管理器
- 音频输出的驱动
- 网络管理器
```





Linux操作系统也一样：

```shell
Linux系统也是由：
- Linux内核
- Linux的系统级软件
2者所组成
```



> 至今，Linux内核依旧是开放源码、免费使用的。



![image-20220711101530504](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/07/20240407232609.png)

如图，Linux内核从1991年开发至今，已经发布到`5.18.10`的版本了（截止到2022年7月11日）

https://www.kernel.org





##### 补充：开放源代码

源码：程序的原始代码

开放源码的意思就是：程序的源代码任何人都可以看到。

Linux内核就是一个开放源代码的程序。



市面上的软件在源码方面主要分为2类：

- 开放源代码：
  - Linux内核、安卓系统的内核
  - 大数据的相关组件（Zookeeper、Hadoop、Spark、Flink等）
- 封闭源代码：（不让你看到它的源码）
  - 微信
  - QQ
  - 淘宝
  - 京东
  - 等等这些软件，你只能用，看不到它的源码的。

> 封闭源代码的软件是非常多的。
>
> 我们大数据体系中用到的各类组件90%都是开放源码的。

> 典型的开放源码的应用：
>
> - 安卓手机（安卓系统的内核就是开放源码的，基于这个，国内的手机厂商可以推出自己的系统：小米系统、Oppo等）





#### Linux的发型版本

![image-20220711102406117](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/07/20240407232610.png)

举例：

```shell
安卓操作系统的内核是开发源代码的。
所以很多手机厂商就基于安卓的内核源码，开发了自己的安卓操作系统：
- 小米手机有MIUI
- Oppo手机有自己的安卓系统
- 等等。。。。
```



同样，Linux的内核是开放源码的，所以`任何人`都可以拿到Linux的内核，进行二次开发，封装出来属于自己的Linux系统版本。

所以，在市面上有非常多的Linux系统版本，这些版本我们都称之为`Linux发行版`



如上图，发行版非常多，比较出名的有：

- Ubuntu、Mint：在个人、桌面（办公）领域用的比较多的Linux系统版本
- RedHat：在企业服务器中用的比较多的Linux系统版本（收费、贼贵）
- `CentOS`：在企业服务器中用的比较多的Linux系统版本（RedHat的简化版，免费）



> 同样，我们课程中要学习的Linux操作系统，就是：CentOS发行版
>
> 这个是在全球以及国内，众多公司的选择。




### 虚拟机

目的：学习Linux操作系统，必须要有一个Linux系统供你使用

解决：

- 给自己电脑装上Linux操作系统（不推荐）
- 在自己的电脑中，通过虚拟机模拟出来一个电脑安装Linux操作系统（`推荐`）



使用虚拟机的目的：在自己电脑中，得到一个可以使用的Linux操作系统，供我们学习用。



#### 什么是虚拟机呢？

虚拟机：在电脑中，通过软件手段，模拟出来的一个虚拟的`电脑`



通过虚拟机软件，来模拟：

- CPU、硬盘、网卡、内存、键盘、鼠标、显示器等设备，构成一个虚拟的电脑硬件

然后在这个虚拟的电脑硬件上，安装操作系统，最终得到一个`虚拟的计算机`

![image-20220711103909547](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711103909.png)

#### 如何得到虚拟机呢

市面上提供在电脑中模拟硬件的软件非常多，常用的有：

- VMware WorkStation（Windows电脑用）
- VMbox（Windows、Linux、MacOS通用）
- VMware Fusion（MacOS用）
- ......

我们课程中，就使用VMware WorkStation这个软件，来在我们的电脑中去模拟一个虚拟的电脑



#### 安装虚拟机软件（VMware WorkStation）

##### 软件的安装包

存放在：`前置资料\vmware\VMware-workstation-full-16.2.1-18811642.rar`

对这个`rar`压缩包进行解压缩，可以得到：

![image-20220711104347986](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711104348.png)

如图2个文件：

- VMware-workstation-full-16.2.1-18811642.exe 就是安装包
- 16序列号.txt 安装的序列号



##### 安装过程

笔记中：略

给同学们提前准备好了文档：

`课程文件夹\附件资料\Linux基础\01_安装VMware虚拟机.doc`



##### 检查VMware是否安装成功（必须检查）

![image-20220711105136906](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711105136.png)

如图，右键网络，打开“网络和Internet”设置



![image-20220711105208557](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711105208.png)

![image-20220711105223936](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711105223.png)

如图，在弹出的`网络连接`的框中，确认有：`VMnet1` 和 `VMnet8` 2个网卡存在

有的话就是安装成功了。



##### 虚拟机是如何上网的

> 虚拟机模拟：CPU、硬盘、内存、显示器、鼠标等是非常稳定的，一般不会有问题
>
> 所以，我们在上面才让同学们检查有没有VMnet1和VMnet8
>
> 因为这两个是用来确保虚拟机可以正常联网的。

联网功能：

- 联网下载软件
- 大数据集群之间互通

都是非常重要的。一定要确保这2个网卡是正常的。



虚拟机上网，是通过：

- 虚拟的交换机（路由器）来去上网。



在VMware中提供3种上网模式：

- NAT模式
- 桥接模式
- 仅主机模式



###### `NAT`模式

表示虚拟机和你的电脑之间是可以互通的，同时虚拟机也可以连接上外网

![image-20220711111902747](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711111902.png)

如图，虚拟机上网，是连接到虚拟网卡`VMnet8`，通过它链接你的物理网卡，借助物理网卡可以上网



###### 桥接模式

表示虚拟机连接到你电脑所在的路由器进行上网

这个模式下，虚拟机和你的电脑同处于一个路由器的内部，同时虚拟机也可以连接外网

![image-20220711112055232](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711112055.png)



###### 仅主机模式

虚拟机无法连接外网，只能和你的电脑进行联通



> 在课程中，我们全程使用NAT模式即可
>
> 使用NAT模式：
>
> - 网络配置简单
> - 虚拟机和你的电脑是互通的
> - 虚拟机也可以上网（打开百度、登陆QQ）

![image-20220711112332768](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711112332.png)





#### 在虚拟机软件（VMware）中，安装Linux操作系统

笔记：略

详细可以参见：`课程文件夹\附录资料\Linux基础\02_安装Centos.doc`



使用的Linux系统的安装包：

安装包在：`课程前置资料\Centos操作系统\CentOS-7-x86_64-DVD-1908.iso`

这个就是CentOS操作系统的安装包。





步骤：

1. 点击新建

   ![image-20220711113624404](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711113624.png)

2. ![image-20220711113644761](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711113644.png)

3. ![image-20220711113718738](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711113718.png)

4. ![image-20220711113758881](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711113758.png)

5. ![image-20220711113855800](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711113855.png)

6. ![image-20220711113920470](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711113920.png)

7. ![image-20220711113938455](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711113938.png)

8. ![image-20220711114031317](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711114031.png)

9. ![image-20220711114057599](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711114057.png)

10. ![image-20220711114120610](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711114120.png)

    如图，开启自动安装流程

    等到10分钟左右，`全程无需操作`，直到安装完成

11. ![image-20220711114153668](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711114153.png)

    看到如图的页面就是安装完成了。





登陆Linux系统

1. ![image-20220711115240943](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711115241.png)

2. ![image-20220711115306484](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711115306.png)

3. ![image-20220711115340313](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711115340.png)

4. ![image-20220711115403335](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711115403.png)

   看到如图就成功进入

5. ![image-20220711115433677](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711115433.png)

6. ![image-20220711115519101](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711115519.png)

   如图，能打开百度即可。




### 远程连接Linux操作系统

#### 关于操作系统的操作方式

不管是Windows、MacOS、Linux，操作系统都提供了2套操作逻辑供我们使用：

1. 基于图形化的窗口来操作，可以用鼠标点点点
2. 基于命令行的模式，通过输入命令，来取控制系统干活



在Windows系统中，使用`图形化窗口`是非常普遍的。

在Linux系统中，使用`命令行的模式`是非常普遍的。

> 这是因为：
>
> 1. Windows的图形化控制逻辑，非常的完善的，很少出错极其稳定。
>
> 2. Linux的图形化控制逻辑是非常的`弱鸡`的，经常出错不够稳定。
>
>    但是反过来，Linux提供了非常完善的`命令行`体系，极其稳定。
>
>    所以企业都是使用Linux的命令行模式去操作Linux系统
>
>    我们学习，也主要学习Linux的各种操作命令



既然我们要使用100%的命令行的模式去操作Linux系统，那么，我们可以使用第三方的软件

去远程连接到Linux系统中去使用命令行。



#### 用什么软件去远程连接到Linux系统呢？

在市面上支持远程连接Linux系统的软件是非常多的：

- SecureCRT
- XShell
- `FinalShell（国产软件）`



#### FinalShell软件的安装

安装包在：`资料\Linux连接软件\finalshell_windows_x64.exe`

1. ![image-20220711145838486](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711145838.png)
2. ![image-20220711145851701](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711145851.png)
3. ![image-20220711145914005](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711145914.png)
4. ![image-20220711145924816](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711145924.png)
5. ![image-20220711150013336](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711150013.png)



#### 通过FinalShell软件连接到Linux操作系统

1. 查看Linux系统的ip地址(方式1)

   ![image-20220711150123299](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711150123.png)

   ![image-20220711150137084](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711150137.png)

   ![image-20220711150204867](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711150204.png)

   ![image-20220711150234588](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711150234.png)

   如图，就看到IP地址了：`192.168.88.130`，每个人的都不一样，各自看各自的。

2. 查看Linux系统的ip地址（方式2：）

   ![image-20220711150339366](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711150339.png)

   ![image-20220711150421314](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711150421.png)

3. ![image-20220711150637578](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711150637.png)

4. ![image-20220711150707740](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711150707.png)

5. ![image-20220711150820569](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711150820.png)

6. ![image-20220711150849229](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711150849.png)

7. `双击`上图的链接

8. ![image-20220711150905439](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711150905.png)

9. ![image-20220711150932810](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711150932.png)



字体不好看，改一下：

1. ![image-20220711151136533](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711151136.png)
2. ![image-20220711151229047](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711151229.png)



#### 体验通过命令行操作Linux操作系统

在FinalShell软件中，直接输入如下内容，并回车：

```shell
mkdir /root/Desktop/test
```

![image-20220711153300213](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711153300.png)

回到虚拟机中，即可看到在桌面上出现了一个叫做`test`的文件夹。



> 证明了，我们通过FinanShell这个第三方软件，`远程连接到Linux`系统后，可以用命令行，对虚拟机进行操作




### Linux虚拟机打快照

#### 拍摄快照

![image-20220714182334169](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/14/20220714182334.png)



#### 恢复

![image-20220714182428062](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/14/20220714182428.png)

![image-20220714182453990](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/14/20220714182454.png)

==即可恢复到拍摄快照的时候的状态==




## Linux基础命令

### Linux操作系统的文件系统



#### Windows系统中

![image-20220711154032603](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711154032.png)

如图，C、D、E、等等硬盘的盘符，是最顶级的目录。

![image-20220711154347904](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711154347.png)

如上图，Windows的结构是以各个盘符为起点，向下嵌套文件夹或文件的。



在Windows中描述一个文件的具体的路径：

比如，上图的hello.txt文件，它在Windows系统中的路径可以描述为：`D:\aaa\hello.txt`



#### Linux文件系统

Linux和Windows不一样

- Windows是有多个盘符，作为`并列`的顶级目录，如上图，C盘和D盘，它俩是并列的
- 在Linux系统中，`顶级`目录，只有一个，叫做：`/`

![image-20220711154737217](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711154737.png)

如上图，在Linux系统中

- `/`作为最顶级的目录存在
- 在`/`之下，可以有文件夹、可以有文件
- 文件夹内可以有文件夹，也可以有文件

![image-20220711154947797](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711154947.png)

如上图，如果要在Linux系统中描述`a.txt`的路径，可以写为：`/aaa/a.txt`



#### 区别

- Linux系统只有1个顶级目录，叫做`/`，也称之为`根目录`，  Windows是有多个并列的顶级目录，比如C盘、D盘等
- 在路径的描述上：
  - Windows：`D:\aaa\bbb\c.txt`，使用的是D盘盘符作为根，使用`\`来区分层次
  - Linux：`/aaa/bbb/c.txt`，使用唯一的`/`作为根，使用`/`来区分层次
  - 对于Linux系统的路径，开头的`/`作为根存在， 后面的`/`只是作为层次区分的符号

![image-20220711155326876](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711155326.png)

如图，在FinalShell中，展示了Linux系统的文件系统结构，可以看到，最高级的就是`/`






### Linux命令的基础语法结构

```shell
# 一个Linux命令，主要包含如下内容
命令本体 [可选的参数] [可选的选项]
```

`[]`包围起来的，表示是可选的意思。



### ls命令

功能：列出来`当前文件夹`下，有哪些文件

![image-20220711155721096](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711155721.png)

如图，通过ls可以看到，在当前的文件夹下有许多的文件和文件夹，上图：`深颜色的`是文件夹，白色的是文件。

![image-20220711155850893](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711155851.png)



#### ls命令的选项

**-a选项**

语法：

```shell
ls -a
# 注意ls 和 -a 之间有一个 空格
```

通过ls -a就可以看到当前文件系统下的隐藏文件和隐藏文件夹

![image-20220711160543750](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711160543.png)

如图，Linux系统的隐藏文件就被列出来了。



**-l**选项：

语法：

```shell
ls -l
# 注意ls 和 -l之间有一个空格
```

可以将横向平铺的结果，变成纵向的结果

![image-20220711160741682](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711160741.png)



**选项的组合使用**

语法：

```shell
ls -la
# 表示组合使用-l和-a的功能
```

可以将结果变成纵向结果，同时列出来隐藏文件

![image-20220711160946527](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711160946.png)

如图，既有纵向结果又可以看到隐藏的文件



#### ls命令的参数

回顾一下基础命令的语法：

```shell
命令本体 [可选的参数] [可选的选项]
```



对于ls命令来说：

```shell
ls 想要查看的目录 可用的选项(-a -l)
```

想要查看的目录，`如果你不写，默认就查看当前文件夹`

如果`你写了，就可以查看你指定的目录`

比如，我想看看Linux的`/`（根目录)下面有什么东西：

```shell
ls / -la
# 查看 / 目录下面有什么内容
# 以及配合纵向显示 和 显示隐藏文件的功能
# ls后面的/ 就是参数
```

![image-20220711161425900](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711161426.png)







### pwd命令查看当前文件夹是什么

功能：在命令行中，显示，你当前的文件夹在什么地方

语法：`直接执行：pwd`并回车即可

![image-20220711160142246](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711160142.png)

![image-20220711160307280](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711160307.png)

如图，我们通过`pwd`确认了当前的文件夹是：`/root`

通过FinalShell工具，可以看到，在这个文件夹下面，的文件夹和文件和ls列出的是一样的。

> 里面多了许多的用`.`作为开头的文件，这些是隐藏文件



### cd 命令

含义：`change directory` 取了首字母c和d

作用：切换当前的工作目录

用法：

```shell
cd [参数]
```

> []表示可选

- 直接使用cd，将会进入用户的HOME目录
- `cd /`，将进入到`/`目录
- `cd /usr` ，将进入到`/usr`目录



### 特殊符号

Linux路径中有一些特殊符号，有特殊的作用

比如：

- `~`，表示的是用户的HOME目录（注意，登陆的用户不同，表示的路径不同），比如：
  - 以`root`用户登陆，~ 表示： `/root`
  - 以普通用户登录，比如`itheima`，~表示：`/home/itheima`
  - 使用： `cd ~`，返回HOME目录， 或者：`cd ~/Desktop` 表示切换到HOME目录内的Desktop文件夹
- `-`，表示的是`上一次`所在的工作目录，比如：`cd -`表示返回上一次所在的工作目录中。
- `.`，表示当前目录，比如`cd .`，当前目录`不动`
- `..`，表示上一级目录，比如`cd ..`，向上退一级目录
- `*`，通配符，和任意长度任意内容相匹配（表示相同），比如：
  - `rm -rf *.txt` 删除所有`.txt`结尾文件或文件夹
  - `rm -rf txt*`删除所有txt开头文件或文件夹
  - `rm -rf *txt*`删除所有名字中带有txt的文件或文件夹



### 用户的HOME目录

操作系统都是属于多租户（多用户）的模式，不管Windows还是Linux都是支持多个用户的。

操作系统由于用户众多，那么必定需要做权限的管理，不能由着普通用户随意操作，管理员除外。



普通用户由于没有特别的权限，所以，需要有一个专属的目录（文件夹）供他自己使用，拥有这个地方的全部权限。

举例：杭州市是政府的。但是盛泰时代山1001房间是你自己的。

在操作系统中，有一个自己不受到任何限制的地方（文件夹），称之为用户自己的HOME目录（家目录）

反之，离开HOME目录，将会受到限制。

#### Windows

默认用户的专属HOME文件夹，在：`C:\Users\用户名`

比如，Windows系统中有3个用户，分别是：`liudehua`、`zhoujielun`、`wanglihong`

它们各自的HOME就在：

- `C:\Users\liudehua`
- `C:\Users\zhoujielun`
- `C:\Users\wanglihong`



#### Linux

默认用户的专属HOME文件夹在：`/home/用户名`

比如，Linux系统中有3个用户，分别是：`liudehua`、`zhoujielun`、`wanglihong`

它们各自的HOME就在：

- `/home/liudehua`
- `/home/zhoujielun`
- `/home/wanglihong`

以及，root超级管理员的也有自己的HOME，位置是：

- `/root`

![image-20240410084846133](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410084846.png)

![image-20240410085033342](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410085033.png)

![image-20240410085047067](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410085047.png)





### Linux的相对路径和绝对路径

在Linux中，对于路径描述分为：相对和绝对



**绝对路径**：以 `/`开头的路径表示形式（从根目录开始描述路径），比如：

- `/root`
- `/usr/local`
- `/a/b/c/d/e`
- 特点：都是以`/`开头



相对路径：不以`/`开头的是相对路径，这个路径在生效的时候，会自动拼接当前所在路径，比如：

- cd Desktop，这就是相对路径的应用，表示：进入到`当前`文件夹内的Desktop文件夹
- 相对路径，它的使用是和`当前所在目录` 强关联





### mkdir命令 - 创建文件夹

功能：创建文件夹

语法：

```shell
# 回忆一下Linux基础命令的格式： 命令本体 [可选的参数] [可选的选项]
mkdir 要创建的文件夹的路径 [-p选项]
```

- 参数表示要创建文件夹的路径（相对路径或绝对路径都可以）
- 选项有1个，`-p`选项

![image-20220711170608433](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711170608.png)



#### 选项

**-p选项**

功能：将前置不存在的文件夹一并创建了

![image-20220711170919458](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711170919.png)


### touch命令 - 创建文件

语法：

```shell
touch 文件的路径
```

在指定的文件路径上， 创建出来1个文件

![image-20220711174811013](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711174811.png)

如图，在当前目录中，就创建了hello.txt文件




### cat命令 - 查看文件的内容

语法：

```shell
cat 被查看的文件
```

![image-20220712091201723](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712091201.png)

如图，文件的内容被正常的查看到了。



### more命令 - 以翻页的形式查看文件的内容

语法：

```shell
more 被查看的文件
```

当我们查看文件后，可以用键盘来控制查看：

- space（空格键）向下翻页
- `b`，向上翻页
- `q`，退出查看




### cp命令 - 文件或文件夹的复制

功能：完成文件或文件夹的复制

语法：

```shell
cp [-r] 参数1 参数2
```

- 参数1：被复制的路径（可以是文件，也可以是文件夹）
- 参数2：要复制去的地方

![image-20240409162610148](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/09/20240409162610.png)

如上图，在当前目录将haha.txt复制一份，并自动改名为：hello.txt



![image-20240409162757150](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/09/20240409162757.png)

将当前目录的haha.txt，复制到`/`目录内，不改名（同名复制）



![image-20240409162836826](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/09/20240409162837.png)

将当前目录的haha.txt，复制到`/`目录内，并改名为`heihei.txt`



> 如何判断是否改名：
>
> - cp haha.txt /root/itheima.txt
>   - 这种写法的参数2，包含文件名（itheima.txt)，最终会改名为itheima.txt
> - cp haha.txt /root/
>   - 这种写法的参数2，不含文件名，仅仅复制haha.txt到/root/内，不改名复制过去





#### 选项

**-r选项**

功能：递归复制，将文件夹内的内容也复制过去，要复制文件夹，请用`-r`

如果不用：![image-20220711175258890](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711175258.png)

![image-20220711175325089](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711175325.png)

如图，使用`-r`选项，就可以正常复制文件夹了。





### mv命令 - 文件或文件夹的移动（剪切）同时兼具改名的功能

mv: `m`o`v`e

语法：

```shell
mv 被移动的文件或文件夹 将要去移动到的地方
```

![image-20220711175550469](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711175550.png)

如图，将hello.txt移动到bbb文件夹的内部

![image-20220711175813938](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711175814.png)

如上图，可以发现，文件被移动到`ccc`文件夹内部，同时被`修改名字`为：`heiheihei.txt`



> mv命令，不仅可以移动，同时还兼具改名的功能

![image-20220711180019139](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711180019.png)

如图，将`nihao.txt`移动到当前目录下作为`dajiahao.txt`存在，就等同于改名字了。



同样，改名字也可以用于文件夹：

![image-20220711180138777](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711180138.png)

同样，将ccc移动到当前目录下作为aaa存在，所以这个操作等同于将`ccc`改名为`aaa`



> 提示：Linux的命令是非常、非常、非常多的
>
> - 我们只是学习了一部分常用的
> - 这些命令`千万不要`死记硬背，因为你记不住
> - 要做到的是，在学习的时候，练习几遍，在以后用到的时候再用即可，如果忘记查一查笔记或者百度。


### rm命令 - 删除文件或文件夹

功能：删除文件或文件夹

语法：

```shell
rm 被删除的路径 [-r选项 | -f选项]
```

- 参数：表示被删除的路径（可以是文件也可以是文件夹）
- 选项：
  - -r
  - -f

![image-20220711171256558](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711171256.png)





#### 选项

**-f选项**

含义：强制删除，不提示（英文单词`force`的缩写）

![image-20220711171509647](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711171509.png)

如图，没有任何提示，文件就被删除了。



**-r选项**

含义：递归删除，将指定的文件夹的内部也全部清空

![image-20220711171605384](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711171605.png)

如图，直接`rm aaa`是无法删除aaa这个文件夹的，所以需要用`-r`选项

![image-20220711171704355](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711171704.png)

如图，可以发现，是可以删除，但是要有很多的提示，很烦



**组合选项**

含义：-r和-f可以组合使用，比如：`rm -fr` 或者 `rm -rf` 都一样

表示，递归删除（删除文件夹内部和文件夹本身），并且强制删除，不提示

![image-20220711171844865](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/11/20220711171844.png)

如图，文件夹被删除，并且没有任何提示。



**重点注意**

==以下内容一定要切记，否则可能被开除==

```shell
rm -rf /
rm -rf /*
# 以上命令千万千万千万千万千万不要执行
# 以上命令等同于给根目录格式化清空
```

表示，从根目录开始删，将根目录里面的全部内容删除



==每一次使用rm -rf的时候一定要小心再小心==



**实际经验**

以前在公司工作的时候，要做什么操作，没有权限：

- 找运维，给你做，不要自己做

==特别是运维说：我把root给你，你自己来==，==千万不要接受，不要接受root账户==


### find命令 - 文件查找命令

功能：根据条件，查找满足要求的文件

基础语法按照文件名搜索：

```shell
find 要查找的路径 [-name选项  -size选项] 要查找的条件

-name 表示按照文件名字搜索
-size 表示按照文件大小搜索
```

示例，在Linux中全盘（从根目录开始）搜索名字叫做test的文件

```shell
find / -name "test"
```

![image-20220712111323845](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712111324.png)

如图，从根目录开始，所有文件名字叫做`test`的文件就被搜索到了。

> 配合通配符可以完成更加丰富的搜索条件
>
> 详细参见下方通配符的笔记



基础语法按照文件大小搜索：

```shell
find / -size +100M
# +100M 表示大小大于100MB的文件
# -100M 表示大小小于100MB的文件
```

> 经常用于在Linux系统中找出大文件



### 通配符 *

通配符`*`表示，匹配任意内容（有没有内容、内容不管是什么，都和*匹配成功）

![image-20220712111543091](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712111543.png)

如图，配合find搜索，找到了全部`以test`开头的文件(以test开头后面不管是什么（哪怕啥也没有）也能匹配成功test*)

![image-20220712111708343](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712111708.png)

如图，所有以`test结尾`的文件，就全部搜索到了

![image-20220712111841020](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712111841.png)

如图，只要带有`test`，就算满足条件，就搜索到了



> 通配符可以用于很多场景：
>
> - find 查找 用通配符匹配名称
> - ls 列出用通配符列出，如 `ls /root/*.txt`
> - rm 删除，如 `rm -rf ./*.txt`，删除所有.txt结尾文件
> - `cp *.txt /root/` 将全部.txt复制到/root内
> - `ls | grep *.txt`
> - `cat *.txt`
> - ...等等




### which 命令 - 查找指定的命令在哪里

> 我们所执行的Linux命令：`它们都是程序`
>
> 比如：cd、ls、pwd、mkdir、cp、mv等等命令，这些命令其实都是一个个程序
>
> 既然是程序，这些程序就肯定有程序文件，存在于Linux系统中

功能：通过which命令，找到执行的命令，的程序文件在哪里

语法：

```shell
which 要查找的命令
```

![image-20220712112802496](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712112802.png)

如图，就找到了`mkdir`这个命令的程序存在与：`/usr/bin/mkdir`




### less命令 - 以翻页和支持搜索的形式查看文件内容

语法：

```shell
less 被查看的文件
```

支持键盘的快捷方式：

- `space(空格键)`，向下翻页

- `b`，向上翻页

- `q`，退出查看

- `/`，输入要搜索的内容并回车，即可完成内容的搜索

  - `n`，向下搜索下一个匹配项

  - `N`，向上搜索匹配项

  - 如果搜索的内容，没有找到会出现：

    ![image-20220712092724062](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712092724.png)



### head命令 - 查看文件的头部内容

语法：

```shell
head [-n选项] 被查看的文件
```

不带选项查看文件，默认查看`头部的10条`内容



**-n选项**

功能：指定查看头部的多少条数据

如下：

```shell
head -n 20 文件
# 表示查看文件的前20条数据
```



### tail命令 - 查看文件的尾部内容

语法：

```shell
tail [-f选项 -n选项] 被查看的文件
```

不带选项查看，是直接查看文件的`尾部10条`内容



#### 选项

**-n选项**

功能：和head的-n一样，表示查看几条

```shell
tail -n 1 文件
# 表示查看文件的最后1条数据
```





**-f选项**

f来自于英文单词：`follow`

功能：跟随文件的尾部，`持续的`查看文件的修改

![image-20220712094200764](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712094200.png)

如图，tail -f后，程序就不会退出，会一直运行

一直运行的逻辑是：持续的监控文件的尾部修改，如果尾部有新增的内容，立刻就显示出来

如果要停止`tail -f`，可以使用键盘快捷键：`ctrl + c`

> ctrl + c 是Linux系统中的万能停止快捷键，等同于Windows系统给窗口点击`X`关闭是一个意思

> 后续在学习到Hadoop等大数据框架后，`tail -f`是非常合适查看框架的运行日志的。



#### -f -n 混合使用

```shell
tail -n 3 -f 1.txt
```

先展示1.txt的最后3行内容，然后持续跟踪1.txt的更新（不会退出）



快捷写法：

```shell
tail -3f 1.txt
```

和上面的命令等同。



#### tailf命令

tail -f 可以通过 `tailf`直接用即可



混合-n选项

```shell
tailf -3 1.txt
```

先展示1.txt的最后3行内容，然后持续跟踪1.txt的更新（不会退出）

等同于 `tail -n 3 -f 1.txt` 和 `tail -3f 1.txt`







### | 管道符

管道符是Linux的特殊符号，表示，将`左侧`内容的输出，作为符号右侧内容的输入。

目前学习到的命令有2个支持管道符应用：

- grep [选项] 关键字 `内容输入`
- wc [选项] `内容输入`



概念：

![image-20240410100604377](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410100604.png)

如图，将命令1的执行结果，作为命令2的输入。



示例：

```shell
cat hello.txt | grep python
```

![image-20240410100652687](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410100652.png)

如上图，将`cat hello.txt`的结果作为 grep命令的输入。

上图的grep命令只写了关键字，没有写内容输入，内容输入由管道符提供。



示例：

![image-20240410100759579](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410100759.png)

如上图，`ls /`的结果，作为`wc -w`命令的输入

统计根目录下有多少个内容（文件或文件夹），结果是20个



#### 嵌套使用

如下图

![image-20240410100405219](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410100405.png)

可以写很多的管道符，从左到右执行：

```shell
# 分析：cat hello.txt | grep 666 | grep ha | grep heihei | wc -w

1. 执行 cat hello.txt 将结果作为 grep 666的输入

2. cat hello.txt | grep 666的结果作为 grep ha的输入

3. cat hello.txt | grep 666 | grep ha  的结果作为 grep heihei的输入

4. cat hello.txt | grep 666 | grep ha | grep heihei 的结构作为wc -w的输入

最后结果4

简单来说，上面的命令是：
1. 查看hello.txt的内容
2. 过滤里面的666
3. 接着过滤ha
4. 接着过滤heihei
5. 接着统计最后结果有多少个单词
```





### grep 命令 - 过滤内容

基础用法（比较少）

语法：

```shell
grep 被过滤的内容 内容输入
```

![image-20220712101419288](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712101419.png)

参数1：被过滤的关键字

参数2：`内容输入`（可以用文件路径代替）

#### -n 选项

可以显示出来，匹配的内容在文件中的`行号`

![image-20240410093726560](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410093726.png)

如上图，显示出匹配的内容，在第3行。



### wc 命令

作用：统计文件（输入内容）的一些情况如：行数、单词数、字节数等

语法：

```shell
wc [-c -m -l -w] 内容输入（文件路径）
```

示例：

```shell
wc hello.txt
```

![image-20240410094308116](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410094308.png)

如图，结果是： 行数 单词数 字节数 文件名



选项：

- -c 统计byte字节数
- -m 统计字符数
- -l 统计行数
- -w 统计单词

![image-20240410094454811](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410094455.png)

选项集体使用

![image-20240410094648201](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410094648.png)



### echo 命令 输出指定的内容

语法：

```shell
echo 被输出的内容
# 演示
echo hahaha   # 在控制台输出hahaha
echo "ni hao ma" # 在控制台输出ni hao ma
# 一般我们建议复杂输出内容，通过双引号包围一下
```



### 重定向符号

在Linux中，还有2个特殊符号：`>` 和 `>>`

称之为重定向符号，功能是：将符号左侧内容的输出， 写入到右侧指定的文件中

- `>`，`覆盖`重定向，将左侧内容的输出，覆盖写入到右侧文件
  - 覆盖：老的内容全部清理，然后写入内容
- `>>`，`追加`重定向，将左侧内容的输出，追加写入到右侧文件
  - 追加：老的内容保留，在原有内容的最后开辟新的一行，写入内容

一般重定向符号，都是配合其它命令一起使用，比如`echo`

![image-20220712103045938](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712103046.png)

如图，将echo命令的结果，写入到指定的文件中，`覆盖写入`

![image-20220712103320896](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712103321.png)

如图，将echo命令的结果，写入到指定的文件中，`追加写入`





### && 和 || 符号

&&与运算符（类似Python的 `and`）

||或运算符（类似Python的 `or`）

- &&表示的是：左边的命令执行成功，会接着执行右边的命令

  ```shell
  echo "你好吗？" >> 1.txt && echo "我好吗？" >> 1.txt && echo "大家都好" >> 1.txt
  # 如上，可以向1.txt中一次性追加3条数据
  ```

  &&符号，一般用于：在`1条`Linux命令中，执行`多个`操作

  ![image-20220712104731320](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712104731.png)

  如图，要注意的是，上一条命令的失败，下一条不会执行，如图：我好帅就没有输出

- ||表示的是：左边的命令`执行失败`，才会执行右边的命令

  ![image-20220712104916125](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712104916.png)

  如图，由于mkdir命令执行失败，所以`我好帅`被输出了。

  `||`，一般用于做备份命令，如果前置命令失败，下一条命令用来收尾





### 符号总结

- `.`，表示当前路径

- `..`，表示上一级路径

- `~`，表示用户的HOME目录

  ![image-20220712105337573](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712105337.png)

- `|`，管道符

  ![image-20220712105352423](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712105352.png)

- `>`，符号左边命令的输出，`覆盖`写入右边提供的位置

- `>>`，符号左边命令的输出，`追加`写入右边提供的位置

- `&&`，左边命令成功右边命令执行

  ![image-20220712105405838](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712105405.png)

- `||`，左边命令失败，右边命令执行



### ln命令 - 创建软链接

> 软链接：和Windows系统的`快捷方式`是一个意思
>
> 将一个文件或者文件夹，创建出来一个快捷方式

语法：

```shell
ln -s 被创建快捷方式的文件或文件夹 快捷方式放到哪里
-s 表示软链接（快捷方式）
```

示例：

```shell
# 给/usr/local/bin文件夹创建快捷方式
ln -s /usr/local/bin kjfs
```

![image-20220712113410277](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712113410.png)

如图，kjfs这个文件夹就指向了 `/usr/local/bin`这个文件夹



示例：

```shell
# 给/root/dajiahao.txt创建快捷方式
ln -s /root/dajiahao.txt nihao.txt
```

![image-20220712113718112](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712113718.png)

> 如果要查看软链接的指向，通过 `ls -l`即可。




### tar命令 - 进行压缩或解压缩

> 在Linux操作系统中，压缩包一般是`.tar`，`.gz`结尾的压缩包
>
> 在Windows操作系统中，压缩包一般见到的是`.zip`，`.rar`结尾的压缩包



#### 进行文件的压缩（打包）

语法：

```shell
tar [-z -c -v -f] 参数1 参数2
```

参数1：打包后的压缩包的路径

参数2：被打包的文件或文件夹

选项：

- -z使用`gzip`压缩格式，不写-z，使用`tar`格式
- -c 表示执行压缩模式
- -v 表示显示压缩的过程
- -f 指定生成的压缩包的路径（指定的参数1）



一般生成压缩包，基本都是固定写法：

```shell
# 写法1，生成tar格式的包：
tar -cvf xxx.tar 被压缩的文件或文件夹

# 写法2，生成gzip格式的包：
tar -zcvf xxx.tar.gz 被压缩的文件或文件夹
```

打tar格式的压缩包演示：

![image-20220712145937837](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712145938.png)

如上图，将`1.txt`，`2.txt`，`dajiahao.txt` 三个文件，压缩到`test.tar`这个包内



打gzip格式的压缩包演示

![image-20220712150126711](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712150126.png)

如上图，将`1.txt`，`2.txt`，`dajiahao.txt` 三个文件，压缩到`test.tar.gz`这个包内



#### 解压压缩包的操作

语法：

```shell
tar [-z -x -v -f] 参数1 [-C 参数2]
```

选项：

- -z 解压 gzip格式，不写的话，是解压tar格式
- -x 表示执行解压模式
- -v 表示显示解压的过程
- -f 指定被解压的压缩包的路径（指定的参数1）

参数1：被解压的压缩包

选项：

- -C 指定将内容解压到哪里，如果不写，默认解压到压缩包所在的位置

  如果使用`-C`，后面必须指定参数2：要解压到哪里的路径



示例：解压tar格式

![image-20220712151011105](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712151011.png)

如图，在当前目录中的test.tar文件解压出来了：1.txt 2.txt dajiahao.txt3个文件



示例：解压gzip格式（结尾是.gz的）

![image-20220712151150662](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712151150.png)

解压gzip格式，解压出来如图3个文件







示例：将内容解压到指定的目录中

> -C选项就是将内容解压到指定的地方
>
> 如果不写-C，就解压到当前路径，就相当于在Windows中将压缩包解压到当前文件夹
>
> 如果写-C,就相当于在Windows中，将内容解压到指定文件夹

![image-20220712151621366](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712151621.png)

如图，通过`-C`的选项，将内容解压到指定的文件夹内了。

==-C一定要注意，是大写的C==





### help命令

> 在每一个Linux命令中，其实都有非常丰富的选项可以用
>
> 比如ls，我们只讲解了`-l` `-a`2个选项
>
> 其实它有很多的选项
>
> 可以通过命令的：
>
> -h
>
> 或
>
> --help
>
> 选择去查看命令的帮助文档

比如，查看ls的帮助文档就是：`ls --help`

![image-20220712115113264](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/12/20220712115113.png)

> 选项太多，不可能每一个都学习，我们主要学习常用选项
>
> 剩余选项，大家知道可以help列出来即可
>
> 需要的时候翻阅帮助文档



> help命令列出来的只是基础简略的帮助文档
>
> 如果想要看命令的详细文档，需要使用man命令



### man命令 - 查看命令的`详细`帮助文档

语法：

```shell
man 被查看详细帮助文档的命令
# 如
man ls
# 表示查看ls命令的详细帮助文档
```



- 命令的`-h`或`--help`选项，是查看`简略帮助文档`
- `man 命令` 查看命令的`详细帮助文档`






### 通过vi | vim 编辑器完成文件的编辑

> vi | vim程序，是可以完成文件的编辑操作，类似Windows系统的记事本程序

在Linux操作系统中，如果你使用`命令行`的形式去完成操作，是无法支持`鼠标操作`的。

在Linux命令行中，一切都是`键盘操作`



#### 简介

在Linux系统中，如果要修改、编辑文件，需要通过内置的`vi`程序来进行编辑

> vim是vi的升级版，这俩是同一个东西



#### vi编辑器的工作模式

![image-20240410120640224](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410120640.png)

vi(vim)打开就进入命令模式，在命令模式内可以输入快捷按键（见下表）控制文件内容更改。

- 通过按键：i、o、O，可以进入插入模式（打字模式），进行内容编写，按esc回退到命令模式
- 通过按键：`:`，进入底线命令模式，回车或esc回退到命令模式（或者就退出了vim了）

> vi/vim编辑器，核心就是命令模式，基于命令模式为中转站，在其它两个模式之间反复横跳。



| 模式         | 命令           | 描述                                      |
| ------------ | -------------- | ----------------------------------------- |
| 命令模式     | `i`            | 在当前光标位置进入`输入模式`              |
| 命令模式     | `o`            | 在当前光标下一行进入`输入模式`            |
| 命令模式     | `O`            | 在当前光标上一行进入`输入模式`            |
| 输入模式     | `esc`          | 任何情况下输入`esc`都能回到命令模式       |
| 命令模式     | `dd`           | 删除光标当期行的内容                      |
| 命令模式     | ndd            | n是数字，表示删除当前光标向下n行的内容    |
| 命令模式     | yy             | 复制当前行                                |
| 命令模式     | nyy            | n是数字，复制当前行和下面的n行            |
| 命令模式     | p              | 粘贴复制的内容                            |
| 命令模式     | u              | 撤销修改                                  |
| 命令模式     | ctrl + r       | 反向撤销修改                              |
| 命令模式     | `gg`           | 跳到首行                                  |
| 命令模式     | `G`            | 跳到行尾                                  |
| 命令模式     | dG             | 从当前行开始，向下全部删除                |
| 命令模式     | dgg            | 从当前行开始，向上全部删除                |
| 命令模式     | d$             | 从当前光标开始，删除到本行的结尾          |
| 命令模式     | d0             | 从当前光标开始，删除到本行的开头          |
| 命令模式     | 键盘上、键盘j  | 向上移动光标                              |
| 命令模式     | 键盘下、键盘k  | 向下移动光标                              |
| 命令模式     | 键盘左、键盘h  | 向左移动光标                              |
| 命令模式     | 键盘右、键盘l  | 向后移动光标                              |
| 命令模式     | n键盘上        | 向上移动光标n行，比如按5n+↑ 光标向上跳5行 |
| 命令模式     | n键盘下        | 向下移动光标n行，比如按5n+↓ 光标向下跳5行 |
| 命令模式     | 0              | 移动光标到当前行的开头                    |
| 命令模式     | $              | 移动光标到当前行的结尾                    |
| 命令模式     | pageup(PgUp)   | 向上翻页                                  |
| 命令模式     | pangdown(PgDn) | 向下翻页                                  |
| 命令模式     | /              | 进入搜索模式                              |
| 命令模式     | n              | 向下继续搜索                              |
| 命令模式     | N              | 向上继续搜索                              |
| 底线命令模式 | `:wq`          | 保存并退出                                |
| 底线命令模式 | :q             | 仅退出                                    |
| 底线命令模式 | `:q!`          | 强制退出                                  |
| 底线命令模式 | :w             | 仅保存                                    |
| 底线命令模式 | :set nu        | 显示行号                                  |
| 底线命令模式 | :set paste     | 设置粘贴模式                              |



##### 无法打开vi程序，提示如下

![image-20240410121815943](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410121816.png)

因为修改了文件，但是没有保存，vim会自动备份你的修改在`.同名文件.swp`中，如下：

![image-20240410121901885](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410121902.png)

`.a.py.swp`是备份。

- 如果vi正常退出（放弃修改退出、保存修改退出），此备份文件会自动消失
- 如果是异常退出，此备份文件还在，vi再次修改文件，就会有上面的提示了，可以选择：
  - 直接回车：只读方式打卡文件
  - 输入E：直接编辑
  - 输入`R`：恢复上次未保存的修改
  - 输入`D`：删除此备份文件
  - 输入`Q` 或 `A`：退出



确认你的操作，然后手动删除此`.swp`文件即可。









## Linux的用户和权限

### root用户

操作系统会有一个管理员用户，在Linux系统中，管理员用户叫做：`root`，也称之为：`根用户`



### 基础概念

![image-20220714092831007](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/14/20220714092831.png)

如图，Linux操作系统是

- 可以有多个用户的
- 也可以将多个用户划分为一个逻辑的组
- 在系统中，有一个超级管理员用户（root)有整个系统的全部权限
- 其它的普通用户，权限是基于root去进行分配的。



### 普通用户的权限

非`root`用户，都是普通用户，它们的全部权限都在：`/home/用户名`自己的家目录内。

离开家目录，将寸步难行。

![image-20240410145825811](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410145826.png)

如图，普通用户，在非家目录中，什么也干不了。





### 用户切换命令

切换用户使用：`su`命令，即：`switch user`的缩写。

语法：

```shell
su [-] [用户名]
```

- `-`是可选，表示切换用户的同时，加载更新环境变量
- 用户名可选，如果不提供，则切换到`root`



举例：

```shell
su - itheima		# 切换到itheima用户
su -				# 切换到root用户
su - root			# 切换到root用户
```

> - root 用户，切换到任何用户，无须密码
> - 任何用户切换到其它用户（包含root），必须提供密码



#### exit命令

在Linux中，切换用户后，可以通过exit退出（取消）切换。

快捷键：`ctrl + d`

如图：

![image-20240410150738017](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410150738.png)

#### 如何判断当前登陆的用户是什么

![image-20240410150814840](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410150815.png)

如图，命令行会提示当前登陆用户。

或者通过命令：

```shell
whoami
```

![image-20240410150859920](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410150900.png)

如图，通过whoami查看当前登陆用户。



### 修改用户密码

#### root用户视角

命令：

```shell
passwd [-d] [用户名]
```

- 不指定用户名，则修改自己的密码
- 如果指定用户名，则修改指定用户
- -d选项可选，可以清除指定用户的密码，让这个用户没有密码即可登陆

root修改密码可以跳过安全认证，多简单都能成功，且不需要输入老的密码。



#### 普通用户视角

命令：

```shell
passwd
```

- 只能改自己的密码
- 并且无法跳过密码的复杂验证，不能低于8个字符，也不能过于简单
- 并且需要验证旧密码



### sudo命令 - 临时以root身份执行命令

假设我们拥有最高权限，或者在理论上是值得交付最高权限的场景下，可以给我们自己的普通用户，开通`sudo`权限，允许我们的普通用户，临时以root身份执行命令。



语法：

```shell
sudo 其它任何命令
```

作用：让sudo后面的其它任何命令，以root身份执行，避免权限受限。



普通用户是无权使用sudo的，需要在root身份下，开通此用户的sudo权限。



#### 开通

以root身份，执行：`visudo`

在打开的`vi`编辑器中，最下方添加：

```shell
用户名 ALL=(ALL)	NOPASSWD: ALL
```

然后`:wq`保存退出即可。



示例：

```shell
itheima ALL=(ALL)	NOPASSWD: ALL
```

给itheima用户，开通sudo权限。



#### 示例

![image-20240410155132464](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410155132.png)

如上，就有权限执行在根目录下创建文件夹了。

> 这个权限是临时的，仅限那一条sudo ... 命令





### 用户的用户组



#### 概念

![image-20240410160122091](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410160122.png)

如上图，Linux是一个多用户且多组的操作系统。

- 可以创建多个用户
- 可以创建多个组
- 1个用户可以加入多个组、1个组也可以有多个用户。



> 对权限的管控，因为用户和组的概念，所以有：
>
> - 可以给单个用户授权
> - 可以给一个组授权

> 权限相关，就设计到：用户本是是否有权、它所在的组是否有权。



#### 创建组、用户的命令

==此命令必须以root执行。==



**创建组**

```shell
groupadd 组名
```

**删除组**

```shell
groupdel 组名
```



**创建用户**

```shell
useradd [-d] [-g] 用户名
```

- -d 指定用户的HOME家目录，如果不提供，默认在：`/home/用户名`
- -g 指定用户加入某个组，如果提供，则默认加入：`用户同名的组`



**删除用户**

```shell
userdel [-r] 用户名
```

- -r 表示删除用户的HOME目录，如果不提供-r，则保留



**查看用户信息**

```shell
id 用户名
```

可以显示用户的：

- 用户名和其id
- 所在组名和其id

![image-20240410161559879](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410161600.png)

如图，`xiaoqiang`，用户id 1005，所在2个组，1：football id 1005，2：pinpang id 1006



**将用户加入组**

```shell
usermod -aG 组名 用户名
```

- 将用户加入指定的组



#### 查看系统有哪些用户和组

**查看有哪些用户**

```shell
getent passwd
```

![image-20240410162253690](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410162254.png)



**查看有哪些组**

```shell
getent group
```

![image-20240410162406940](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410162407.png)



### 文件归属

在Linux系统上，是有许多文件的。

- 文件很多
- 用户很多

文件的归属，以及哪个用户可以操作哪个文件，这些都是需要有严格的授权划分的。

![image-20220714093239132](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/14/20220714093239.png)

如图，Linux系统中，通过`ls -l`，可以查看纵向的文件列表，同时可以查看文件的归属

如上图，`root root`表示的是文件：

- 归属于root用户
- 归属于root用户组

![image-20220714093421672](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/14/20220714093421.png)

如图，这就是文件详细的权限设定的细节：

- r:read，可以读取（查看内容）
- w:write，可以修改
- x:可以执行

![image-20220714093537984](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/14/20220714093538.png)

文件的权限细节中，有`9`位长度，细节如下：

- 前三位，表示文件的归属用户的权限
- 中间三位，表示文件的归属用户组的权限
- 后三位，其它用户的权限



比如，一个文件在归属上是：属于`test`用户，属于`class`用户组

```shell
rwx-w-r--
test用户对这个文件的权限是：rwx,可读可写可执行
class用户组对这个文件的权限是：不可读，可以修改，不可以执行
其它用户对这个文件的权限是：可以读取，不可修改，不可以执行
```



### 文件和文件夹

![image-20220714094224850](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/14/20220714094225.png)

如图，在权限的前方有一个符号：

- `-`，表示是文件
- `d`，表示是文件夹



对于文件和文件夹，rwx的含义不太相同：

- r读取
  - 文件是可以读取文件内容
  - 文件夹是表示可以列出文件夹里面的内容
- w写入
  - 文件表示可以修改文件的内容
  - 文件夹表示：可以在文件夹内删除文件、改名文件、新建文件等。
- x执行
  - 文件：表示文件可以作为程序执行
  - 文件夹：表示你是否可以`cd`进入这个文件夹



![image-20220714095209584](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2022/07/14/20220714095209.png)

如图，当我们没有权限的时候，就会遇到：

`Permission denied`



### 文件和文件夹的权限细节

![](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410170420.png)

如图，通过`ls -l` 列出的详细信息中：

- 序号1：文件/文件夹的权限细节
- 序号2：文件/文件夹所属用户
- 序号3：文件/文件夹所属用户组

序号1的细节：

![image-20240410170502209](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/10/20240410170502.png)

共10位：

- 第一位：-表示文件，d表示文件件，l表示软连接
- 第2~4位：所属用户所拥有的权限
- 第5~7位：所属用户组所拥有的权限
- 第8~10位：其它用户所拥有的权限



**r**

读取权限

- 如果是文件：表示可以查看文件内容
- 如果是文件夹：可以查看文件夹内的内容，如ls 查看文件夹内有啥



**w**

写权限

- 如果是文件：可以修改文件内容
- 如果是文件夹：可以在文件夹`内部`，创建、删除、改名、复制文件或文件夹等操作



**x**

执行权限

- 如果是文件，可以将此文件作为程序执行
- 如果是文件夹，可以cd进入此文件夹







### 修改文件或文件夹的权限

使用命令：`chmod`命令



在Linux的`chmod`命令中，对不同的权限有具体的数字标号：

- r标记为4
- w标记为2
- x标记为1



权限是三部分：

- 用户权限
- 用户组权限
- 其它用户权限

> 这3部分可以完全用数字来表示：
>
> 比如751，第一个7表示用户权限，第二个5表示用户组权限，第三个1表示其它用户权限
>
> - 7表示：可读可写可执行（r是4、w是2、x是1，和是7）
> - 5表示：可读 执行（r是4、x是1，和是5）
> - 1表示：可执行，不可读不可写（x是1）
>
> 所以751 == `rwxr-x--x`
>
> 比如：
>
> - 643 == `rw-  r--  -wx`
> - 542 == `r-x  r--  -w-`

> - 1:仅执行
> - 2:仅写
> - 3:wx 写和执行
> - 4:r 仅读
> - 5:rx 读和执行
> - 6:rw 读和写
> - 7:rwx 读和写和执行





#### chmod命令

语法1：

```shell
chmod 权限 被设置的文件或文件夹
# 比如
chmod 666 1.txt
# 给1.txt设置666(rw-rw-rw-)的权限
```





语法2：

```shell
chmod [+或- 以及 r w x] 文件
# 给文件单独增加x权限
chmod +x 文件
# 给文件单独增加w权限
chmod +x 文件
# 给文件减少x权限
chmod -x 文件
```

> rw作用范围只在前三位（用户权限）
>
> `x`除外，一次设置用户、用户组、其它用户的权限都受到影响



==root可以改任何文件或文件夹==

==普通用户只能修改自己所属的文件或文件夹==



#### chown命令

功能：修改文件的所属用户和用户组

语法：

```shell
chown [用户][:][用户组] 被修改的文件或文件夹
# 将1.txt设置为test2用户
chown test2 1.txt
# 将1.txt设置为test2用户，class用户组
chown test2:class 1.txt
# 将1.txt 设置为class用户组
chown :class 1.txt

# 将test文件夹用户设置为test2 组为class，内部也应用同样的设置
chown -R test2:class test
```

> 这个命令需要root执行







## Linux实用操作



### 常用快捷键

**ctrl + c**

强制退出

- 强制退出某个命令

  ![image-20240412095253078](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412095253.png)

- 或者强制重写命令（开新行写命令）

  ![image-20240412095259065](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412095259.png)



**ctrl + d**

登出（退出登陆）

等同于命令：exit

> 在任何需要输入exit的时候，都可以用这个快捷键代替



**history**

查看历史命令

![image-20240412095456503](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412095456.png)



**!命令**

从历史命令中，从最新到最老，搜索提供的字符能够匹配的命令

![image-20240412095456503](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412095550.png)

比如：`!su`

在上图中，即可匹配`su - root`，然后执行。



> 人是记不住太多最近的命令的，使用这个不要搜索的太远。一般5条命令内



**ctrl + r**

历史命令搜索，可以根据给定的字符，搜索历史命令匹配的。

![image-20240412095644913](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412095645.png)



**光标移动**

- ctrl + a，移动到行首
- ctrl + e，移动到行尾
- ctrl + ←，向左跳一个单词
- ctrl + →，向右跳一个单词



**清屏**

快捷键：`ctrl + l`

命令：`clear`





### yum(CentOS)安装和卸载软件

yum命令可以联网安装或卸载Linux系统中的程序。



语法：

```shell
yum [-y] [install | remove | search] 软件名称
```

- `-y` ，可选，表示自动确认，无须提示选择
- install | remove | search 三选一
  - install 安装
  - remove 卸载
  - search 搜索



安装输出的示例（安装mariadb）

```shell
[root@localhost ~]# yum install mariadb
已加载插件：fastestmirror, langpacks
Loading mirror speeds from cached hostfile
 * base: mirrors.aliyun.com
 * extras: mirrors.aliyun.com
 * updates: mirrors.aliyun.com
正在解决依赖关系
--> 正在检查事务
---> 软件包 mariadb.x86_64.1.5.5.68-1.el7 将被 安装
--> 正在处理依赖关系 mariadb-libs(x86-64) = 1:5.5.68-1.el7，它被软件包 1:mariadb-5.5.68-1.el7.x86_64 需要
--> 正在检查事务
---> 软件包 mariadb-libs.x86_64.1.5.5.60-1.el7_5 将被 升级
---> 软件包 mariadb-libs.x86_64.1.5.5.68-1.el7 将被 更新
--> 解决依赖关系完成

依赖关系解决

=======================================================================================================================
 Package                        架构                     版本                             源                      大小
=======================================================================================================================
正在安装:
 mariadb                        x86_64                   1:5.5.68-1.el7                   base                   8.8 M
为依赖而更新:
 mariadb-libs                   x86_64                   1:5.5.68-1.el7                   base                   760 k

事务概要
=======================================================================================================================
安装  1 软件包
升级           ( 1 依赖软件包)

总计：9.5 M
总下载量：8.8 M
Is this ok [y/d/N]: y
Downloading packages:
mariadb-5.5.68-1.el7.x86_64.rpm                                                                 | 8.8 MB  00:00:03     
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  正在更新    : 1:mariadb-libs-5.5.68-1.el7.x86_64                                                                 1/3 
  正在安装    : 1:mariadb-5.5.68-1.el7.x86_64                                                                      2/3 
  清理        : 1:mariadb-libs-5.5.60-1.el7_5.x86_64                                                               3/3 
  验证中      : 1:mariadb-libs-5.5.68-1.el7.x86_64                                                                 1/3 
  验证中      : 1:mariadb-5.5.68-1.el7.x86_64                                                                      2/3 
  验证中      : 1:mariadb-libs-5.5.60-1.el7_5.x86_64                                                               3/3 

已安装:
  mariadb.x86_64 1:5.5.68-1.el7                                                                                        

作为依赖被升级:
  mariadb-libs.x86_64 1:5.5.68-1.el7                                                                                   

完毕！

```



卸载输出的示例

```shell
[root@localhost ~]# yum remove mariadb -y
已加载插件：fastestmirror, langpacks
正在解决依赖关系
--> 正在检查事务
---> 软件包 mariadb.x86_64.1.5.5.68-1.el7 将被 删除
--> 解决依赖关系完成

依赖关系解决

=======================================================================================================================
 Package                    架构                      版本                              源                        大小
=======================================================================================================================
正在删除:
 mariadb                    x86_64                    1:5.5.68-1.el7                    @base                     49 M

事务概要
=======================================================================================================================
移除  1 软件包

安装大小：49 M
Downloading packages:
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  正在删除    : 1:mariadb-5.5.68-1.el7.x86_64                                                                      1/1 
  验证中      : 1:mariadb-5.5.68-1.el7.x86_64                                                                      1/1 

删除:
  mariadb.x86_64 1:5.5.68-1.el7                                                                                        

完毕！
```



搜索的示例

```shell
[root@localhost ~]# yum search wget
已加载插件：fastestmirror, langpacks
Loading mirror speeds from cached hostfile
 * base: mirrors.aliyun.com
 * extras: mirrors.aliyun.com
 * updates: mirrors.aliyun.com
================================================== N/S matched: wget ==================================================
wget.x86_64 : A utility for retrieving files using the HTTP or FTP protocols

  名称和简介匹配 only，使用“search all”试试。
```



> 同理，如果是Ubuntu系统，那么命令换成apt即可，其余不变。



> yum命令需要`root`权限





### systemctl 启动关闭控制系统服务（软件）

概念：在操作系统中，正规军软件（将自己注册为系统服务）即在操作系统中进行备案。

所谓的备案就是：提供操作系统对自己软件的：启动、关闭、状态检查、开机自启动的控制。



这种备案的正规军软件，称之为系统服务。

系统服务有2种：

- 操作系统自带的，比如Windows系统的`Windows update`服务，Linux系统的`network`服务
- 第三方软件自行注册的，比如Windows系统的`BaiduNetdiskUtility`，Linux系统的`httpd`服务（都是后面自己安装的软件，但是这些软件会将自己注册为服务）



对于服务的控制，在Linux系统，通过systemctl命令来控制。



语法：

```shell
systemctl (start | stop | restart | status | enable | disable) 服务名
```

- ()语法表示必写，`|` 表示或，如上是6个选项，6选一，必须选一个

- 服务名，就是被控制的服务

- start：启动

- stop：关闭

- restart：重启

- status：查看运行状态

  ![image-20240412105523133](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412105523.png)

  ![image-20240412105547778](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412105548.png)

- enable：开机启动

- disable：关闭开机启动





### 修复Linux操作系统无IP地址的问题

![image-20240412105711109](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412105711.png)

如上图，没有IP地址



通过几个命令修复：

```shell
# 关闭NetworkManager服务
systemctl stop NetworkManager
# 关闭其开机自启
systemctl disable NetworkManager
# 重启网络服务
systemctl restart network
```



### ln -s 软链接

软连接：和Windows系统中的快捷方式一样，可以创建一个文件或文件夹，进行快捷链接指向。



语法：

```shell
ln -s 参数1 参数2
```

- 参数1：被链接的本体
- 参数2：软连接的路径（包含其存放的位置和文件名）



示例：

![image-20240412111505037](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412111505.png)





#### 注意

被链接的本体，即参数1，可以用相对和绝对两种路径写法，不同的写法，得到的结果不同。

比如：

```shell
ln -s test.py soft.py
```

![image-20240412111601466](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412111601.png)

比如：

```shell
ln -s /root/test.py soft.py
```

![image-20240412111635507](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412111635.png)

可以看到：

- 参数1使用相对路径，软链接的指向也是相对
- 参数1使用绝对路径，软链接的指向也是绝对

> - 如果软连接的指向是相对的话，那么软连接文件或文件夹不可移动，否则失效。
>
> 如图：
>
> ![image-20240412111750500](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412111750.png)

为了避免软链接失效，可以用绝对路径。



### 修改Linux系统时区为中国

操作：

```shell
rm -f /etc/localtime
ln -s /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
```

- rm -f /etc/localtime  删除系统自带的localtime设置
- 将/usr/share/zoneinfo/Asia/Shanghai通过软连接的形式，替代过去即可





### date命令

功能：查看日期时间相关

语法：

```shell
date [-d] ["+格式化字符串"]
```

格式化字符串：

| 格式化字符串 | 含义                                                     |
| ------------ | -------------------------------------------------------- |
| %Y           | 年（2024）                                               |
| %y           | 年（后2位）                                              |
| %m           | 月                                                       |
| %d           | 日                                                       |
| %H           | 小时（24小时格式）                                       |
| %M           | 分钟                                                     |
| %S           | 秒                                                       |
| %s           | 时间戳（从（UTC时区）1970-01-01 00:00:00至今过去多少秒） |

示例：

```shell
[root@localhost Asia]# date "+%Y"
2024
[root@localhost Asia]# date "+%y"
24
[root@localhost Asia]# date "+今年是%Y"
今年是2024
[root@localhost Asia]# date "+今年是%Y年"
今年是2024年
[root@localhost Asia]# date "+今年是%Y年，是%m月，是%d日"
今年是2024年，是04月，是12日
[root@localhost Asia]# date "+%Y-%m-%d"
2024-04-12
[root@localhost Asia]# date "+%Y-%m-%d %H:%M:%S"
2024-04-12 11:51:22
[root@localhost Asia]# date "+%s"
1712893898
```



#### -d 日期计算

可以按照指定的单位进行日期增减

语法：

```shell
date -d "+|-n unit"
```

- `+|-` 表示增加或者减少
- `n`表示数字
- `unit`单位，支持：`year、month、day、hour、minute、second`



示例：

```shell
[root@localhost Asia]# date -d "+1 day"
2024年 04月 13日 星期六 12:00:11 CST
[root@localhost Asia]# date -d "-1 day"
2024年 04月 11日 星期四 12:00:20 CST
[root@localhost Asia]# date -d "-1 month"
2024年 03月 12日 星期二 12:00:26 CST
[root@localhost Asia]# date -d "+1 month"
2024年 05月 12日 星期日 12:00:57 CST
[root@localhost Asia]# date -d "+1 minute"
2024年 04月 12日 星期五 12:02:15 CST
[root@localhost Asia]# date -d "+15 second"
2024年 04月 12日 星期五 12:01:38 CST
[root@localhost Asia]# date -d "+15 second"
2024年 04月 12日 星期五 12:01:40 CST
[root@localhost Asia]# date
2024年 04月 12日 星期五 12:01:30 CST
[root@localhost Asia]# date -d "+15 second"
2024年 04月 12日 星期五 12:01:46 CST
[root@localhost Asia]# date -d "+1 year"
2025年 04月 12日 星期六 12:01:44 CST
[root@localhost Asia]# date -d "+1 year" "+%Y-%m-%d %H:%M:%S"
2025-04-12 12:02:06
```



如下，支持和格式化日期字符串一起用：

```shell
[root@localhost Asia]# date -d "+1 year" "+%Y-%m-%d %H:%M:%S"
2025-04-12 12:02:06
```



### 时间戳

我们表示时间，如果用年月日时分秒，是合适于人类阅读的，对于计算机来说，太麻烦。

计算机表示时间，一般纯数字即可，就是时间戳。



含义：自`1970-01-01 00:00:00`至今过去的秒或毫秒数

比如，以`秒`为单位：

- 时间戳：`3`，表示：`1970-01-01 00:00:03`
- 时间戳：`66`，表示：`1970-01-01 00:01:06`
- ...
- 时间戳：`1712893898`，表示：`2024-04-12 11:51:38`



比如，以毫秒为单位：

- 时间戳：`3000`，表示：`1970-01-01 00:00:03`
- 时间戳：`66000`，表示：`1970-01-01 00:01:06`
- ...
- 时间戳：`1712893898000`，表示：`2024-04-12 11:51:38`



> 不同的系统中，时间戳的单位不同
>
> - Java语言默认是毫秒级
> - Python语言默认是秒级
> - Linux默认是秒级



#### UTC

utc时区，世界协调时时间，也就是时区为0

![image-20240412121331513](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412121331.png)

上图红色就是UTC，我们在东八区，比UTC快8小时

即，我们早上10点，UTC凌晨2点



### ntp同步时间

安装：`yum install -y ntp`

启动：

```shell
systemctl start ntpd

# 开机自启动
systemctl enable ntpd
```

> ntp软件会自动定期联网同步时间，保证时间准确（`前提是时区准确`）



手动校准时间

```shell
ntpdate -u ntp.aliyun.com
```

`ntp.aliyun.com`是阿里云提供的时间校准服务网站





### 配置虚拟机的固定IP地址

![image-20240412143614231](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412143614.png)

如图，虚拟机默认通过DHCP从路由器获得IP地址

虚拟机用的路由器，就是我们的：`vmnet8虚拟网卡`

![image-20240412143705722](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412143705.png)

虚拟机的IP地址，并不是固定的，而是每一次都可能更换（路由器自动分配）



修改虚拟机的固定IP地址为2步骤：

1. 修改VMware的网段
2. 在Linux内修改固定IP



#### 修改VMware的网段

![image-20240412144125604](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412144125.png)

<img src="https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412144138.png" alt="image-20240412144138296" style="zoom:67%;" />

![image-20240412144239347](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412144239.png)

![image-20240412144312560](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412144312.png)

![image-20240412144326107](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412144326.png)



- 子网IP：192.168.88.0，表示VMware内部的虚拟机能够使用的IP地址范围是：`192.168.88.1~192.168.88.255`

- NAT中的网关是：192.168.88.2，表示虚拟机通过这个IP地址上网（路由器本身的地址）

  VMnet8这个网卡，默认会设置为192.168.88.1，为了避免冲突，NAT网关设置为：88.2

  如下图：

  ![image-20240412144548237](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412144548.png)





#### 在Linux系统中配置固定IP地址

在CentOS中，ip地址需要修改文件：

```shell
/etc/sysconfig/network-scripts/ifcfg-ens33
```



通过vim修改：

```shell
vim /etc/sysconfig/network-scripts/ifcfg-ens33
```

![image-20240412145348508](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412145348.png)

如上图：

- 将第四行修改为：

  ```shell
  BOOTPROTO="static"
  ```

- 在文件的最后，新增4行：

  ```shell
  IPADDR="192.168.88.130"
  NETMASK="255.255.255.0"
  GATEWAY="192.168.88.2"
  DNS1="192.168.88.2"
  ```

  > 建议复制粘贴，不要写错一个字母



#### 关闭NetworkManager服务

在CentOS系统中，有2个配置网络的服务（程序）

- network（系统的网络总服务）

- `NetworkManager`（图形化系统用来配置网络的程序），如下图

  ![image-20240412145627352](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412145627.png)

我们修改的文件：/etc/sysconfig/network-scripts/ifcfg-ens33，是`network`服务的操作文件。

需要关闭`N`etwork`M`anager，统一由network服务操纵。要不然会有冲突，导致IP地址失效。

```shell
systemctl stop NetworkManager
systemctl disable NetworkManager
```

> 注意，大小写。





### ip地址和主机名

#### ip地址

每一个联网的设备都有IP地址，用来确定网络位置。

ip地址分为：

- IPV4（用的最多）
- IPV6



IPV4的格式为：a.b.c.d，a/b/c/d均可以是`0~255`的数字。



#### 特殊IP地址

在操作系统中：

- `127.0.0.1` 代表本机（自己电脑）
- `0.0.0.0`
  - 代表本机（自己电脑）
  - 白名单或允许的IP范围（遇到的时候讲解）



#### 主机名和IP地址映射（域名解析）

IP地址不容易记忆，可以用名称去代替，名称代替IP地址需要有电话本（名字和IP的对照表）

Windows、Linux、MacOS等操作系统，都支持本地电话本，同时联网的时候也可以找网络电话本，去查询主机名（网址）和IP地址的对照关系。

流程如下：

![image-20240412160659601](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412160659.png)

从图中可以看到：

1. 首先访问本地的电话本文件（通过文件记录这个对照关系）

   1. Windows访问：`C:\windows\system32\drivers\etc\hosts`
   2. Linux访问：`/etc/hosts`
   3. MacOS访问：`/etc/hosts`

2. 如果本地电话本没有记录，则去网络电话本查找（DNS服务器），如下图：

   ![image-20240412160824634](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412160824.png)



#### 配置通过名称去访问虚拟机（不用IP地址）

在Windows系统中修改：`c:\windows\system32\drivers\etc\hosts`

添加：

```shell
192.168.88.130 centos
```



注意，修改这个文件需要管理员权限，步骤如下：

1. ![image-20240412161102693](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412161102.png)
2. ![image-20240412161131859](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412161132.png)
3. ![image-20240412161219040](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412161219.png)
4. ![image-20240412161233514](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412161233.png)
5. 如图，改好保存即可。

![image-20240412161312256](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412161312.png)

如图，配置好后，可以通过主机名(centos)访问虚拟机，不用IP地址了。





### ping命令 - 验证是否网络联通

可以通过ping命令，测试和指定的ip地址或主机名（网址）能否连接成功

语法：

```shell
ping [-c] 主机或IP
```

- `-c`，测试的次数，不指定-c则为无限次

示例：

![image-20240412162333005](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412162333.png)

![image-20240412162402867](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412162403.png)



### wget 下载文件

功能：联网下载东西

语法：

```shell
wget -b url
```

- url：下载地址
- -b，可选，进入后台下载



示例：

```shell
wget https://archive.apache.org/dist/hadoop/common/hadoop-3.3.0/hadoop-3.3.0-rat.txt
```

![image-20240412164705796](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412164706.png)

会显示进度，下载完成后，下载的文件，会出现在：`当前工作目录`



后台下载示例：

```shell
wget -b https://archive.apache.org/dist/hadoop/common/hadoop-3.3.0/hadoop-3.3.0.tar.gz
```

![image-20240412164801397](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412164801.png)

会将下载的进度，写入`当前工作目录`的`wget-log`文件，可以通过`tail -f`跟踪

![image-20240412164832557](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412164832.png)





### curl 发送网络请求

功能：向指定的网址（ip地址）发送网络请求，支持get/post等模式

语法：

```shell
curl [-O] url
```

- url：网址
- `-O`，可选，将请求转换为下载模式



发送网络请求示例：

![image-20240412165517444](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412165517.png)

下载示例：

![image-20240412165451318](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412165451.png)





### （虚拟）端口（重要）

端口是和外界进行沟通交流的窗口，分为：

- 物理端口，比如USB、HDMI、RJ45网卡等
- 虚拟端口，操作系统对外进行网络沟通的窗口



1个计算机可以有1个IP，这个IP可以定位计算机，但是不足以在网络上定位计算机内容的程序。

端口相当于计算机内部的地址，比如1个程序，占用的计算机192.168.88.131的5005端口，大白话可以是：

在192.168.88.131这个计算机的5005房间内，可以找到这个程序。



> IP地址相当于小区，端口相当于小区内的门牌号
>
> 程序就是占用一个个房间得到一个个门牌号对外沟通。

如下图：

![image-20240412171450371](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412171450.png)

计算机能够提供65535个端口，99%都是空闲的，程序只需要自己找一个空闲的用即可。



#### 端口划分

Linux系统端口大体分3类

- `1~1023`，系统内置程序或者一些超级知名的程序预留
  - 22，ssh（远程链接用）
  - 443，https网站
  - 80，http网站
  - 25，smtp（发邮件）服务
  - ...
- `1024~49151`，用户自行使用
- `49151~65535`，用户自行使用，一般用于那种临时性占用



> 只需要记住：1024以内不用即可，其余的随便。



### 嗅探指定ip的对外端口

通过`nmap`软件



安装：

```shell
yum install -y nmap
```

使用：

```shell
nmap ip地址
```

示例：

```shell
nmap 127.0.0.1
```

![image-20240412172937516](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412172937.png)



### netstat查看端口占用情况

功能：查看本机内全部的端口的使用情况

语法：

```shell
netstat -anp
```

一般配合`管道符和grep`过滤，因为结果太多



示例，查看3306端口是否有人用：

![image-20240412173505414](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412173505.png)

如上图，表示3306端口，空闲。



示例查看`sshd`程序，占用了哪个端口

![image-20240412173541660](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412173541.png)

- LISTEN 表示此端口被监听（占用）
- `0.0.0.0:22` 
  - 其中22 就是其监听的端口
  - `0.0.0.0`，表示允许任何IP地址连接





### 进程查看和关闭

程序在操作系统中运行起来，称之为一个进程或多个进程。

程序的进程会被分配进程ID



#### 查看进程信息

ps命令

语法：

```shell
ps -ef
```

查看全部进程信息



```shell
ps -ef | grep 关键字
```

通过管道符和关键字，过滤信息



输出：

![image-20240412180459186](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/12/20240412180459.png)

从左到右：

1. 第一个红框：程序启动的用户是谁
2. 第二个红框：`进程ID`
3. 第三个红框：`进程启动命令`





#### 关闭进程

语法：

```shell
kill [-9] 进程ID
```

- `-9`可选
  - 使用-9，表示强制停止，压根不理会进程的感觉，系统直接将其干掉
  - 不使用-9，表示文明停止，系统向进程发送`终止运行`的信号，由进程在保存好关键信息后，`自我了断`



> 有时候，某些进程不使用-9干不掉，所以可选择-9强制执行。





### 系统信息监控命令

#### top

top命令类似Windows的任务管理器

![image-20240413102539785](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/13/20240413102540.png)

默认每5秒刷新一次，语法：直接输入top即可，按q或ctrl + c退出



启动前选项：

![image-20240413102554837](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/13/20240413102555.png)



运行时快捷键（非-b选项启动可用）

![image-20240413102612059](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/13/20240413102612.png)



#### 查看磁盘剩余空间 df命令

语法：

```shell
df [-h]
```

- -h可以让空间单位更加容易阅读

```shell
[root@localhost ~]# df -h
文件系统        容量  已用  可用 已用% 挂载点
/dev/sda3        98G  5.3G   93G    6% /
devtmpfs        471M     0  471M    0% /dev
tmpfs           487M     0  487M    0% /dev/shm
tmpfs           487M  8.4M  478M    2% /run
tmpfs           487M     0  487M    0% /sys/fs/cgroup
/dev/sda1       297M  147M  151M   50% /boot
tmpfs            98M   12K   98M    1% /run/user/42
tmpfs            98M     0   98M    0% /run/user/0
```



#### 查看硬盘和CPU详情 iostat

语法：

```shell
iostat [-x] [n1] [n2]
```

- `-x` 显示更多列（信息）
- n1 刷新间隔
- n2 刷新次数，如果不写n2，无限刷新

![image-20240413104753182](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/13/20240413104753.png)

iostat标准输出：

- 第一行：%user 用户CPU占用率   %system 系统CPU占用率  %idle 空闲CPU百分比
- 第二行：sda为硬盘名称，KB_read/s每秒读取KB， KB_wrtn/s 每秒写入KB， KB_read总读取KB  KB_wrtn总写入KB



iostat -x 显示更多信息

![image-20240413105000982](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/13/20240413105001.png)







#### 查看网卡发送和接收数据量 sar -n

语法：

```shell
sar -n DEV n1 n2
```

- -n 表示查看网络信息
- DEV 表示统计网卡
- n1 表示刷新间隔
- n2 表示刷新次数，不给n2 无限刷新

![image-20240413105525883](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/13/20240413105526.png)

```shell
信息解读：
IFACE 本地网卡接口的名称
rxpck/s 每秒钟接受的数据包
txpck/s 每秒钟发送的数据包
rxKB/S 每秒钟接受的数据包大小，单位为KB
txKB/S 每秒钟发送的数据包大小，单位为KB
rxcmp/s 每秒钟接受的压缩数据包
txcmp/s 每秒钟发送的压缩包
rxmcst/s 每秒钟接收的多播数据包
```





### 上传、下载

通过FinalShell软件，可以完成文件在虚拟机和宿主机（自己的Windows电脑）之间相互传输数据。



上传：

![image-20240413144653038](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/13/20240413144653.png)

如图，选择上传的路径，将需要的内容，拖入红色框框（大的那个）即可。



或者通过rz命令：

```shell
rz
```

![image-20240413144734245](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/13/20240413144734.png)



如图，弹出文件选择框，选择文件即可。



下载

选择文件，然后右键：

![image-20240413144816738](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/13/20240413144817.png)

或者输入命令：

```shell
sz 文件
```

这两种方式，都会将文件下载到：Windows电脑的桌面的fsdownload文件夹。







### tar和gz格式压缩、解压



tar命令



#### 解压

解压`.tar`文件语法：

```shell
tar -xvf 被解压的包 [-C 要解压去的目的地路径]
```

- -x 解压模式
- -v 显示解压进度（列出压缩包被解压的文件）
- -f 选择被解压的文件
- `-C`可选，选择解压缩的目的地，如果不写，则是当前路径

> -C 要写在最后，因为f选项后面需要立刻跟上被解压的包的路径。所以f选项也必须在结尾，如-xvf，而不是-xfv



解压`.tar.gz`文件语法

```shell
tar -zxvf 被解压的包 [-C 要解压去的目的地路径]
```

- `-z` gzip格式进行解压，选项必须在前
- -x 解压模式
- -v 显示解压进度（列出压缩包被解压的文件）
- -f 选择被解压的文件
- `-C`可选，选择解压缩的目的地，如果不写，则是当前路径



> 注意：
>
> - Linux文件名的后缀并不一定和其压缩算法强关联，比如tar格式起名叫做.gz也是OK的
> - 一般解压缩，默认 -zxvf就OK了
> - 如果无法解压缩，就用-xvf即可



#### 压缩

创建tar压缩包语法：

```shell
tar -cvf 压缩包 参数1 参数2 ... 参数N
```

- -c 压缩模式
- -v 显示压缩过程
- -f 要`形成`的压缩包是什么
- 参数1 ~ 参数N，即将被压缩到压缩包的零散文件





创建gz压缩包语法：

```shell
tar -zcvf 压缩包 参数1 参数2 ... 参数N
```

- -z gzip格式
- -c 压缩模式
- -v 显示压缩过程
- -f 要`形成`的压缩包是什么
- 参数1 ~ 参数N，即将被压缩到压缩包的零散文件



### zip格式压缩、解压

压缩：

```shell
zip [-r] 压缩包名（路径） 参数1 参数2 ... 参数N
```

- `-r`可选，如果被添加到压缩包的有文件夹，则必须写，除非你只要一个空文件夹而已
- 压缩包名，就是要创建的压缩包在哪里，以及叫啥
- 参数1~参数N 被添加到压缩包的文件或文件夹



解压：

```shell
unzip 压缩包 [-d 位置]
```

- `-d`指定要解压到哪里，同`tar`的`-C`



### 脚本的概念

脚本也是一种编程语言或者程序代码，不同的是，脚本可以直接被执行。

脚本：一种文件，里面记录了相关的代码或者命令，可以被作为直接执行，而无需编译的过程。



举例：

sql脚本，有一个文件：test.sql，内容：

```shell
create table xxx(
	id int primary key, 
	name varchar(255)
);

insert into xxx values();
insert into xxx values();
insert into xxx values();
insert into xxx values();
insert into xxx values();
insert into xxx values();
insert into xxx values();
```



Linux Shell脚本

有一个文件叫做：test.sh，内容：

```shell
cd ~
mkdir haha
cd haha
echo "我好帅" >> 1.txt
cp 1.txt 2.txt
```

如上，就是Shell脚本，可以在Linux系统中直接运行，只需要x权限即可。



#### 编程语言的分类

- 编译型
- 解释型



编译型： 代码 -> 编译器（翻译） -> 程序 -> 执行

- C/C++/Java/Scala

解释型： 代码 -> 执行（边执行边翻译）

- Python，Perl，Linux Shell

> 解释型的编程语言的代码，其实都可以叫做脚本







## 环境变量

### 概念

操作系统在运行的时候，可以加载很多的信息作为记录。

程序在运行的时候，可以取出这些信息去用。这些称之为环境变量。

![image-20240413111844967](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/13/20240413111845.png)

如上图，系统的环境变量，相当于一个小型的数据库，可以用来做信息记录：

1. 系统内置了很多信息
2. 程序或者用户可以从里面取、也可以向里面存

> 环境变量是系统级的信息中转站。



### 环境变量的存储格式

环境变量是一种非常简单的存储形式，叫做：`Key - Value`

也就是： 

```shell
名 = 值
```

比如：

```shell
name = xiaomei
age = 11
home = beijing
...
```

- 想要得到name，通过name可以取到xiaomei
- 通过age可以取到11



### 系统内置的环境变量（信息）

以CentOS为例：

```shell
XDG_SESSION_ID=1
HOSTNAME=localhost.localdomain
SELINUX_ROLE_REQUESTED=
TERM=xterm
SHELL=/bin/bash
HISTSIZE=1000
SSH_CLIENT=192.168.88.1 2253 22
SELINUX_USE_CURRENT_RANGE=
OLDPWD=/tmp
SSH_TTY=/dev/pts/0
USER=root
LS_COLORS=rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=01;05;37;41:su=37;41:sg=30;43:ca=30;41:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.Z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.jpg=01;35:*.jpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.axv=01;35:*.anx=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=01;36:*.au=01;36:*.flac=01;36:*.mid=01;36:*.midi=01;36:*.mka=01;36:*.mp3=01;36:*.mpc=01;36:*.ogg=01;36:*.ra=01;36:*.wav=01;36:*.axa=01;36:*.oga=01;36:*.spx=01;36:*.xspf=01;36:
MAIL=/var/spool/mail/root
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/root/bin
PWD=/root
LANG=zh_CN.UTF-8
SELINUX_LEVEL_REQUESTED=
HISTCONTROL=ignoredups
SHLVL=1
HOME=/root
LOGNAME=root
XDG_DATA_DIRS=/root/.local/share/flatpak/exports/share:/var/lib/flatpak/exports/share:/usr/local/share:/usr/share
SSH_CONNECTION=192.168.88.1 2253 192.168.88.130 22
LESSOPEN=||/usr/bin/lesspipe.sh %s
XDG_RUNTIME_DIR=/run/user/0
_=/usr/bin/env
```

- USER 记录了当前登陆的用户是谁
- HOME 记录了当前登陆用户的家目录路径
- PWD 记录了当前用户的工作目录（会随着用户切换目录动态变化）
- PATH，很重要，后面说



### 如何取出环境变量和如何自行【临时】存入环境变量信息

取信息：

```shell
$变量名
```



存信息：

```shell
export 名=值
```

> 这种存储形式，只能临时生效，退出后重新登陆，就失效了。

```shell
export name=xiaomei
$name
```





### 让环境变量永久有效

环境变量如果想要永久有效，可以将环境变量记录在文件内。

根据记录的地方不同，作用范围也不同。

Linux支持：

- 系统级环境变量，`所有用户都可以用`，需要记录在：`/etc/profile`文件内

  ![image-20240413115801239](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/13/20240413115801.png)

- 用户级环境变量，`仅自己可用`，其它用户无法使用，记录在用户HOME目录内的`.bashrc`文件

  ![image-20240413120011097](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/13/20240413120011.png)

  如图，每个用户有自己的`.bashrc`，记录在里面那么仅供自己使用。





示例

在`/etc/profile`内记录：

```shell
export LOVE=xiaomei
```

记录完成后，并非立刻生效。

- 执行：`source /etc/profile` 立即生效
- 退出重新登陆，也能生效

这个LOVE变量， 任何用户都能访问

![image-20240413120207093](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/13/20240413120207.png)



示例，用itheima用户，记录自己的环境变量HEIMA_LIKE

```shell
# 编辑 /home/itheima/.bashrc
export HEIMA_LIKE=xiaoqiang
```

并非立刻生效

- 执行：`source /home/itheima/.bashrc`生效
- 或者退出重新进来生效



仅itheima用户可用这个环境变量

![image-20240413120351745](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/13/20240413120352.png)





### PATH环境变量

系统的内置环境变量有一个叫PATH的，非常特殊，功能很强大：

> 在命令行执行的任何命令（程序），都会在PATH所记录的文件夹里面挨个搜索
>
> - 如果搜索到指定的命令（程序）直接执行
> - 未找到提示未找到命令

默认PATH记录的是（以root用户为例）

```shell
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/root/bin
```

执行任何命令，都会去：

- `/usr/local/sbin`
- `/usr/local/bin`
- `/usr/sbin`
- `/usr/bin`
- `/root/bin`

这些目录搜索。

比如执行：`ls`，会在`/usr/bin`中找到，直接执行

很多命令无需提供路径，在任何地方都能执行，就是因为PATH搜索



#### 让自己写的程序也可以完成任意地方执行

编写一个文件叫做：`haha`

```shell
# 内容如下
echo "哈哈哈 我好爽"
```

- 为文件赋予可执行权限：chmod 777 haha



将haha存入下面任何一个文件夹内：

![image-20240413121821751](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/13/20240413121822.png)

就可以在任意地方，执行`haha`执行这个程序。

![image-20240413121845506](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/13/20240413121845.png)

#### PATH的搜索目录也可以修改

比如，在`/root`内，新建文件夹：`my_bin`，将这个`/root/my_bin`加入搜索目录

![image-20240413122327273](https://image-set.oss-cn-zhangjiakou.aliyuncs.com/img-out/2024/04/13/20240413122327.png)

如图，在PATH原有的内容后面，添加：`:/root/my_bin`即可将这个文件夹加入搜索目录。



注意：上面的语法是：

```shell
export PATH=$PATH:/root/bin
# 执行顺序是先执行 = 右侧
# 在执行的时候=右侧的$PATH还是正常的内容
# 在正常内容后面加上:/root/bin
# 将整体在提供给PATH（覆盖回去）
```

> 可以避免影响系统原有的PATH内容



或者直接这样也行：

```shell
export PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/root/bin:/root/my_bin
```



##### 永久生效

可以选择：

- `HOME目录的.bashrc`配置上述的修改， 用户级永久生效
- `/etc/profile`配置上述的修改， 系统级（全部用户可用）永久生效





## 扩展 - JDK环境部署

1. 上传`jdk-8u391-linux-x64.tar.gz`到`root`用户的HOME目录内

2. 执行：

   ```shell
   mkdir -p /export/server
   ```

3. 执行：

   ```shell
   tar -zxvf jdk-8u391-linux-x64.tar.gz -C /export/server/
   ```

4. 软连接

   ```shell
   cd /export/server
   ln -s jdk1.8.0_391 jdk
   ```

5. 环境变量，在`/etc/profile`最后添加

   ```shell
   export JAVA_HOME=/export/server/jdk   # 记录JAVA安装在哪
   export PATH=$PATH:$JAVA_HOME/bin
   ```

6. 删除系统自带java

   ```shell
   rm -f /usr/bin/java
   ```

7. 生效环境变量

   ```shell
   source /etc/profile
   ```

8. 验证

   ```shell
   java -version
   
   # 如下结果为正确结果
   java version "1.8.0_391"
   ```





### 扩展 - 脚本模式一次性部署

1. 上传`jdk-8u391-linux-x64.tar.gz`到`root`用户的HOME目录内

2. 准备如下脚本，赋予执行权限，执行部署

   ```shell
   # 确定pwd为root HOME
   cd ~
   
   # 创建文件夹
   mkdir -p /export/server
   
   # 解压
   tar -zxvf jdk-8u391-linux-x64.tar.gz -C /export/server/
   
   # 更换目录
   cd /export/server
   
   # 软连接
   ln -s jdk1.8.0_391 jdk
   
   # 环境变量
   echo "" >> /etc/profile   # 搞一个空行
   echo "export JAVA_HOME=/export/server/jdk" >> /etc/profile
   echo "export PATH=$PATH:$JAVA_HOME/bin" >> /etc/profile
   
   # 删除自带java
   rm -f /usr/bin/java
   
   # 生效环境变量
   source /etc/profile
   
   # 验证
   java -version
   
   # 结束
   echo "完事"
   
   ```

   









