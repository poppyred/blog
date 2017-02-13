---
layout:  post
title: 嵌入式基础概念扫盲
author:  wilmosfang
tags:   c 
categories:  c
wc:  869   692 38897 
excerpt:  二极管、三极管、电阻、电容、电感、晶振、继电器、数码管、LCD、寄存器、RAM、ROM、总线、上拉/下拉电阻、与门、或门、非门、触发器、时序图、IO口、TTL电平、位运算、进制转换、中断、中断源、中断请求、中断服务程序、中断返回、优先级、定时器、看门狗、实时时钟、串口RS232、传感器、模数转换器、数模转换器、领域知识
comments: true
---


# 前言


嵌入式是一个非常底层的应用领域

要想精深这门武功绝非一朝一夕的事情

但作为一个怀着浓烈好奇心的门外汉，还是想一窥其中精彩，虽然并无任何捷径可走，但仍然有一些路标可以指引方向，至少不会绕太多弯路，浪费掉宝贵时间

每个领域都有各具特色的基础概念和待研究的对象，将这些思维层面的关卡提前打通，可以有效扫清路上的一些障碍，让之后的道路变得更加宽阔

下面这些基础概念是通过查阅各种网络资料收集整理而来，这里进行分享，希望可以给有兴趣的筒子们节省一点时间

---

# 概要

* TOC
{:toc}

---

## 二极管

### 是什么

二极管，（英语：Diode），电子元件当中，一种具有两个电极的装置，只允许电流由单一方向流过，许多的使用是应用其整流的功能。而变容二极管（Varicap Diode）则用来当作电子式的可调电容器。大部分二极管所具备的电流方向性我们通常称之为“整流（Rectifying）”功能。二极管最普遍的功能就是只允许电流由单一方向通过（称为顺向偏压），反向时阻断 （称为逆向偏压）。因此，二极管可以想成电子版的逆止阀

### 主要特性

单向导电：电流只可以从二极管的一个方向流过

(正向导通，反向截止)

### 主要作用

整流：二极管具有单向导电性，因此可将方向交替变换的交流电转换为单一方向的脉冲直流电，完成整流的功能


限幅：由于在二极管两端加正向电压使其导通后，其正向压降基本保持不变，因此其在电路中可以作为限幅元件，将信号的幅度限制在一定的范围内


开关：由于二极管具有单向导电性，在正向电压作用下电阻很小，相当于通路，类似于开关打开状态;而在反向电压作用下电阻很大，相当于断路，类似于开关闭合状态。二极管具有的这种开关特性，使得其可以组成各种逻辑电路


续流：在开关电源的电感中或继电器的感性负载中起到续流的作用

检波：将高频信号中的低频信号检出，这一作用经常用于收音机中

触发：具有对称性的二端半导体器件，经常用于触发双向可控硅，在电路中用作过压保护

发光：也称为发光二极管(LED)，经常应用于VCD、DVD、计算器等显示器上，例如电脑硬盘的指示灯、充电器的指示灯等都是发光二极管在生活中的应用

变容：通过对其施加反向电压来改变其PN结的静电容量，从而达到变容的功能，经常于电视机高频头的频道转换和调谐电路

稳压：工作于反向击穿状态的面结型硅二极管，在稳压电路中串入限流电阻，限制稳压二极管击穿后电流值，使得其击穿状态可以一直保持下去


---


## 三极管

### 是什么

三极管，全称应为半导体三极管，也称双极型晶体管、晶体三极管，是一种控制电流的半导体器件其作用是把微弱信号放大成幅度值较大的电信号， 也用作无触点开关。晶体三极管，是半导体基本元器件之一，具有电流放大作用，是电子电路的核心元件。三极管是在一块半导体基片上制作两个相距很近的PN结，两个PN结把整块半导体分成三部分，中间部分是基区，两侧部分是发射区和集电区，排列方式有PNP和NPN两种。

### 主要特性

放大电流


### 主要作用

放大电流：将输入的微弱信号扩大β倍后输出，这便是三极管的电流放大作用

开关：三极管在饱和导通时，其CE极间电压很小，低于PN结导通电压，CE极间相当于短路，“开关”呈现开的状态;三极管在截止状态时，其CE极间电流很小，相当于断路，“开关”呈现关的状态。因此可完成开关的功能，且其开关速度极快，控制灵敏，且不产生电火花。

扩流：可扩大电流限值或电容容量。比如：将小功率可控硅与大功率三级管相结合，可以得到大功率可控硅，扩大了最大输出电流值;在长延时电路中，三极管可完成扩大电容容量的作用

代换：与某些电子元器件相结合可代换其它器件，完成相应功能。比如：两只三极管串联可代换调光台灯中的双向触发二极管;在某些电路中，三极管可以代换8V的稳压管，代换30V的稳压管等

---


## 电阻


### 是什么

电阻器（Resistor）在日常生活中一般直接称为电阻。是一个限流元件，将电阻接在电路中后，电阻器的阻值是固定的一般是两个引脚，它可限制通过它所连支路的电流大小。阻值不能改变的称为固定电阻器。阻值可变的称为电位器或可变电阻器。理想的电阻器是线性的，即通过电阻器的瞬时电流与外加瞬时电压成正比。用于分压的可变电阻器。在裸露的电阻体上，紧压着一至两个可移金属触点。触点位置确定电阻体任一端与触点间的阻值


### 主要特性

阻碍电流

### 主要作用

分压：当一电阻和另一个元器件如灯泡在电路中处于串联时，流过电阻和灯泡的电流相同，而电阻和灯泡各自的电压之和等于电阻和灯泡作为整体时两端的总电压。此时，该电阻起到分压的作用

> 经常被用于收音机和扩音机的音量调节电路、半导体管工作点的偏置电路及降压电路中，而且在USB转串口的线上面，经常使用两个电阻分压得到3.3V或2.8V的串口

分流：当一电阻和另一元器件如灯泡在电路中处于并联时，电阻两端电压和灯泡两端电压相同，而流过电阻的电流与流过灯泡的电流之和等于流过电阻和灯泡的总电流。此时，该电阻起到分流的作用

阻抗匹配：在信号的传输过程中，为了得到最大功率输出的一种工作状态，而采用一些方法使得负载阻抗与激励源内部阻抗相互适配的过程。而其方法之一就是通过改变阻抗力来实现，在这种情况下，电阻起到的是它的阻抗匹配作用

> 经常被用于传输线上

滤波：在电阻与电容串联组成的RC充放电电路中，充电放电的无限循环，将电阻R起到的作用称为滤波作用

> 经常被用于积分电路、微分电路、去耦电路、定时电路

零欧姆电阻： 零欧姆电阻可以方便布线;可以使我们在PCB上的调试更加方便;方便测耗电流;还可以起到熔丝作用;可以代替跳线、拨码开关等焊接在板子上，以防用户乱动设置;可以在高频信号下，可以充当电感或电容使用;在电路参数不确定时，也可以先用零欧姆电阻代替，确定后再更改;可以用于在最短回流路径断裂时提供较小的回流路径，减小干扰;可以有效的限制环路电流，使噪声得到抑制;可以作为温度补偿器

电位器：可变电阻器也称电位器，是阻值可以变化的电阻，在一些仪器仪表设备的模拟电路中，有时存在一些不确定的因素，这时就需要电位器的可变性来将其调节到最佳状态。还有一些设备的输出本身就是在不断变化的，这时也需要电位器来实现

特殊电阻(传感器)： 热敏电阻的阻值随温度升高而减小，应用在电路中，可以根据其阻值来判断温度，用做热传感器;光敏电阻的阻值在有光照时大大减小，在电路中可以用做光开关;压敏电阻的阻值随其两端电压大小的变化而变化，在电路中可以起到保护作用，保护电路不要因电压的起伏而受到损害。还有一种最特殊的电阻是超导体元件，它在导电的时候不会产生热量，制成计算机元件时不需要冷却系统，可以大大减少计算机的体积和能耗

> 热敏电阻可以被用作热传感器，光敏电阻可以被用作光开关


---

## 电容

### 是什么

电容器，通常简称其容纳电荷的本领为电容，用字母C表示。定义1：电容器，顾名思义，是‘装电的容器’，是一种容纳电荷的器件。英文名称：capacitor。电容器是电子设备中大量使用的电子元件之一，广泛应用于电路中的隔直通交，耦合，旁路，滤波，调谐回路， 能量转换，控制等方面。定义2：电容器，任何两个彼此绝缘且相隔很近的导体（包括导线）间都构成一个电容器。

是由两块金属电极之间夹一层绝缘电介质构成。当在两金属电极间加上电压时，电极上就会存储电荷，所以电容器是储能元件。任何两个彼此绝缘又相距很近的导体，组成一个电容器。平行板电容器由电容器的极板和电介质组成

### 主要特性

电容器的充电：两板分别带等量异种电荷，每个极板带电量的绝对值叫电容器的带电量

电容器的放电：电容器两极正负电荷通过导线中和。在放电过程中导线上有短暂的电流产生

阻止直流电流通过，允许交流电流通过

### 主要作用

滤波：通高频阻低频。电容越大低频越容易通过，电容越小高频越容易通过。具体用在滤波中,大容量电容滤低频，小容量电容滤去高频。把电压的变化转作为电流的变化，从而缓冲了输出电压。滤波就是充电，放电的过程。起到稳定输出电压的作用

旁路：产生一个交流分路，即当混有高频和低频的信号经过放大器被放大时，要求通过某一级时只允许低频信号输入到下一级，而不需要高频信号进入，则在该级的输入端加一个适当大小的接地电容，使较高频率的信号很容易通过此电容被旁路掉(这是因为电容对高频阻抗小)，而低频信号由于电容对它的阻抗较大而被输送到下一级放大

去耦：起到一个电池的作用，满足驱动电路电流的变化，避免相互间的耦合干扰

> 旁路是把输入信号中的干扰作为滤除对象，而去耦是把输出信号的干扰作为滤除对象，防止干扰信号返回电源

储能：电容收集的是电荷属于物理反应，电池属于分解化学反应，常见的电容储能有充磁机，电容电焊机等通过高电压大电流的场合，在使用电容储能时一般用大电容或者若干的小电容并联组成的电容组

耦合：又称“电场耦合” 耦合是指信号由第一级向第二级传递的过程，一般不加注明时往往是指交流耦合


谐振：利用电容和其他无源元件所产生的电压与电流之间的变化，实际是利用了电容充放电的特性。一般有电容的并联谐振和串联谐振，亦可以通过谐振电容的串并联组合成陷波器等工程应用的滤波器

---


## 电感


### 是什么

电感器(Inductor)是能够把电能转化为磁能而存储起来的元件。电感器的结构类似于变压器，但只有一个绕组。电感器具有一定的电感，它只阻碍电流的变化。如果电感器在没有电流通过的状态下，电路接通时它将试图阻碍电流流过它；如果电感器在有电流通过的状态下，电路断开时它将试图维持电流不变。电感器又称扼流器、电抗器、动态电抗器

### 主要特性

通直流，阻交流：能够把电能转化为磁能而存储起来，在电子线路中，电感线圈对交流有限流作用，它与电阻器或电容器能组成高通或低通滤波器、移相电路及谐振电路等

### 主要作用

扼流：在低频电路用来阻止低频交流电；脉动直流电到纯直流电路；它常用在整流电路输出端两个滤波电容的中间，扼流圈与电容组成∏式滤波电路。在高频电路：是防止高频电流流向低频端，在老式再生式收音机中的高频扼流圈

滤波：阻止整流后的脉动直流电流流向纯直流电路由扼流圈（为简化电路，降低成本，用纯电阻替带扼流圈）两个电容（电解电容）组成派式滤波电路。利用电容充放电作用和扼 流圈通直流电，阻挡交流电特性来完成平滑直流电而得到纯正的直流电

震荡：整流是把交流电变成直流电，那么震荡就是把直流电变成，交流电的反过程。把完成这一过程的电路叫作“震荡器”，震荡器的波形：有正旋波，锯齿波，梯形波，方波，矩形波，尖峰波，频率由几HZ-几十GHZ.在有线电，无线电领域应用非常广泛


---


## 晶振


### 是什么


晶体振荡器是指从一块石英晶体上按一定方位角切下薄片（简称为晶片），石英晶体谐振器，简称为石英晶体或晶体、晶振；而在封装内部添加IC组成振荡电路的晶体元件称为晶体振荡器。其产品一般用金属外壳封装，也有用玻璃壳、陶瓷或塑料封装的

### 主要特性

产生振荡频率

### 主要作用

时钟信号：通常一个系统共用一个晶振，便于各部分保持同步，有些通讯系统的基频和射频使用不同的晶振，而通过电子调整频率的方法保持同步


时钟频率：晶振与锁相环电路配合使用，以提供系统所需的时钟频率。如果不同子系统需要不同频率的时钟信号，可以用与同一个晶振相连的不同锁相环来提供

---

## 继电器


### 是什么

继电器（英文名称：relay）是一种电控制器件，是当输入量（激励量）的变化达到规定要求时，在电气输出电路中使被控量发生预定的阶跃变化的一种电器。它具有控制系统（又称输入回路）和被控制系统（又称输出回路）之间的互动关系。通常应用于自动化的控制电路中，它实际上是用小电流去控制大电流运作的一种“自动开关”。故在电路中起着自动调节、安全保护、转换电路等作用


### 主要特性

通过输入量的变化来控制被控量的变化

### 主要作用

扩大控制范围：可通过小电流来控制大电流的运作，以多触点继电器为例，一旦其控制信号达到规定的某一值后，便可根据触点组的形式来同时换接、断开或接通多路电路

放大：灵敏型继电器、中间继电器等多种继电器都将继电器的放大作用极好的体现出来，它们可利用一个很微小的可控制量来起到控制大功率电路的作用

综合信号：继电器的多个控制信号按规定的形式得以输入时，便在继电器内部对这些信号进行综合，并达到预定的控制效果


> 继电器与其它电器一起，还可在自动装置中组成程序控制线路以实现自动化运行，继电器还有遥控、监测等作用


---


## 数码管


### 是什么

数码管是一种半导体发光器件，其基本单元是发光二极管(LED)

### 主要特性

发光亮度高，响应时间快

### 主要作用

显示：通过控制电路让其显示相应数字

---


## LCD


### 是什么

LCD 液晶显示器是 Liquid Crystal Display 的简称，LCD 的构造是在两片平行的玻璃当中放置液态的晶体，两片玻璃中间有许多垂直和水平的细小电线，透过通电与否来控制杆状水晶分子改变方向，将光线折射出来产生画面

### 主要特性

当通电时导通，排列变得有秩序，使光线容易通过；不通电时排列混乱，阻止光线通过

轻薄短小、耗电量低、无辐射

### 主要作用

显示：液晶显示器

---

## 寄存器


### 是什么

寄存器是中央处理器内的组成部分。寄存器是有限存贮容量的高速存贮部件，它们可用来暂存指令、数据和地址。在中央处理器的控制部件中，包含的寄存器有指令寄存器(IR)和程序计数器(PC)。在中央处理器的算术及逻辑部件中，存器有累加器(ACC)

### 主要特性

位于CPU内部，数量很少

寄存器所能存储的数据不一定是8bit，有一些寄存器可以存储16bit数据，对于386/486处理器中的一些寄存器则能存储32bit数据

每个内部寄存器都有一个名字，而没有类似存储器的地址编号

### 主要作用

* 1.可将寄存器内的数据执行算术及逻辑运算
* 2.存于寄存器内的地址可用来指向内存的某个位置，即寻址
* 3.可以用来读写数据到电脑的周边设备

---

## RAM


### 是什么

随机存取存储器（random access memory，RAM）又称作“随机存储器”，是与CPU直接交换数据的内部存储器，也叫主存(内存)。它可以随时读写，而且速度很快，通常作为操作系统或其他正在运行中的程序的临时数据存储媒介。

存储单元的内容可按需随意取出或存入，且存取的速度与存储单元的位置无关的存储器。这种存储器在断电时将丢失其存储内容，故主要用于存储短时间使用的程序。 按照存储单元的工作原理，随机存储器又分为静态随机存储器（英文：Static RAM，SRAM)和动态随机存储器（英文Dynamic RAM，DRAM)

### 主要特性

随机存取：当存储器中的数据被读取或写入时，所需要的时间与这段信息所在的位置或所写入的位置无关

易失性：当电源关闭时RAM不能保留数据

对静电敏感：静电会干扰存储器内电容器的电荷，引致数据流失，甚至烧坏电路。故此触碰随机存取存储器前，应先用手触摸金属接地

访问速度：现代的随机存取存储器几乎是所有访问设备中写入和读取速度最快的，存取延迟和其他涉及机械运作的存储设备相比，也显得微不足道

需要刷新：现代的随机存取存储器依赖电容器存储数据。电容器充满电后代表1(二进制)，未充电的代表0。由于电容器或多或少有漏电的情形，若不作特别处理，数据会渐渐随时间流失。刷新是指定期读取电容器的状态，然后按照原来的状态重新为电容器充电，弥补流失了的电荷。需要刷新正好解释了随机存取存储器的易失性

### 主要作用

存取数据：内存


---

## ROM


### 是什么

ROM 是 ROM image（只读内存镜像）的简称，常用于手机定制系统玩家的圈子中。 一般手机刷机的过程，就是将只读内存镜像（ROM image）写入只读内存（ROM）的过程。 常见的 ROM image 有 img、zip 等格式，前者通常用 fastboot 程序通过数据线刷入（线刷），后者通常用 recovery 模式从 sd刷入（卡刷），故 img 镜像也被称为线刷包，zip 镜像也被称为卡刷包。 国内的定制系统开发者，经常会陷入自己的产品究竟是应该称为 OS还是 UI的争论，为了避免此类争论和表示谦虚，会自称为 ROM。很多定制系统玩家也会统一将定制系统称为 ROM


### 主要特性

一旦储存资料就无法再将之改变或删除

断电后能保证数据不会丢失

### 主要作用

通常用在不需经常变更资料的电子或电脑系统中，资料并且不会因为电源关闭而消失。例如早期的个人电脑如Apple II或IBM PC XT/AT的开机程式（作业系统）或是其他各种微电脑系统中的轫体（Firmware）


---

## 总线


### 是什么

总线（Bus）是计算机各种功能部件之间传送信息的公共通信干线，它是由导线组成的传输线束， 按照计算机所传输的信息种类，计算机的总线可以划分为数据总线、地址总线和控制总线，分别用来传输数据、数据地址和控制信号。总线是一种内部结构，它是cpu、内存、输入、输出设备传递信息的公用通道，主机的各个部件通过总线相连接，外部设备通过相应的接口电路再与总线相连接，从而形成了计算机硬件系统。在计算机系统中，各个部件之间传送信息的公共通路叫总线，微型计算机是以总线结构来连接各个功能部件的。

### 主要特性

连接各个部件的一组信号线

### 主要作用

地址总线用来表示地址码，数据总线用来表示传输的数据，控制总线表示总线上操作的命令、状态

---


## 上拉/下拉电阻


### 是什么

上拉就是将不确定的信号通过一个电阻钳位在高电平，电阻同时起限流作用。下拉同理，也是将不确定的信号通过一个电阻钳位在低电平。

上拉是对器件输入电流，下拉是输出电流；强弱只是上拉电阻的阻值不同，没有什么严格区分；对于非集电极（或漏极）开路输出型电路（如普通门电路）提供电流和电压的能力是有限的，上拉电阻的功能主要是为集电极开路输出型电路输出电流通道。

### 主要特性

稳定电平

### 主要作用

稳定电平：数字电路有三种状态，高电平、低电平、和高阻状态，有些应用场合不希望出现高阻状态，可以通过上拉电阻或下拉电阻的方式使处于稳定状态，具体视设计要求而定

上拉电阻是用来解决总线驱动能力不足时提供电流的问题的，一般是上拉增大电流，下拉电阻是用来吸收电流


---


## 与门


### 是什么

与门（英语：AND gate）又称“与电路”、逻辑“积”、逻辑“与”电路。是执行“与”运算的基本逻辑门电路。有多个输入端，一个输出端。当所有的输入同时为高电平（逻辑1）时，输出才为高电平，否则输出为低电平（逻辑0）

### 主要特性

只有当所有输入端都是高电平（逻辑“1”）时,该电路输出才是高电平（逻辑“1”）,否则输出为低电平（逻辑“0”）

### 主要作用

执行“与”运算的基本逻辑门电路


---


## 或门


### 是什么

或门（OR gate），又称或电路、逻辑和电路。如果几个条件中，只要有一个条件得到满足，某事件就会发生，这种关系叫做“或”逻辑关系。具有“或”逻辑关系的电路叫做或门。或门有多个输入端，一个输出端，只要输入中有一个为高电平时（逻辑“1”），输出就为高电平（逻辑“1”）；只有当所有的输入全为低电平（逻辑“0”）时，输出才为低电平（逻辑“0”）

### 主要特性

只要有一个或几个输入端是 “1”,或门的输出即为 “1”。而只有所有输入端为 “0”时,输出才为 “0”

### 主要作用

实现逻辑或的功能


---


## 非门


### 是什么

非门（英文：NOT gate）又称非电路、反相器、倒相器、逻辑否定电路，简称非门，，是逻辑电路的基本单元。非门有一个输入和一个输出端。当其输入端为高电平（逻辑1）时输出端为低电平（逻辑0），当其输入端为低电平时输出端为高电平。也就是说，输入端和输出端的电平状态总是反相的。非门的逻辑功能相当于逻辑代数中的非,电路功能相当于反相,这种运算亦称非运算

### 主要特性

输出始终和输入保持相反。当输入端为高电平（逻辑“1”）时，输出端为低电平（逻辑“0”）；反之，当输入端为低电平（逻辑“0”）时，输出端则为高电平（逻辑“1”）

### 主要作用

实现逻辑非的功能


---

## 触发器

### 是什么

在实际的数字系统中往往包含大量的存储单元，而且经常要求他们在同一时刻同步动作，为达到这个目的，在每个存储单元电路上引入一个时钟脉冲（CLK）作为控制信号，只有当CLK到来时电路才被“触发”而动作，并根据输入信号改变输出状态。把这种在时钟信号触发时才能动作的存储单元电路称为触发器，以区别没有时钟信号控制的锁存器


### 主要特性

触发器的接收端电平只有达到某个阈值时，才会在输出端将对应的电平输出，能保证一个脉冲内的信号稳定

### 主要作用

在实际的电路中，一般使用触发器，通过时钟脉冲进行控制，用得最多的时D触发器和J－K触发器；触发器能保证一个脉冲内的信号稳定

触发器和组合电路中的译码器、编码器、选择器、分配器等组合在一起能构成所有我们需要的电路

---

## 时序图

### 是什么

描述IC芯片操作时序的图

### 主要特性

描述IC芯片操作时序

### 主要作用

描述IC芯片操作时序


> 操作时序永远使用是任何一片IC芯片的最主要的内容。一个芯片的所有使用细节都会在它的官方器件手册上包含。所以使用一个器件事情，要充分做好的第一件事就是要把它的器件手册上有用的内容提取，掌握


---

## IO口

### 是什么

输入输出(input/output)的接口


### 主要特性

输入和输出

### 主要作用

用于输入和输出


---

## TTL电平

### 是什么

TTL（Transistor-Transistor Logic）电平信号被利用的最多是因为通常数据表示采用二进制规定，+5V等价于逻辑“1”，0V等价于逻辑“0”，这被称做TTL（晶体管-晶体管逻辑电平）信号系统，这是计算机处理器控制的设备内部各部分之间通信的标准技术


相关术语：

~~~
    TTL——Transistor-Transistor Logic
　　HTTL——High-speed TTL
　　LTTL——Low-power TTL
　　STTL——Schottky TTL
　　LSTTL——Low-power Schottky TTL
　　ASTTL——Advanced Schottky TTL
　　ALSTTL——Advanced Low-power Schottky TTL
　　FAST(F)——Fairchild Advanced schottky TTL
　　CMOS——Complementary metal-oxide-semiconductor
　　HC/HCT——High-speed CMOS Logic(HCT与TTL电平兼容)
　　AC/ACT——Advanced CMOS Logic(ACT与TTL电平兼容)（亦称ACL）
　　AHC/AHCT——Advanced High-speed CMOS Logic(AHCT与TTL电平兼容)
　　FCT——FACT扩展系列，与TTL电平兼容
　　FACT——Fairchild Advanced CMOS Technology
~~~


### 主要特性


输出高电平>2.4V,输出低电平<0.4V。在室温下，一般输出高电平是3.5V，输出低电平是0.2V。最小输入高电平和低电平：输入高电平>=2.0V，输入低电平<=0.8V，噪声容限是0.4V

### 主要作用

实现各种逻辑组合或逻辑运算



---

## 位运算

### 是什么


程序中的所有数在计算机内存中都是以二进制的形式储存的。位运算说穿了，就是直接对整数在内存中的二进制位进行操作。比如，and运算本来是一个逻辑运算符，但整数与整数之间也可以进行and运算。举个例子，6的二进制是110，11的二进制是1011，那么6 and 11的结果就是2，它是二进制对应位进行逻辑运算的结果（0表示False，1表示True，空位都当0处理）

~~~
     110
AND 1011
---------------
    0010 --> 2
~~~

主要包含有：与，或，非，异或，左移，右移，无符号右移


### 主要特性

二进制数计算


### 主要作用


操作二进制数


---

## 进制转换

### 是什么

进制转换是人们利用符号来计数的方法。进制转换由一组数码符号和两个基本因素“基数”与“位权”构成。基数是指，进位计数制中所采用的数码（数制中用来表示“量”的符号）的个数。位权是指，进位制中每一固定位置对应的单位值


>“数制”只是一套符号系统来表示指称“量”的多少。我们用“1”这个符号来表示一个这一“量”的概念。自然界的“量”是无穷的，我们不可能为每一个“量”都造一个符号，这样的系统没人记得住。所以必须用有限的符号按一定的规律进行排列组合来表示这无限的“量”。符号是有限的，这些符号按照某种规则进行排列组合的个数是无限的。十进制是10个符号的排列组合，二进制是2个符号的排列组合。
>
>在进行进制转换时有一基本原则：转换后表达的“量”的多少不能发生改变。二进制中的111个苹果和十进制中的7个苹果是一样多的

目前主要是：十进制，二进制，八进制，十六进制与它们之间的转换

### 主要特性

不同进制的基数个数不同，相同位权所代表的单位量不一样


### 主要作用

用来表示量的多少，便于计算机处理，便于人类阅读


---

## 中断

### 是什么

中断指当出现需要时，CPU暂时停止当前程序的执行转而执行处理新情况的程序和执行过程


>中断处理过程：
*（1）保护被中断进程现场。为了在中断处理结束后能够使进程准确地返回到中断点，系统必须保存当前处理机程序状态字PSW和程序计数器PC等的值。
*（2）分析中断原因，转去执行相应的中断处理程序。在多个中断请求同时发生时，处理优先级最高的中断源发出的中断请求。
*（3）恢复被中断进程的现场，CPU继续执行原来被中断的进程

### 主要特性

中断类型码或者由指令给出．或者是预先规定的

不执行INTA*(中断应答)总线周期

除单步中断外，任何内部中断都无法禁止

除单步中断外，任何内部中断的优先级都比外部中断高


### 主要作用


响应中断、处理中断与返回

实现优先权排队

高级中断源能中断低级的中断处理

---

## 中断源

### 是什么

中断源,中断是指由于某种事件的发生（硬件或者软件的），计算机暂停执行当前的程序，转而执行另一程序，以处理发生的事件，处理完毕后又返回原程序继续作业的过程。中断是处理器一种工作状态的描述。我们把引起中断的原因，或者能够发出中断请求信号的来源统称为中断源

### 主要特性

某种事件的发生，能够发出中断请求信号


### 主要作用

产生中断


---

## 中断请求

### 是什么

“紧急事件”须向处理器提出申请（发一个电脉冲信号），要求“中断”，即要求处理器先停下“自己手头的工作”先去处理“我的急件”，这一“申请”过程，称——中断请求


### 主要特性

要求“中断


### 主要作用

由于在计算机运行中，CPU是持续处于忙碌状态，而当硬件接口设备开始或结束收发信息，需要CPU处理信息运算时，便会透过IRQ对CPU送出中断请求讯号，让CPU储存正在进行的工作，然后暂停手边的工作，先行处理周边硬件提出的需求，这便是中断请求的作用


---

## 中断服务程序

### 是什么

中断服务程序,处理器处理“急件”，可理解为是一种服务，是通过执行事先编好的某个特定的程序来完成的，这种处理“急件”的程序被称为——中断服务程序

### 主要特性

CPU得放下当前工作优先处理


### 主要作用

处理紧急事务

---

## 中断返回

### 是什么

首先恢复原保留寄存器的内容和标志位的状态，这称为恢复现场，由用户编程完成。然后，再加返回指令RETI，RETI指令的功能是恢复PC值，使CPU返回断点，这称为恢复断点。恢复现场和断点后，CPU将继续执行原主程序，中断响应过程到此为止

### 主要特性

恢复现场，继续原来的工作


### 主要作用

处理中断善后，恢复之前工作


---

## 优先级

### 是什么

是计算机分时操作系统在处理多个作业程序时，决定各个作业程序接受系统资源的优先等级的参数

>各个作业在输入计算机之前，都要按一定的要求对它指定优先级。例如要按程序的性质或其长度，或是按作业的来源等，指定其优先级。然后计算机根据各作业程序优先级的高低，来决定处理各程序的先后次序。甚至在处理过程中，还能允许优先级较高的程序中断优先级较低的程序。
>
>进程是有优先级的。如果即将被运行的进程的优先级比正在运行的进程的优先级高，则系统可以强行剥夺正在运行的进程的CPU，让优先级高的进程先运行


### 主要特性

程序接受系统资源优先等级

### 主要作用

量化任务的紧要程度，协调多个作业执行的先后顺序


---

## 定时器

### 是什么

时控开关，就是设置定时关闭开启的装置

### 主要特性

定时产生触发事件

### 主要作用

可以用做精确延时处理，比如延时1ms时间

可以当做计数器，比如将这个功能IO口接到一个时钟源，可以统计有多少个脉冲信号

>接通延时型定时器，断开延时型定时器，脉冲型定时器，扩张型脉冲定时器

---

## 看门狗

### 是什么

在由单片机构成的微型计算机系统中，由于单片机的工作常常会受到来自外界电磁场的干扰，造成各种寄存器和内存的数据混乱，会导致程序指针错误，不在程序区，取出错误的程序指令等，都会陷入死循环，程序的正常运行被打断，由单片机控制的系统无法继续正常工作，会造成整个系统的陷入停滞状态，发生不可预料的后果

看门狗就是定期的查看芯片内部的情况，一旦发生错误就向芯片发出重启信号的电路。看门狗命令在程序的中断中拥有最高的优先级


### 主要特性

在系统运行以后也就启动了看门狗的计数器，看门狗就开始自动计数，如果到了一定的时间还不去清看门狗，那么看门狗计数器就会溢出从而引起看门狗中断，造成系统复位，所以在使用有看门狗的芯片时要注意清看门狗

### 主要作用

看门狗电路的应用，使单片机可以在无人状态下实现连续工作，其工作原理是:看门狗芯片和单片机的一个I/O引脚相连，该I/O引脚通过程序控制它定时地往看门狗的这个引脚上送入高电平（或低电平），这一程序语句是分散地放在单片机其他控制语句中间的，一旦单片机由于干扰造成程序跑飞后而陷入某一程序段进入死循环状态时，写看门狗引脚的程序便不能被执行，这个时候，看门狗电路就会由于得不到单片机送来的信号，便在它和单片机复位引脚相连的引脚上送出一个复位信号，使单片机发生复位。即程序从程序存储器的起始位置开始执行，这样便实现了单片机的自动复位


---

## 实时时钟

### 是什么

实时时钟的缩写是RTC(Real_Time Clock)。RTC 是集成电路，通常称为时钟芯片

实时时钟芯片是日常生活中应用最为广泛的消费类电子产品之一。它为人们提供精确的实时时间,或者为电子系统提供精确的时间基准,目前实时时钟芯片大多采用精度较高的晶体振荡器作为时钟源。有些时钟芯片为了在主电源掉电时，还可以工作，需要外加电池供电


### 主要特性

提供基准频率

### 主要作用

提供精确的实时时间,或者为电子系统提供精确的时间基准


---

## 串口RS232

### 是什么

个人计算机上的通讯接口之一，由电子工业协会(Electronic Industries Association，EIA) 所制定的异步传输标准接口。通常 RS-232 接口以9个引脚 (DB-9) 或是25个引脚 (DB-25) 的型态出现，一般个人计算机上会有两组 RS-232 接口，分别称为 COM1 和 COM2。

### 主要特性

通常 RS-232 接口以9个引脚 (DB-9) 或是25个引脚 (DB-25) 的型态出现


### 主要作用

异步串行通讯


---

## 传感器

### 是什么

传感器（英文名称：transducer/sensor）是一种检测装置，能感受到被测量的信息，并能将感受到的信息，按一定规律变换成为电信号或其他所需形式的信息输出，以满足信息的传输、处理、存储、显示、记录和控制等要求

>传感器的特点包括：微型化、数字化、智能化、多功能化、系统化、网络化。它是实现自动检测和自动控制的首要环节。传感器的存在和发展，让物体有了触觉、味觉和嗅觉等感官，让物体慢慢变得活了起来。通常根据其基本感知功能分为热敏元件、光敏元件、气敏元件、力敏元件、磁敏元件、湿敏元件、声敏元件、放射线敏感元件、色敏元件和味敏元件等十大类

### 主要特性

能感受到被测量的信息，并能将感受到的信息，按一定规律变换成为电信号或其他所需形式的信息

### 主要作用

收集信息

>人们为了从外界获取信息，必须借助于感觉器官。而单靠人们自身的感觉器官，在研究自然现象和规律以及生产活动中它们的功能就远远不够了。为适应这种情况，就需要传感器。因此可以说，传感器是人类五官的延长，又称之为电五官

---

## 模数转换器

### 是什么

模数转换器即A/D转换器，或简称ADC，通常是指一个将模拟信号转变为数字信号的电子元件。通常的模数转换器是将一个输入电压信号转换为一个输出的数字信号。由于数字信号本身不具有实际意义，仅仅表示一个相对大小。故任何一个模数转换器都需要一个参考模拟量作为转换的标准，比较常见的参考标准为最大的可转换信号大小。而输出的数字量则表示输入信号相对于参考信号的大小

### 主要特性


模拟信号转化为数字信号

### 主要作用

信号数字化


---

## 数模转换器

### 是什么

数模转换器，又称D/A转换器，简称DAC，它是把数字量转变成模拟的器件。D/A转换器基本上由4个部分组成，即权电阻网络、运算放大器、基准电源和模拟开关。模数转换器中一般都要用到数模转换器，模数转换器即A/D转换器，简称ADC，它是把连续的模拟信号转变为离散的数字信号的器件

### 主要特性

数字信号转化为模拟信号

### 主要作用

数字信号还原为模拟信号

---

## 领域知识

除了上面的常见概念和对象，还有一些内功层面的原理需要将来漫长的时间里在脑中一点点耕耘，主要包含如下四个方面

* 电路原理
* 模电
* 数电
* 单片机