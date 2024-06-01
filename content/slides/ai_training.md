+++
title = "Ai Training"
author = ["忻斌健"]
date = 2023-01-11T00:00:00+08:00
draft = false
+++

<div class="ox-hugo-toc toc">

<div class="heading">Table of Contents</div>

- [概述](#概述)

</div>
<!--endtoc-->



## 概述 {#概述}


### 智能定义 {#智能定义}


#### 生物学：行为学，（inwards)，描述性 declarative，归纳性，knowing-that {#生物学-行为学-inwards-描述性-declarative-归纳性-knowing-that}


#### 人工智能：数学，物理，（outwards)，工程化 procedural，真正理解智能 knowing-how {#人工智能-数学-物理-outwards-工程化-procedural-真正理解智能-knowing-how}

<!--list-separator-->

-  Machine in the Ghost (Gilbert Ryle 吉尔伯特·赖尔 1949): 二元论的谬误，范畴错误 （精神和躯体的区分）

    <!--list-separator-->

    -  把意识过程（智能）和物理过程割裂开

<!--list-separator-->

-  "Can Digital Computers Think?" 1951 Turing, 预期 50 年后

    <div class="NOTES">

    ‘To take an extreme case, we are not interested in the fact that the brain has the consistency of cold porridge. We don’t want to say ‘‘This machine’s quite hard, so it isn’t a brain, and so it can’t think.’’ ’

    </div>


#### 50 多年后，人工智能的工程化对图灵问题的回应 {#50-多年后-人工智能的工程化对图灵问题的回应}

<rV77BJAUYGU>


### 机器学习 {#机器学习}


#### 机器可以学习 {#机器可以学习}

<!--list-separator-->

-  神经网络（前馈，卷积，并发，变形金刚，GPT）

<!--list-separator-->

-  规模化（Scaling Law)和浮现性能（Emerging capabilities）

<!--list-separator-->

-  梯度反向传播（Gradient Back-Propagation)


#### 机器为何学习 {#机器为何学习}

<!--list-separator-->

-  Agency

    <!--list-separator-->

    -  普适的简单假设：

        <!--list-separator-->

        -  动态系统，边界，Computing world, Dynamics + Agent (System with Boundaries)

        <!--list-separator-->

        -  复杂性假设和不可约计算性


#### 机器如何学习 {#机器如何学习}

<!--list-separator-->

-  监督学习

<!--list-separator-->

-  半监督学习

<!--list-separator-->

-  自监督学习

<!--list-separator-->

-  目标函数


### 优化 -- 神经网络（深度学习） {#优化-神经网络-深度学习}


#### 网络架构 {#网络架构}

<!--list-separator-->

-  全连接层（前馈网）

<!--list-separator-->

-  卷积层（卷积网）

<!--list-separator-->

-  注意力层（变形金刚网）

<!--list-separator-->

-  稀疏拓朴层（图神经网络）


#### 优化 {#优化}

<!--list-separator-->

-  构造损失(目标函数，极大似然估计)

<!--list-separator-->

-  梯度反向传播


### 目标 {#目标}


#### 监督学习：极大似然估计 {#监督学习-极大似然估计}


#### 生成模型 Generative Model （动态随机过程，概率分布的变换） {#生成模型-generative-model-动态随机过程-概率分布的变换}

<!--list-separator-->

-  变分自编码 VAE

<!--list-separator-->

-  对抗生成网络 GAN

<!--list-separator-->

-  扩散模型 Diffusion Model 动态随机过程

<!--list-separator-->

-  主动推理（自由能量原则，动态平衡）

    -   最大化目标：基于内在模型的置信精度+熵（最小化惊奇值 surprise，不可能性的期望）
    -   最大化的自变量：内在模型的参数


#### 柯尔莫哥洛夫复杂度 {#柯尔莫哥洛夫复杂度}

<!--list-separator-->

-  知识压缩作为目标

    <!--list-separator-->

    -  Markus Hutter(Shane Legg),

    <!--list-separator-->

    -  Ilya Sutskever


### 机器学习例子 {#机器学习例子}


#### 房价预测作为线性回归 {#房价预测作为线性回归}

<!--list-separator-->

-  [Linear Regression](https://www.geeksforgeeks.org/ml-linear-regression/)

<!--list-separator-->

-  [Linear Regressin: Jupyter Notebook](https://github.com/AshishJangra27/Machine-Learning-with-Python-GFG/blob/main/Regression/1%20Linear%20Regression/Linear%20Regression%20from%20Scratch.ipynb)


### 技术进步 {#技术进步}

{{< figure src="/ox-hugo/technology.png" >}}

<div class="NOTES">

新技术的出现导致社会的进步，人工智能被誉为新时代的电力
电力有坏处：

-   触电危险
-   基础设施昂贵
-   消灭旧的行业,产生新的行业和职业

大数据：
[Jordan Tigani (ex Google Enguineering lead of BigQuery)大数据已死](https://motherduck.com/blog/big-data-is-dead/)
2011, 2017~2019,大数据并没有成为瓶颈

-   到不了大数据级别 GB
-   存储和计算正在分离
-   没有新业务，数据是线性增长的
-   人们只关心最近的数据
-   真正有大数据的公司，几乎从不查询全部数据, 2017
-   单机的计算能力大增

</div>


### 科学观念的更新 {#科学观念的更新}

{{< figure src="/ox-hugo/science.png" >}}

<div class="NOTES">

三个领域发生巨大持久和深刻的变化

-   理解原理越深刻，应用影响越大，--&gt; 革命性的应用
    -   物理学案例：核聚变，宇宙的起源，恒星的形成，\\(E=MC^2\\) ，取之不尽用之不竭的安全能源，50 年以后--&gt;5 年以后
    -   生物学案例：真核细胞生物的生化起源：光合作用，细胞呼吸作用，线粒体，外星生命研究
-   发现问题是取得进展的研究方向。
-   深刻理解会改变观念！

[比尔盖茨 AI的时代开始了](https://www.gatesnotes.com/The-Age-of-AI-Has-Begun)

-   GUI 之后的第二次革命性的技术展示 2022.中旬--&gt; 9 月

</div>
