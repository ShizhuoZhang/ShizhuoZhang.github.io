---
layout: post
title: Review of Learning-based Adaptive Control
date: 2021-10-11
tags: Academic-essay
---
<center> <font face="黑体" color=red size=6>A Research Proposal: Learning-based Adaptive Control for High Performance of Robotic Dynamic Systems</font></center>


<center> <font face="黑体" size=4>Zhang Yaokun 2021-10</font></center>


<p align="left"><font face="黑体" size=5>Abstract:</font></p> 

&emsp;&emsp;Nowadays, various robots are flooding into every corner of society. Like human cerebellum, the robot dynamics control system is crucial for its motion and manipulation. However, the tendency to more complex applications and higher performance requirements in future generation robots have been posing huge challenges to the robot dynamic control. On the one hand, traditional control methods depend heavily on accurate dynamic models of the system, which are hard to derive in complex nonlinear systems; on the other hand, changeable environment and unmanageable uncertainty in real-life systems impede the practical application of most conventional control methods, making the ability to adapt to unknown environments indispensable for any advanced control system. Fortunately, Intelligent Control technology provides promising directions, especially the neural networks (NNs) based control schemes deserve more attention in light of the superior performance of deep learning methods in many robotic fields. Therefore, an issue on how to integrate NN into control systems to achieve better adaptive control for nonlinear systems with unknown dynamics is chosen as my research topic. Aiming to this, literature review has been conducted from three aspects of dynamics modeling, online prediction and control optimization. And for the sake of practical application, the flight control of a novel tail-sitter unmanned aerial vehicle (UAV) is focused and then improvement schemes based on the existing work.

___



<p align="left"><font face="黑体" size=5>1. Background</font></p> 

With the advent of *the era of Industry 4.0*, almost all sectors such as processing and manufacturing, service, medical care, urban construction, etc. will develop and upgrade toward the direction of automation in the next few decades, and various robot systems will flood in every corner of society. Nowadays, robotics technology is advancing with each passing day, plus with the leaps in AI technology, it is not fantasy to think about truly intelligent machines, which are able to make appropriate judgments and decisions in different scenarios, just like human beings. Among many core technologies of robots, eg. environment perception, positioning and navigation, control and decision, etc., the control of robot dynamic systems is always of the most importance since any robot application is manifested in motion and manipulation to perform planned actions. 

 

**Traditional robot dynamic control** is based on classical control system theory, a mature discipline with beautiful theoretical foundations and associated numerical algorithms. Besides the extensively used PID feedback correction, a wide variety of control methods such as Robust Control, Optimum Control, Adaptive Control, Sliding Mode Control, etc. [1] have emerged and thrived over the past half century. From different perspectives of robustness, optimality and stability and in various settings of linear, nonlinear, stochastic, etc., so many powerful methods with their own advantages are undoubtedly enough to deal with most control systems. However, when conducting these methods, it is all indispensable to first obtain an accurate mathematical model to describe dynamic behaviors of system and environment, which is the only biggest drawback restricting their practical applications. Because a complex actual system inevitably has some unmanageable factors, such as strong nonlinearity, changeable environment, coupling of high-dimensional state, various uncertainty like external disturbances and system failures, etc., let alone the systems that cannot derive detailed mechanistic mathematical models. Furthermore, the tendency to more complex applications and higher performance requirements in future generation robot systems have posed more challenges to the control of the autonomous system: rather than passively rely on the robustness of the system, it’s supposed to exploit its ability of self-adaptation to the environment to achieve better trade-off between dynamic and steady performance.

 

Since the 1980s, **Intelligent Control** characterized by expert system, NN and fuzzy logic has begun to flourish, forming the corresponding new control methods [2]. These methods are essentially bionic by emulating the learning and decision patterns of organisms, and thus have less dependency on the mathematical model to some extent. Therefore, it is definitely a promising research direction, especially the NN-based control methods deserve more attention in light of the sprouting up of Deep Learning in the past decade [3]. When control meets learning, many new possibilities will be created: 

* deep NN has unique advantages in processing nonlinearity and high-dimension so that it can achieve more accurate modeling; 

* the inherently parallel architecture makes NN ideal for real-time implementations that require fast speed;

*  the online training capabilities of NN greatly facilitate the self-adaptation of controller. 

Following this line of thinking, the above-mentioned conundrums, especially for complex dynamic systems that are currently beyond the capability of existing control methods, seem to be conquerable, and then such problems in control engineering areas such as manufacturing, aerospace, biomedical, etc. will have better solutions.



It is obvious to all that **Machine Learning** (ML) has been widely applied in image and speech recognition, machine vision, natural language processing, etc., and it also shows superior performance in many robotic fields like environment perception, high-level tasks planning and control policy making [4], [5], which are relatively direct and accessible for learning. By contrast, robot dynamic control, the underlying part in the whole robot system, is more control-oriented rather than learning-oriented, because of its close contact with real-life hardware. Though more efforts might be made, this highly interdisciplinary direction (as shown in Fig.1) has been proved profitable in plenty of related work [6]–[9], making it worthwhile to develop learning-based control for robot dynamic systems. 

<img src="https://shizhuozhang.github.io/images/academic/Learning_control_filed.JPG" style="zoom:70%;" />

In summary, all I want to explore is the issue that <u>how to integrate NN into control to achieve better adaptive control for nonlinear systems with unknown dynamics</u>, especially those with rapid and unforeseen changes in the environment. And the ultimate objective is to develop learning-based adaptive control methods and achieve good real-world performance in engineering practice like UAVs or manipulators. As presented above, the biggest difficulty of this work lies on the settlement of adverse impacts caused by changes.

___



<p align="left"><font face="黑体" size=5>2. Literature Review</font></p> 

In view of the universality of the above proposed issue for any robotic control system, potential solutions can be found from three aspects of a typical control system: the control plant, environment and controller. Accordingly, literature has been investigated from the following three categories: dynamics modeling, online prediction and control optimization.

<p align="left"><font face="黑体" size=4>2.1 Dynamics modeling</font></p> 

In a sense, the control problem is basically the problem of system modeling, mainly involving two concerns of the complexity and the accuracy. The complexity refers to getting an effective kinetic or dynamic model that reflects motion characteristics of a certain system and the accuracy refers to the model error in real-life working scenarios. A model with more accuracy but less complexity is always expected, but traditional physical modeling can hardly have it both ways. Different from traditional model identification, using NN to model the input-output characteristic of a system and get a data-driven black-box model make a class of Model Learning methods [10] become mainstream.

 

On the one hand, superior to the mathematical model, NN-based dynamic models can readily deal with nonlinearity for common autonomous systems, which greatly facilitates later control design. Eg: using the multilayer perceptron NN, literature [11] identified the nonlinear dynamic model of a 5-Dof manipulator based on experimental input-output (Voltage-Joint angle) data; aiming at the dynamics of unmanned surface vehicles, literature [12] compared the simplified mathematical model and recurrent neural network (RNN) model and concluded the NN model greatly outperforms the conventional linear dynamic model; literature [13] adopted the Modular RNN framework to learn a Multi-Input-Multi-Output (MIMO) model for state prediction of quadrotors.

 

On the other hand, NN-based dynamic models are relatively simple to address the difficulty of modeling for novel components or intractable properties that are impossible to model in a mechanistic way. To cite just a few examples: literature [14] employed BP NN to substitute an unknown Stewart structure of manipulator in the system dynamic model; literature [15] borrowed multilayer NN model to replace the traditional inversion model to cope with the hysteresis property for the control of piezoelectric actuators used in nanotechnology; for the altitude control of a flapping wing micro aerial vehicle, literature [16] directly identified the relation between altitude dynamics and the actuators flapping amplitude by a type of generalized regression NN.

<p align="left"><font face="黑体" size=4>2.2 Online prediction</font></p> 

The focus of the last part is mainly on offline dynamics modeling that doesn’t involve control loops or interferences, yet it is more advisable to validate the accuracy of the established model in real working environment. Unfortunately, neither a well-derived first principle model nor a well-trained data-based model can totally guarantee its performance, because of the inevitable modeling errors and the existence of uncertainties like unmatched workspaces, parameter variations or unknown noise and disturbances. Thus real-time online model prediction is necessary, including online compensation and online identification.

 

For one thing, online compensation, or say model modification, is to estimate all the unmodeled dynamics and uncertainties that can be formulated as unknown functions. Just like mending holes on a cratered ball to make it smooth, this supplementary method has been a general way to deal with uncertainties in the NN-based adaptive control architecture [17], [18], because of NN’s excellent performance on function approximation. To cite two recent representative examples. The complex ground effects caused by interactions between multi-rotor airflow and ground is always annoying for multi-rotor drones, literature [8] blended together the nominal dynamics model and a deep NN (DNN) that offline learned these highorder interactions and finally accomplished smooth landing by online compensating disturbance aerodynamic forces. And for high-performance manipulator tracking control, literature [19] proposed a modified NN structure to model the inherent discontinuous friction and then canceled it out online.

 

For another, while offline identified models are robust to small variations, online identification is meant to locate the models in a rapidly time-varying environment. The most common way is to determine parameters of the original model structure offline derived. For NN black-box modeling, the Auto-Regressive model with eXogenous inputs (ARX) is extensively employed and the online learning algorithm is the key because of short available training time and small sets of training data given as batches. Literature [20] compared offline and online NN modeling for a UAV and showed that online models are more adaptive to changes. Literature [21] and [22] discussed different training algorithms. And in literature [23], [24], a combination way is recommended to sequentially train NN models online using the parameters from offline training. In addition, there are other ML methods like Gaussian process regression for online model approximation or local dynamics prediction [25], which are also optional directions and won't be covered here.

<p align="left"><font face="黑体" size=4>2.3 Control optimization</font></p> 

No matter how to model a system, all efforts are for the sake of control design, that is, to find an effective control law. Eg. literature [26] obtained the real-time linearized model to design General MinimumVariance optimal control law by conducting instantaneous linearization of NN models. This is a typical indirect adaptive control based on the identified model. As long as the model accuracy can be guaranteed, many conventional control methods will become beneficiaries. Model Prediction Control (MPC), an optimization control strategy for constrained multivariable system, is the first one to mention, because the performance of MPC greatly depends on the accurate process model to predict states, whereas model learning-based MPC is pushing through this limitation [27]. Eg: literature [28] adopted simple multilayer NN architecture to offline and online identify nonlinear systems and then designed an adaptive NN model predictive controller. And Literature [7] implemented an online real-time model predictive controller using learned dynamic model for tasks of robotic food-cutting, in which deep RNN was used to learn nonlinear time-varying dynamics.

 

Besides, the direct adaptive control optimally adjusts the controller. For classical controllers like PID, it lies on adjustment of controller parameters by online tunning or gain scheduling, eg. single neuron PID [29] or NN-based self-tunning[30]. For NN controller, it always combines model reference adaptive control (MRAC) strategy to adjust the weights of NN according to reference model and errors. Eg: literature [31] compared multi-layer feedforward NN and diagonal RNN as controllers in the MRAC frame and applied them to robotic manipulator and inverted pendulum. Another significant optimization control policy is Adaptive Dynamic Programming (ADP), which is virtually known as the recently popular model-based Reinforcement Learning (RL) in the computer science field. Instead of totally learning by trial-and-error, for time-sensitive dynamics control, ADP is mainly used to realize optimal output regulation or tracking control under the optimal control frame in the case of unknown system dynamics and disturbances [32]. Eg: for the attitude control of quadrotor, literature [33] combined traditional PD control with an improved ADP architecture that has critic network, action network plus a goal network for self-learning, and achieved expected tracking performance under severe disturbances.

 

Furthermore, from a more learning-oriented perspective, control design can also be considered a regression task: find the mapping from sensor to actuator that optimizes the goal cost function, which is also identified as a concept of “end-to-end control”. Compared with conventional controller, it is called machine learning control in [34], a novel control design strategy using DNN or data-driven regression techniques to discover effective control laws without the need for a system model. Eg: literature [35] built DNN to calculate robot joint torques without modeling the robot manipulator dynamics. 

<p align="left"><font face="黑体" size=4.5>2.4 Methods summary</font></p> 

To sum up, significant progress of NN has been made in control of nonlinear dynamic systems: in offline and online model learning, in predicting system dynamics, in solving control optimization. All mentioned solutions are illustrated in Fig. 2. Although there has been relatively comprehensive coverage with different emphases, a large gap between the theory and practice truly gives the alarm. Besides the notorious shortcomings of NN like lack of physical explainability, incomplete theoretical foundations, need for large amounts of data, etc., some more practical concerns deserve attention to improve the feasibility and usability of the existing schemes: 

* Evolve the NN architecture and learning technique for dynamic control systems to avoid the complex and long training process, especially online learning algorithms.
* Improve the robustness of learning-based control methods to ensure security, like adding redundant configuration design or fusing more prior physical knowledge from control into the learning process.
* Reduce onboard computational burden for learning-based control of micro automated devices.

<img src="https://shizhuozhang.github.io/images/academic/Learning_control.JPG" style="zoom:70%;" />

___

For more details, please visit [RP_zyk-UAV]([shizhuozhang/papers-YkZ (github.com)](https://github.com/shizhuozhang/papers-YkZ))to find a complete version! 

