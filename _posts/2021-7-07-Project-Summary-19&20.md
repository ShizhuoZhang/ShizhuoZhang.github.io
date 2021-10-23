---
layout: post
title: 2019&2020年项目整理与总结
date: 2021-7-07
tags: Project-Summary
---
18年9月到华科自动化学院飞导系多谱实验室团队，本想做无人机方向，继续tilt-rotor （[shizhuozhang/2018_quad-tilt-rotor-YkZ (github.com)](https://github.com/shizhuozhang/2018_quad-tilt-rotor-YkZ)）的深入研究，谁知当时课题组无人机相关的项目是预研项目不需要太多人手，于是被分配到做高速飞行器项目方向。不过终归也还是飞行控制方向，依然做出了一些新的成果。

<p align="left"><font face="黑体" size=4>年度关键词:</font></p> 

飞行控制，控制算法，控制系统仿真

___

<center> <font face="黑体" color=red size=4>2019.01</font></center>

**Project:**  基于全向移动机器人平台和Kinect的二维SLAM

<img src="https://shizhuozhang.github.io/images/project_summary/platform.png" style="zoom:30%;" />

**Brief intro:**

该项目为华中科技大学研究生控制系统综合实验选题。实验内容包括：基于ROS操作系统编写节点程序，实现通过电脑键盘按键操控移动机器人平台运动的功能；获取Kinect视觉传感器的图像信息，并通过对图像的信息的处理实现Kinect模拟激光雷达的效果；利用全向移动机器人平台和Kinect对周围环境进行二维的SLAM建图。

**Features:**

* 开发环境是Ubuntu16.04系统，Kinetic版本的ROS系统。
* 读取电脑键盘的键值，作为一个节点；键盘键值转化为移动平台的运动指令，并借助串口通信协议发送给移动平台，作为另一个节点。订阅Kinect节点发布的话题获得RGB图像和深度图像信息。
* Depthimage_to_laserscan节点通过订阅Kinect节点发布的Image和Camera_info话题，将其中的深度信息转化为激光数据后，通过发布Scan话题给出伪激光数据。
* 对比使用了Hector_slam算法和Gmapping算法这两种SLAM算法来创建地图。

**Outcomes:**

由于课程时间和硬件的问题，系统中没有加入里程计，只能使用虚拟里程计发布里程数据，使得动态的地图构建结果不太理想。但系统的基本框架还是完善，算是SLAM入门的小尝试吧。 项目资料和代码以开源到我的github: [shizhuozhang/Test_2D_SLAM-YkZ (github.com)](https://github.com/shizhuozhang/Test_2D_SLAM-YkZ)

___

<center> <font face="黑体" color=red size=4>2019.02-2019.09</font></center>

**Project:**  运载火箭推力下降故障控制重构方法研究 (Control reconfiguration methods for space launch vehicle with thrust loss fault)

<img src="https://shizhuozhang.github.io/images/project_summary/Graphical abstract_zyk.png" style="zoom:30%;" />

**Brief intro:**

该项目为实验室课题。研究执行器故障下的控制重构技术，属于容错控制领域，但研究的背景是运载火箭在助推飞行段推力下降故障，因此该控制对象应用研究资料较少。当执行器出现推力下降故障时，重新分配控制力，保证飞行稳定；故障较严重使得系统稳定裕度不足时，调整控制参数，确保飞行稳定。

**Features:**

* 建立推力下降故障下火箭的动力学模型，并定性分析推力下降故障对姿态控制系统的干扰影响。
* 根据不同严重程度的故障情况，制定基于伪逆分配方法的控制重构策略以及基于神经网络的自适应增益调度方法的控制重构策略。
* 利用控制可达性理论分析故障系统的可重构性，得到故障发生的时刻和故障的严重程度对于系统在飞行过程中能否维持可控状态的影响。
* 在VC++6.0环境下对火箭飞行过程中不同故障情形进行仿真，验证所提出的控制重构策略。

**Outcomes:**

整理系统重构控制方面的工作，以第一作者发表期刊论文一篇；控制分配的方法参与发表会议论文一篇。该项目的论文和部分代码片段在我的github上: [shizhuozhang/2019_FTC_SLV-YkZ (github.com)](https://github.com/shizhuozhang/2019_FTC_SLV-YkZ)

___



<center> <font face="黑体" color=red size=4>2019.09-2019.10</font></center>

**Project:**  飞行器控制性能评估方法和软件平台完善

<img src="https://shizhuozhang.github.io/images/project_summary/图片2.png" style="zoom:50%;" />

**Brief intro:**

该项目为实验室飞行器控制性能评估软件平台项目的一小部分。软件平台和方案都已有，仅做一些修修补补的工作，不过我还是发现了一些新的研究思路：对飞行器控制系统进行性能评估的意义，不应局限于对控制器的控制能力进行评估或者检测出控制系统的当前控制性能变差，更重要的是，能够通过对控制性能的实时评估指导控制过程。例如，对于一些性能指标驱动的自适应控制系统，可靠的在线评估结果可以作为自适应控制的设计依据，根据稳定性和跟踪性能之间的权衡来自适应调整控制器参数。此外，在故障容错控制领域，性能的好坏可以反映系统的故障情况，可以作为参考信息，用于系统的主动容错控制。要达到这一目标，目前广泛用于飞行控制系统性能评估的基于AHP法的离线评估方式是不可用的，而目前合理、具体的用于量化非线性时变系统的控制性能的性能指标还是一个开放性的课题，需要更多的研究。基于机器学习的技术应用于飞行器控制性能的在线监测与评估领域是一个很好的研究方向。

**Outcomes:**

做了大量的文献调研，写了一篇综述，但由于种种原因，没有继续做下去。该想法在下一个项目中有所体现，但显然只是低配版，之后还可以深入去做。

___

<center> <font face="黑体" color=red size=4>2019.11-2020.02</font></center>

**Project:**  稳定与跟踪综合控制性能提升的姿态控制技术研究 

<img src="https://shizhuozhang.github.io/images/project_summary/图片1.png" style="zoom:50%;" />

**Brief intro:**

该项目为实验室课题。原有工作是通过切换两套控制器来应对不确定的飞行环境，大裕度的控制器用于干扰剧烈的情况，控制目标是维持稳定；小裕度的控制器用于干扰小的情况，控制目标是准确快速地跟踪姿态指令。这就产生了一个问题：如何合理地切换两个控制器。我的工作主要就是在原有控制方案基础上设计控制器切换方案。结合之前控制性能评估项目的思路，最终开发出基于在线性能评估的增益自适应的控制方法：对飞行器姿态控制 系统性能的实时评估，自适应地调整控制器增益，实现更好的综合控制性能，使控制系统能够适应各种不确定性和外部扰动，实现高性能姿态跟踪控制。

**Features:**

*  将具有不同控制增益的线性校正控制器下的姿态控制系统的控制性能按照裕度大小或专家经验划分为不同的等级，控制器按照增益预置方法进行设计 ；
* 通过离线飞行仿真，建立飞行过程的时域状态量和相应控制性能等级的数据集，以此训练神经网络；在线飞行时，利用训练好的神经网络，对系统的控制性能等级进行实时的评估；
* 基于性能评估结果，采用自适应增益调度策略 在线 调整控制器参数 。

**Outcomes:**

该部分工作整理成发明专利，小论文写了一部分，但由于时间和疫情影响，没能继续深入，所以这部分工作也暂时搁置。项目代码和论文专利资料: [shizhuozhang/NN_Adp_GSC_HFV-YkZ (github.com)](https://github.com/shizhuozhang/NN_Adp_GSC_HFV-YkZ)

___

<center> <font face="黑体" color=red size=4>2020.02-2020.08</font></center>

**Project:** 毕业论文：针对综合控制性能提升的飞行器控制方法研究 (Research on the Aircraft Control Method for the Improvement of the Comprehensive Control Performance)

<img src="https://shizhuozhang.github.io/images/project_summary/Coordinate.png" style="zoom:40%;" />

**Brief intro:**

论文的选题是从“稳定与跟踪综合控制性能提升的姿态控制技术研究“这一课题中衍生出的一个研究方向。除了原有的基于神经网络性能评估的自适应增益调度方法，又从”系统模型辨识“和”非线性鲁棒控制“，这两个角度做了新的方案，全都是围绕控制性能展开的。由于疫情原因，原来的飞行器模型和仿真平台在实验室没法再用，只能重新开发新的仿真平台，这也是论文工作的一个重要内容。

**Features:**

* 针对通用高速飞行器模型，分析了飞行器的空气动力，并推导出飞行器的非线性六自由度运动方程组，以及相应的小偏差线性模型和仿射非线性控制模型，并搭建出完整的飞行系统数值仿真平台：[shizhuozhang/winged-cone-HFV-model-YkZ (github.com)](https://github.com/shizhuozhang/winged-cone-HFV-model-YkZ)
* 方法一：从控制性能评估的角度，设计并验证了一种基于在线性能评估的增益自适应的控制方案。首先设计了具有不同控制性能的多级线性校正控制器，通过离线仿真建立了飞行状态量和相应控制性能等级的网络训练数据集，然后利用训练好的神经网络在线监测飞行状态量，实时评估系统的控制性能，最后基于性能评估结果自适应地调整控制器增益，达到改善系统综合控制性能的目的。该方法的代码和论文资料同上一个项目介绍。

* 方法二：从系统模型辨识的角度，设计并验证了一种基于神经网络即时线性化的自适应控制方案。首先利用神经网络对飞行器动力学特性进行离线和在线的辨识，然后通过对辨识网络进行即时线性化处理获取系统当前时刻的等效线性模型，最后基于该线性模型和广义最小方差控制指标自适应地调节控制器参数，达到改善系统综合控制性能的目的。该方法的代码和论文资料: [shizhuozhang/Inst_Linr_Ctrl_HFV (github.com)](https://github.com/shizhuozhang/Inst_Linr_Ctrl_HFV)
* 方法三：从非线性鲁棒控制的角度，设计并验证了一种基于改进预设性能控制的滑模控制方案。首先在预设性能控制理论的基础上改进了传统的性能约束和误差变换方案，并提出一种性能约束重启的控制策略，然后基于虚拟控制误差设计了双环滑模控制器，使系统能够始终按照预先设定的控制性能运行。该方法的代码和论文资料:[shizhuozhang/PPFSMC_HFV-YkZ (github.com)](https://github.com/shizhuozhang/PPFSMC_HFV-YkZ)

**Outcomes:**

方法一写了专利，在受理阶段。有很多改进的想法，比如基于深度网络的评估方法，针对不同系统的基于评估的自适应方案等，有机会的话都想再继续做下去，应该会有不错的成果。

方法三整理成小论文，投稿到CJA，但被reject，后来考虑可能补充一些实际的实验结果会比较好（如四旋翼平台上的应用），但已经毕业离校，又不想继续深入做仿真的改进，所以该论文只好暂时搁置，之后读博或者工作有合适的机会再尝试吧。。。

