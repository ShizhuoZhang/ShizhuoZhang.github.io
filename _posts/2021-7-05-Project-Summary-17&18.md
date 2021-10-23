---
layout: post
title: 2017&2018年项目整理与总结
date: 2021-7-05
tags: Project-Summary
---
15-16年做了大量的比赛，之后沉寂了半年，整理相关的技术。一方面，在EV协会中做了控制部部长，平时要搞会员培训，做一些教程。另一方面，感觉之前做比赛或小项目很多时候比较凌乱，缺乏系统的规划，对于方案的制定和元件的选型等基本是有啥用啥，哪个调通用哪个，最后做出来的东西能用，但不高效，也不涉及太高深的算法，顶多就是系统架构复杂一些。所以决定少做比赛，沉淀一下技术。期间，开发了一些模块化的电子模块。后来，开始外接学校老师的实际项目赚外快。虽然赚了一些钱，但并没有太大的满足感，直到申报了“国家大学生创新创业计划”，开始做倾转旋翼无人机，就又开始了对未知的探索。。。

<p align="left"><font face="黑体" size=4>关键词:</font></p> 

控制系统综合设计，实验平台开发，赚外快

___

<center> <font face="黑体" color=red size=4>2017.01-2017.04</font></center>

**Project:**  STM32学习板及电子模块设计制作

<center class="half">
    <img src="https://shizhuozhang.github.io/images/project_summary/IMG_20170621_144514.jpg" style="zoom:10%;" />
    <img src="https://shizhuozhang.github.io/images/project_summary/ahrs.jpg" style="zoom:20%;" />
</center>



**Brief intro:**

当时痴迷嵌入式系统硬件设计，集成设计了一些电子模块。期间，开发了诸如STM32的学习板，电源系统模块，电机驱动模块，一些常用的传感器模块等，设计PCB，然后焊接，然后针对硬件开发相应的软件，乐此不疲。

**Outcomes:**

部分电路板原理图和PCB文件已开源:[shizhuozhang/PCB_design-YKz (github.com)](https://github.com/shizhuozhang/PCB_design-YKz)

___

<center> <font face="黑体" color=red size=4>2017.05-2017.08</font></center>

**Project:**  电力仿真实验平台开发

<img src="https://shizhuozhang.github.io/images/project_summary/1-16348872754551.jpg" style="zoom:15%;" />

<img src="https://shizhuozhang.github.io/images/project_summary/2-16348872993152.jpg" style="zoom:10%;" />

**Brief intro:**

该项目为自动化学院某老师的外包项目。针对电力仿真实验平台设计底层信息采集电路和处理程序，然后将其发送到PC端的上位机进行不同模式的电力仿真实验。

**Features:**

* 设计了整套集成化电路系统，实现平台面板上所以开关量和模拟量信息的采集。
* 开发实验平台软件包，包括处理采集到的信息，与PC端上位机的交互等。

**Outcomes:**

做完后发现是给本科生做实验用的，复制了十几套类似的平台，工作量超大，累死人。（不知道这套实验平台还在不在用，真害怕自己手艺不精，做的东西不稳定，导致学生做实验的时候抱怨，实验平台太垃圾。。。）

项目的部分资料已开源: [shizhuozhang/17_eletricity_simu_platform-YkZ (github.com)](https://github.com/shizhuozhang/17_eletricity_simu_platform-YkZ)

___

<center> <font face="黑体" color=red size=4>2017.09-2017.10</font></center>

**Project:**  航天科工实习和保研申请

**Outcomes:**

实习内容大部分是参观探测制导和飞行器控制领域的工程化的设计、加工过程。

10月份顺利拿到“免试推荐研究生资格”（保研）。

___

<center> <font face="黑体" color=red size=4>2017.11</font></center>

**Project:**  云台和姿态角随动系统

<center class="half">
    <img src="https://shizhuozhang.github.io/images/project_summary/1.jpg" style="zoom:15%;" />
    <img src="https://shizhuozhang.github.io/images/project_summary/2.jpg" style="zoom:15%;" />
</center>

**Brief intro:**

该项目为制导与控制系统课程的综合课设实验作品。包括两个小作品，一个是飞行姿态角模拟系统，一个是简易的2自由度恒稳云台。两个系统本质都是对2维角度的控制，也没有涉及太多的理论难点。

**Features:**

* STM32控制器，MEMS陀螺仪测角度，2自由度舵机结构。
* 均为PID算法。姿态角模拟系统要求快速和准确，云台系统要求抗干扰，所以参数的调节准则有所不同。

**Outcomes:**

这种课程要求的小项目对于当时的我来说，简直是小case，轻松拿到优秀的成绩。实验代码、报告和视频演示结果:[shizhuozhang/17-Coursework-YkZ (github.com)](https://github.com/shizhuozhang/17-Coursework-YkZ)



___

<center> <font face="黑体" color=red size=4>2017.11-2018.04</font></center>

**Project:** 小型倾转四旋翼无人机（Design and Control of a Quad-Tilt-rotor UAV Prototype）

<img src="https://shizhuozhang.github.io/images/project_summary/Tilt-rotor-bet.JPG" style="zoom:35%;" />

<img src="https://shizhuozhang.github.io/images/project_summary/tiltrotor.jpg" style="zoom:15%;" />

**Brief intro:**

 该项目资助来源于哈工程 (HEU) 自动化学院 2017年的大学生创新创业训练计划的项目，项目经费1万元左右，后该项目延续为我的本科毕业设计。启发来源于美国”鱼鹰V-22“倾转旋翼机和中国在研的“蓝鲸”四倾转旋翼机。由于经费有限，时间有限，资料有限，当时的个人能力有限，仅完成模型机的初步实现，包括：机械模型的设计制作（感谢EV刘同学的帮助），整体电控系统的设计，一个简单的地面站上位机（感谢EV燕同学的帮助），基于Free-RTOS的飞控开发，Hovering控制器设计、仿真和实现，倾转过渡模式的控制策略的仿真，进行了hovering模式下的飞行试验。后来由于飞行试验过程中的事故，导致模型部分损毁，由于没有时间和经费修复，研究就此终止，成为遗憾。

**Features:**

* 该项目里对部分元件，如电机，舵机等建模过程有详细描述，可以参考。
* 飞行控制还是常规双环PID，不过不是none-model的调参，对系统做了简单的建模，基于简化线性传函，在simulink中做了仿真，给实际的控制器参数提供参考。

* 模型机结构做的很差，倾转机构没找到特别好的方案，也没人帮忙，只能用大扭矩舵机，导致整机重量偏重，不过这种构型应该是可以进一步测试的。

* 整个电控系统是自己开发的，包括元件选型，PCB的设计焊接等，系统分成控制器板和电源板两部分，控制板（MCU是STM32F407VE）专门处理飞控程序，留有各种传感器接口，电源板集成了电流采样、强电隔离、控制电稳压等电路。无刷电机，电调，AHRS均使用淘宝模块，外加了蓝牙模块用来调试是存数据。

* 关于倾转策略，当时想了一个“非负攻角加速”的策略，先在直升机状态下倾转转子同时调整俯仰角到某一临界角度，然后再加速，使气动力逐渐发挥作用。但是没看到相关文献，自认为是奇思妙想，虽然没能通过实飞测试，但做了半实物仿真。至于现在有没有人做了相关工作，也没有再过多关注。

**Outcomes:**

这是我本科所有科创项目中最综合的一个，由于大家当时都很忙，除了必要的帮忙，我几乎一个人承担机械、电控、仿真、软件和试验测试，所以部分工作实在显得简陋。总体来说，整个项目也算尽力去做了，但最大的不足还是在机械结构的设计和制作上，这也是倾转旋翼机的最大的难点之一，现阶段感觉可能尾座式无人机（tail-sitter）可能更有希望推广应用。该项目的部分代码、资料和测试视频已开源: [shizhuozhang/2018_quad-tilt-rotor-YkZ (github.com)](https://github.com/shizhuozhang/2018_quad-tilt-rotor-YkZ)



___

<center> <font face="黑体" color=red size=4>2018.05-2018.06</font></center>

**Project:**  船舶强迫横摇实验装置，交流伺服电机控制

<img src="https://shizhuozhang.github.io/images/project_summary/experiment1.jpg" style="zoom:10%;" />

<img src="https://shizhuozhang.github.io/images/project_summary/device1.jpg" style="zoom:8%;" />

**Brief intro:**

该项目为船舶工程学院某老师的课题项目的一部分。该项目针对某型船舶强迫横摇实验设计实验装置，包括驱动重物以不同角频率横移、船舶横摇角度信息采集和处理、以及上位机和底层控制器之间的交互程序。

**Features:**

* STM32控制器控制电机、读取角度、发送信息给上位机。
* 由于系统使用220V交流电供电，故专门设计了一套电源稳压系统适配系统中动力电和控制电的不同需求。
* 使用专用的驱动器控制交流伺服电机的速度和位置，不用再做闭环控制，只需要搞懂驱动器的指令即可。
* 上位机由EV燕同学帮忙开发，可实现运动波形的设置、叠加等功能。

**Outcomes:**

项目的代码和部分资料已开源: [shizhuozhang/18_vessel_rolling_simu-YkZ (github.com)](https://github.com/shizhuozhang/18_vessel_rolling_simu-YkZ)

