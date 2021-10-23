---
layout: post
title: 2015&2016年项目整理与总结
date: 2021-7-03
tags: Project-Summary
---

<p align="left"><font face="黑体" size=4>关键词:</font></p> 

科创比赛，MCU开发，电子设计DIY，控制系统，robot。

just do it，脑洞大开，又菜又爱玩，重在过程。

___

<center> <font face="黑体" color=red size=4>2015.05-2015.07</font></center>

**Project:**  物块分拣搬运小车

<img src="https://shizhuozhang.github.io/images/project_summary/IMG_20150722_184713.jpg" style="zoom: 15%;" />

**Brief intro:**

该项目为2015年robocup比赛的参赛作品，比赛内容是模拟工厂不同颜色物品的分拣工作：在给定地图上将两堆物块分拣并搬运至相应的区域，要求分拣颜色无误，物块放置精准。针对该任务，设计制作了该自动作业小车，包括机械结构、硬件电路和程序设计。

**Features:**

* STM32控制器，高精度步进电机驱动，履带结构，舵机控制抓取动作，颜色传感器用于识别颜色，灰度传感器用于巡线移动。
* 针对特定场景，设计了这种特殊的抓取（勾取）装置（相对于其他的抓取结构，该结构最简单可靠，很有灵性）。
* 针对任务流程，设计了相应的程序化调度方案。

**Outcomes:**

调试过程的结果很好，但比赛时由于场地的光照问题（灰度传感器对强光照敏感），没有获得很好的名次，实属遗憾！调试视频: [2015robocup_物块分拣搬运履带小车_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1xf4y1g7Ur/)

___

<center> <font face="黑体" color=red size=4>2015.08</font></center>

**Project:**  风力摆控制系统

<center class="half">
    <img src="https://shizhuozhang.github.io/images/project_summary/Flb1.jpg" width="200"/>
    <img src="https://shizhuozhang.github.io/images/project_summary/Flb2.jpg" width="150"/>
</center>

**Brief intro:**

该项目为2015年全国大学生电子设计比赛控制题的参赛作品，比赛内容是设计制作了2自由度风力摆控制系统，实现摆的定点悬停、直线运动和绕心运动等功能。

**Features:**

* STM32控制器，十字分布的空心杯电机（小型四旋翼的转子和桨），双轴MEMS陀螺仪测摆杆的角度，LCD显示屏用于任务选择等交互，万向节和摆杆结构，激光器用于指示运动轨迹。
* 控制思路相对简单：通过简单的建模，可以得到地面的地图上的点坐标和摆杆的2维摆角之间的关系，先通过摆杆角度反馈实现定点，然后更新点坐标序列实现直线和绕心运动。
* MEMS陀螺仪模块测量摆杆角度反馈到MCU，通过PD算法调节四只空心杯电机转速达到控制风力摆的目的。

**Outcomes:**

黑龙江赛区一等奖。调试视频: [2015电赛-风力摆画圆_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1Rq4y197N4?spm_id_from=333.999.0.0)



___

<center> <font face="黑体" color=red size=4>2015.08-2015.10</font></center>

**Project:**  水下作业机器人（ROV）

<center class="half">
    <img src="https://shizhuozhang.github.io/images/project_summary/ROV.jpg" style="zoom:15%;" />
    <img src="https://shizhuozhang.github.io/images/project_summary/水下机器人水下对抗.jpg" style="zoom:15%;" />
</center>

**Brief intro:**

该项目为2015Robocup水下机器人比赛项目中EV机器人团队的参赛作品。该ROV水下机器人通过岸上控制台摇杆进行操作控制来实现机器人水下作业的功能；其中控制台和水下的机器人以脐带缆相互连接以实现电力供给和信息交换。

**Features:**

* STM32控制器，防水无刷电机和相应的驱动电路构成动力单元，摄像头配合光端机和光纤电缆传输水下视频到操作者的显示屏上；装配有机械手机构完成抓取等水下作业操作。
* 前进、后退、浮沉、转向等动作均是开环控制，依靠操作手的判断完成作业任务。
* 后期改进版本增加了深度传感器对下潜深度实现闭环控制，电机也做了简单的转速闭环；将推进器的结构布局从一字型改成X型，使运动更加高效。

**Outcomes:**

主要负责其中的电控部分，包括硬件电路和控制软件系统开发与调试。比赛获得“水下作业组冠军”和“水下对抗组一等奖”。完整的比赛视频没有找到，调试过程的记录也比较少（当时团队里没有搞宣传的人啊，要是当时短视频也如此流行，我会不会成为网红呢，哈哈哈）

**PS：**凭借团队在该领域的不断积累，[2018年](https://www.nsfc.gov.cn/csc/20340/20289/29992/index.html)和[2019年](http://news.hrbeu.edu.cn/info/1017/3423.htm)在国际水下机器人大赛中均取得冠军，虽未参赛，但依然为母校和团队感到骄傲！

___

<center> <font face="黑体" color=red size=4>2015.11-2015.12</font></center>

**Project:** 自主寻路避障小车

<img src="https://shizhuozhang.github.io/images/project_summary/智能寻路避障小车.jpg" style="zoom:25%;" />

**Brief intro:**

该项目为哈工程2015年科研立项的申报项目。该自主寻路避障小车采用相对定位原理，通过轨迹推算并在运动过程中不断避障直到到达指定位置。这种定位思想类似惯性导航系统，不过依赖传感器精度，并有累积误差。

**Features:**

* 以轮式车体结构作为载体，使用步进电机驱动，使用3组STM32单片机分别进行数据处理，运动控制以及控制信息的输入；使用2.4G无线传输模块进行信息输入控制板和数据处理板之间的信息的收发；使用单轴MEMS陀螺仪进行车体运动航向角测量；使用3组超声波模块和两套舵机伺服机构实现车身前方区域避障功能。  
* 模块化的系统设计思路：由信息输入控制板通过LCD触摸屏和无线传输模块将指定点坐标信息发送给数据处理板，数据处理板根据当前坐标信息和目的坐标信息计算出偏转角度和前进距离，并将该计算结果作为控制信息通过串口传送给运动控制板。运动控制板接受信息后偏转指定角度并前进，这一过程中陀螺仪模块通过串口以一定频率更新车体的航向角信息；超声波模块以一定频率检测障碍信息。运动控制板结合上述两种信息进行综合运动控制，并在每一次停下避障转弯时，将已前进的距离和角度通过串口发回数据处理板，用于当前位置点坐标的更新。通过数据处理板和运动控制板之间不断地进行位置信息的交流，车体自主避障前进，直至到达目的地。     

**Outcomes:**

只是为了做着玩，不过麻雀虽小，五脏俱全，算是自主避障导航（自动驾驶）的雏形吧，和现在的超声波，激光雷达，视觉避障比起来，真是小孩子的玩具，哈哈哈。调试视频: [寻路避障小车_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1zq4y197LK?spm_id_from=333.999.0.0)

___

<center> <font face="黑体" color=red size=4>2016.03-2016.08</font></center>

**Project:**  2016Robomasters机甲大师机器人大赛



<center class="half">
   <img src="https://shizhuozhang.github.io/images/project_summary/ROBOMASTER.png" style="zoom:30%;" />
   <img src="https://shizhuozhang.github.io/images/project_summary/ROBOMASTER1.jpg" style="zoom:35%;" />
</center>





**Brief intro:**

该项目为DJI主办的 2016年[RoboMaster 机甲大师赛](https://www.robomaster.com/zh-CN)全国大学生机器人大赛。比赛形式为参赛双方各自制造多台战车战车上安装有射击装置和血条系统，通过操纵战车在模拟的站地内相互较量，模拟枪战游戏。图为哈工程EV机器人战队制作的步兵车。

**Features:**

* Mecanum轮式运动底盘，可以完成原地旋转、左右平移、漂移等特殊运动形式，实现全向移动超灵活运动。
* 车体运动采用PD控制器，通过电机编码器和电流采样芯片，对直流电机做转速和电流闭环。没有模型仿真，实际效果全靠试验调参。。。每个电机设计了单独的控制驱动器。
* 双轴云台控制就是对云台电机做位置闭环，依然是无模型PD控制。Yaw轴电机与底盘之间存在位置跟随，即车体主轴始终与枪管指向一致，以保持车身上的摄像头视野开阔，有利于保证射击精度。 
* 除了常用的串口通信，系统中还广泛采用工业CAN总线通信传输控制信号。

**Outcomes:**

由于2016年该比赛还处于起步阶段（2015年首次全国范围内竞赛），学校不太重视没有经费，技术也都处于摸索阶段，现在看来做出的东西比较一般。最难的应该是机械设计，感觉准备比赛的过程中，除了焊接电路，大多时候都在拧螺丝。。。尽管产品有点low，但在当时的比赛中依然取得北方赛区一等奖，全国总决赛三等奖的成绩。当时的比赛官方视频已经找不到了，只有一些自己的录得残缺但好玩的测试视频：[2016RoboMasters步兵车测试_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1ef4y1g7Nt?spm_id_from=333.999.0.0)；[2016Robomaster比赛片段截取_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1iF411Y7zt?spm_id_from=333.999.0.0)

___

<center> <font face="黑体" color=red size=4>2016.08</font></center>

**Project:**  金属探测循迹小车

<img src="https://shizhuozhang.github.io/images/project_summary/金属检测循迹小车.jpg" style="zoom:40%;" />

**Brief intro:**

该项目为2016年全国大学生电子设计大赛控制题参赛作品。一个金属探测小车，通过电磁传感器探测地面的金属区域，实现巡线运动和硬币检测。

**Features:**

* STM32控制器，步进电机驱动，电磁传感器检测金属，舵机控制运动方向。
* 运动控制依然是PD控制，监测车身的运动方向和地面金属丝的偏移大小，构成负反馈来调节车体的方向舵偏，实现巡线（有点飞思卡尔竞速车的味道，但硬件配置真的没法比）。
* 摆来摆去的探测方式感觉很原始很搞笑，哈哈哈（因为当时没有多余的传感器了。。。）

**Outcomes:**

但是刚做完robomaster比赛，很多材料都没有提前准备，东拼西凑造出来这台小车，勉强获得赛区二等奖。调试视频: [2016电赛-金属探测小车_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1Nu411f7uJ?spm_id_from=333.999.0.0)

___

