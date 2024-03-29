﻿<!--
  Copyright (c) 2017, Xin YUAN, courses of Zhejiang University
  All rights reserved.

  This program is free software; you can redistribute it and/or
  modify it under the terms of the 2-Clause BSD License.

  Author contact information:
    yxxinyuan@zju.edu.cn
-->

# 人工智能

## 前言

媒体在2017年推出了一张图，帮助大家看懂人工智能的知识体系[参见[一张图][AITU-20170801]]。
这里就不再贴出这些图了。

人工智能的知识体系，总体上可分为符号主义、联结主义和行为主义三大类[参见[三大主义][ZY-20161026]]。

## 符号主义

符号主义(symbolicism)，又称为逻辑主义(logicism)、心理学派(psychologism)或计算机学派(computerism)，
其原理主要为物理符号系统(即符号操作系统)假设和有限合理性原理。

符号主义认为人工智能源于数理逻辑。数理逻辑从19世纪末起得以迅速发展，20世纪30年代开始用于描述智能行为。
计算机出现后，又在计算机上实现了逻辑演绎系统。其有代表性的成果为启发式程序LT逻辑理论家，
证明了38条数学定理，表明可以应用计算机研究人的思维，模拟人类智能活动。
正是这些符号主义者，早在1956年首先采用“人工智能”这个术语。
后来又发展了启发式算法->专家系统->知识工程理论与技术，并在20世纪80年代取得很大发展。
符号主义曾长期一枝独秀，为人工智能的发展作出重要贡献，尤其是专家系统的成功开发与应用，
为人工智能走向工程应用和实现理论联系实际具有特别重要的意义。
在人工智能的其他学派出现之后，符号主义仍然是人工智能的主流派别。
这个学派的代表任务有纽厄尔(Newell)、西蒙(Simon)和尼尔逊(Nilsson)等。

符号主义本质上是模拟人类的认知思维模式，用抽象的符号表达事物的属性和行为，建立一系列的推理规则。
实际上，这种推理规则也是一种函数，自变量和应变量都是离散的数值。

符号主义的缺陷是[参见[符号主义][FH-20170717]]：

1. 哥德尔已经证明了公理化方法具有本质的局限性。命题和推理规则的相容性，完备性都难以同时保证。
在实际的应用中，制定的推理规则无法覆盖要解决问题的全部情况，失去使用价值。
1. 对于机器证明而言，无法说明是“证明”了 定理，还是“检验”了定理。
1. 问题必须首先代数化，这并非智能的必要步骤。此外还有算法复杂度P和NP的问题。
1. 无法提出新概念，新方法。

最新较热的知识图谱是符号主义和连接主义交叉的产物。当然，它也没能彻底解决符号主义的缺陷。

## 联结主义

连接主义(connectionism)，又称为仿生学派(bionicsism)或生理学派(physiologism)，
其主要原理为神经网络及神经网络间的连接机制与学习算法。

连接主义认为人工智能源于仿生学，特别是对人脑模型的研究。
它的代表性成果是1943年由生理学家麦卡洛克(McCulloch)和数理逻辑学家皮茨(Pitts)创立的脑模型，
即MP模型，开创了用电子装置模仿人脑结构和功能的新途径。
它从神经元开始进而研究神经网络模型和脑模型，开辟了人工智能的又一发展道路。
20世纪60`~`70年代，连接主义，尤其是对以感知机(perceptron)为代表的脑模型的研究出现过热潮，
由于受到当时的理论模型、生物原型和技术条件的限制，脑模型研究在20世纪70年代后期至80年代初期落入低潮。
直到Hopfield教授在1982年和1984年发表两篇重要论文，提出用硬件模拟神经网络以后，
连接主义才又重新抬头。1986年，鲁梅尔哈特(Rumelhart)等人提出多层网络中的反向传播算法(BP)算法。
此后，连接主义势头大振，从模型到算法，从理论分析到工程实现，为神经网络计算机走向市场打下基础。
现在，对人工神经网络(ANN)的研究热情仍然较高，但研究成果没有像预想的那样好。

连接主义技术在历史上经历了三起三落，当前正处于一个新的高潮上[参见[连接主义][LJ-20170628]]。

本质上，连接主义使用网络连接的方式来构造需要求解的函数的结构形式。
其发展过程中，引入的统计理论是机器学习的基石。
深度学习还是机器学习的一种，因用于围棋AI阿法狗，其表现超过人类而成为新的网红技术。
无论哪种连接主义的技术，最终都是在求解一个泛函最优化问题以获得一个函数，
该函数用来解决分类问题、回归问题，决策问题等。
泛函的建模可能是概率最大化，也可能是误差最小，能量最小等等，
而泛函的形式，可能是线性的，也可能是非线性的，可能是凸的，也可能是非凸的。

对于机器学习，更深入的讨论请阅读[机器学习](ml.md)。

连接主义的缺陷是：

1. 统计的引入，使得其对训练样本的要求是服从独立同分布假设，这个条件较强。
1. 网络的结构形式没有理论来帮助设计。
1. 最优化问题建模时，往往通过正则化方法提升维度，使其成为凸函数从而保证能得到全局最优解。
但这新问题的解和原问题的解差别是什么，正则项是不是有合理解释，最终的解能不能满足工程上的要求，
都是疑问。
1. 连接主义也只是拟合函数，并不能得到新概念，新方法。

## 行为主义

行为主义(actionism)，又称为进化主义(evolutionism)或控制论学派(cyberneticsism)，
其原理为控制论及感知-动作型控制系统。

行为主义认为人工智能源于控制论。控制论思想早在20世纪40\~50年代就成为时代思潮的重要部分，
影响了早期的人工智能工作者。
维纳(Wiener)和麦克洛克(McCulloch)等人提出的控制论和自组织系统
以及钱学森等人提出的工程控制论和生物控制论，影响了许多领域。
控制论把神经系统的工作原理与信息理论、控制理论、逻辑以及计算机联系起来。
早期的研究工作重点是模拟人在控制过程中的智能行为和作用，
如对自寻优、自适应、自镇定、自组织和自学习等控制论系统的研究，并进行“控制论动物”的研制。
到20世纪60\~70年代，上述这些控制论系统的研究取得一定进展，播下智能控制和智能机器人的种子，
并在20世纪80年代诞生了智能控制和智能机器人系统。
行为主义是20世纪末才以人工智能新学派的面孔出现的，引起许多人的兴趣。
这一学派的代表作者首推布鲁克斯(Brooks)的六足行走机器人，它被看作是新一代的“控制论动物”，
是一个基于感知-动作模式模拟昆虫行为的控制系统。

当前比较热的强化学习就是一种行为主义的方法。
在现有发表的关于强化学习的论文中，都有为了达到良好效果而使用的trick。

本质上，行为主义就是一个闭环反馈的控制系统[参见[行为主义][XW-20170628]]。在实际的工程实践中，
只有两种工业界开发的方法，即PID控制和预测控制得到了广泛的应用，分别的占比是85%和14%。
还有1%都是其他名气很差的控制。控制系统还是在求解一个控制函数，可以和物理中的运动方程类比，
隐含的数学模型依然是在求解泛函最优化问题，可以和物理中的体系能量最小类比。和连接主义不同的是，
这个优化目标是可能在不断变化的，因此就需要在很短时间内算出控制决策。

行为主义也有它自己的缺陷：

1. 在复杂情况下，控制参数的确定靠经验，并没有可靠的理论来指导。
1. 整个系统的稳定性比较难分析，可能会陷入动力学系统常见的混沌。
1. 高自由度和柔性的运动依然没有可靠的理论来仿真。
1. 机器人规则制定和符号主义的问题一样，无法覆盖所有复杂情况。自动驾驶的困境就是来源于此。

## 应用分析

人工智能在现实中的确也获得了不少领域的应用，但其应用范围比较窄，[这里](app.md)是具体的分析。

此外，在实际应用中出现了将三种主义相互结合而产生的一系列方法，如将规则引入机器学习。
这类方法实际上都是用其他的函数模型来调制主要用来应用的函数模型，能在具体领域取得一定的效果，
但并没有理论上的突破。

[AITU-20170801]: http://www.sohu.com/a/161327614_236505 "一张图"
[ZY-20161026]: https://blog.csdn.net/u011531010/article/details/52935348 "三大主义"
[FH-20170717]: http://www.sohu.com/a/157710445_466950 "符号主义"
[LJ-20170628]: http://blog.sina.com/s/blog_a30c17f30102x63x.html "连接主义"
[XW-20170628]: http://blog.sina.com.cn/s/blog_a30c17f30102x640.html "行为主义"
