+++
title = "DeepSeek调研报告及应用展望"
author = ["忻斌健"]
date = 2025-01-02T00:00:00+08:00
draft = false
+++

<div class="ox-hugo-toc toc">

<div class="heading">&#30446;&#24405;</div>

- [背景](#背景)
- [DeepSeek模型的演变](#deepseek模型的演变)
- [启示](#启示)
- [大模型应用](#大模型应用)

</div>
<!--endtoc-->



## 背景 {#背景}


### 培训的动机 {#培训的动机}

-   不特别讨论如何与\\(\mathcal{R}1\\) 交互
-   了解\\(\mathcal{R}1\\) 的来源，开发，功能特点
-   潜在的用途

<div class="NOTES">

-   交互主要是关于提示工程，
    -   DeepSeek从入门到精通(清华)，可自行参考
    -   技巧是不稳定的：依赖于提问长度变化，代理模式，推理能力的提升
-   提示工程是主要关于交互的心理模式，前提是了解对象R1
    -   R1是个什么模型？
    -   来源，模型开发的历史，如何开发，功能特点，能力

</div>


### 深度学习与神经网络 {#深度学习与神经网络}

-   基于机器学习
-   神经网络
    -   可从数据中学习，可以碎片化学习
    -   学习能力强
    -   学习容量大
-   强化学习：
    -   数据饥渴
    -   可以从复杂系统的碎片化经验中学习


### 苦涩的教训(Rich Sutton) {#苦涩的教训--rich-sutton}

> 大部分人工智能和强化学习领域的进步来源于利用大量计算资源和通用学习算法，而不是依赖领域专家手工设计的特定知识。

-   学习算法的优势(规模化能力)
    -   专门设计的系统不利于规模化部署
    -   长期来看依赖计算和数据得来的策略更加稳健和高效
    -   通用算法能随着算力增加而不断提升表现
-   自动发现的重要性
    -   让系统通过数据和计算自动发现问题的最佳解
    -   非在细节上进行过多手工调优
    -   数据驱动,解除模型学习的限制

        <div class="notes">

        -   规模化能力、
            -   短期内利用人工经验可能有帮助，
            -   专家系统：需要工程团队维护规则算法，随着系统复杂度增加（必然性）不可维护
            -   比人类预先嵌入的智慧更为持久且具适应性
        -   自动发现有利于工程化
            -   将精力放在利用大规模计算和数据上
            -   推动了深度学习及强化学习等领域的革命性进步
        -   数据驱动：高质量数据非常重要

        </div>


### \\(\mathcal{R}1\\) 的认知模型 {#mathcal-r-1-的认知模型}

{{< figure src="/ox-hugo/autoregressive.png" title="技术进步" width="600px" >}}

-   所有大语言模型是自回归模型
-   标记(token)
-   回答是通过随机抽样得到
-   低概率,高精度

<div class="notes">

-   采样和统计模型
-   提问是条件，回答是条件概率
-   温度参数: 可以调节随机性
-   fp32 单精度浮点数精度：可以表示的最小标称正数 \\(1.18\times 10^{-38}\\)
-   fp16： \\(5.96\times 10^{-8}\\)
-   fp8 1.4.3: 0.0156

</div>


## DeepSeek模型的演变 {#deepseek模型的演变}

-   开源最前沿模型(V0)
    -   网络基本架构
        -   <span class="underline">LLaMA</span> (变形金刚模型)+ <span class="underline">RMSNorm+SwiGLU</span>, <span class="underline">GQA</span>, <span class="underline">RoPE</span>
    -   训练
        -   <span class="underline">SFT,DPO,Flash Attention</span>,bf16+fp32, <span class="underline">vLLM</span>,BBPE, <span class="underline">MTP</span>,ZeRO
-   提取高质量数据集(V0~\\(\mathcal{R}1\\))
    -   高质量数据集(2T), DeepSeekMath,CoT,代码
-   **增量式创新** (V1~\\(\mathcal{R}1\_{0}\\))
    -   细颗粒力度混合专家架构 (**DeepseekMoE**): 2+64/4+128/1+256
    -   多头隐注意力 (**MLA**)
    -   **数据路由均衡** (端到端训练)
-   训练方法上的创新(\\(\mathcal{R}1\\))
    -   **纯强化学习训练**: **GRPO**

<div class="notes">

-   历史
    -   LLM-&gt;MoE-&gt;V2-&gt;V3-&gt;Math-&gt;Zero-&gt;\\(\mathcal{R}1\\)
    -   2024.01~2025.01
    -   <span class="underline">GPT4时代还没有</span>
    -   Mixtral 0/8 ➡GPT4➡DeepSeekMoE➡V3
    -   训练方法上的创新
        -   冷启动数据训练
        -   分阶段训练
        -   微调训练与后训练，附加强化学习训练
        -   蒸馏:基于QWen2.5/Llama3 (优于纯RL)，

</div>


### \\(\mathcal{R}1\\)(\\(\mathcal{R}1\_0\\))模型架构 {#mathcal-r-1--mathcal-r-1-0--模型架构}

<a id="figure--model"></a>

{{< figure src="/ox-hugo/deepseek_v3.png" caption="<span class=\"figure-number\">&#22270;1&nbsp; </span>\\(\mathcal{R}1\_0\\) 网络模型" width="600pix" >}}

<a id="figure--RL elicits reasoning!"></a>

{{< figure src="/ox-hugo/reasoning_increase.png" caption="<span class=\"figure-number\">&#22270;2&nbsp; </span>强化学习训练引发推理能力提升" title="tree" width="600pix" >}}


### \\(\mathcal{R}1\\) 训练流水 {#mathcal-r-1-训练流水}

<a id="figure--position"></a>

{{< figure src="/ox-hugo/the-real-deepseek-r1-schematic-v0.gif" title="tree" width="1000pix" >}}


### 主要特点 {#主要特点}

-   开源大模型(权重开放，方法开放，非常宽松的MIT许可)
    -   容易复制，已经被多次复现(Open\\(\mathcal{R}1\\))改进(S1)
    -   非视觉多模态模型→ DreamCraft3D, Janus Pro (79.2%@MMBench, 0.8@t2i)
-   较强的推理能力
    -   来自强化学习训练和推理数据训练样本
    -   大模型的推理能力可蒸馏到小模型
-   高效(较低成本)
    -   架构：训练和推理稀疏化(MoE) + 内嵌瓶颈层(MLA) + (MTP）
    -   硬件驱动: 匹配通信约束跨节点数据流,低精度浮点数计算

<div class="notes">

-   国内其他大模型公司:科大讯飞，腾讯云，百度，阿里千问,华为盘古：模型和应用？
-   24年底，六小龙大模型公司的减法： 商汤日日新,零一万物,百川,智谱GLM,月之暗面Kimi,MiniMax海螺AI？
-   Demis Hassabis: 过度炒作，没有科学上的进步，已知技术，基于谷歌，Meta和开源的成果）

</div>


## 启示 {#启示}

-   开发模式
    -   采用通用基础大模型
    -   SoTA+递增式改进+实验验证
-   提高模型性能的方法
    -   模型和驱动架构
    -   高质量数据集
    -   推理能力可以蒸馏到较小模型
-   幻方量化:量化基金以AI为核心的量化基金


### 幻方量化(High-Flyer)发展 {#幻方量化--high-flyer--发展}

-   2020 2亿人民币超算一代
    -   参照美国“文艺复兴科技”
-   2021 10亿人民币超算二代(10000 A100)
    -   旗下100支基金产品亏损超10%
    -   总体回报率20%~50%
-   2022 建议客户回撤资金
-   2023 4月成立Deepseek,专注通用人工智能研究
-   2024 1月DeepSeekLLM,DeepSeekMoE开源
-   2024 2月国家打击量化基金扰乱股市
    -   业绩落后综合指数4%
-   2024 10月因轧空关闭中性基金产品
-   2025 1月Deepseek \\(\mathcal{R}1\\) 开源


## 大模型应用 {#大模型应用}

-   汽车行业端到端大模型
    -   车机应用:LLM,对话，感知
    -   感知大模型:车道,行人,障碍物识别
    -   车辆控制(VLA,生成式模型):世界大模型
-   机器人行业
    -   规模化控制模型(VLA,生成式扩散模型,块变形金刚模型)
    -   机械臂操作:模仿学习
    -   双足/四足机器人行走控制:强化学习


### 大模型的应用模式 {#大模型的应用模式}

<a id="figure--model deployment"></a>

{{< figure src="/ox-hugo/llm_mentalmodel.jpg" width="800pix" >}}

-   人机接口(HMI,前端)
-   大语言模型(\\(\mathcal{R}1\\),后端)
-   应用域数据源(问题适配,中台)

<div class="NOTES">

<https://medium.com/towards-data-science/building-ai-products-with-a-holistic-mental-model-33f8729e3ad9>

</div>


### \\(\mathcal{R}1\\) 推理模型和制造与工业自动化: {#mathcal-r-1-推理模型和制造与工业自动化}

> 添加图像编解码网络

-   工业自动化
    -   可用于自动化装配线:可以帮助机器人准确地执行装配任务
    -   质量检测:减少错误和不合格品
-   质量控制
    -   通过视觉系实时检测产品缺陷
    -   建立故障模型预测
    -   预测性维护(匹配时间序列数据)
-   移动机器人
    -   复杂任务调度
    -   路径规划


### 数据处理 {#数据处理}

-   OA助手
    -   办公文本生成
    -   表格数据分析和报告生成
-   编程助手
    -   专用领域编程模型
    -   架构辅助设计
    -   文档和测试自动化


### 机器人 {#机器人}

> 结合\\(\mathcal{R}1\\) 微调开源VLA基础模型

-   X1
    -   敏捷步态控制
    -   复杂机械臂操作
-   焊接机器人
    -   复杂路径规划与控制
    -   零示教自适应多任务控制
-   移动机器人规划
    -   路径规划


### 开发工作 {#开发工作}

-   服务部署
    -   企业内网后端服务
    -   前端界面开发和集成
-   提示工程
    -   系统化整理提示模板
    -   监控，维护和更新
    -   使用培训


#### 不同应用域的适配开发模式 {#不同应用域的适配开发模式}

-   数据
    -   收集，清洗，
    -   数据集维护和更新
-   模型微调
    -   应用域滚动训练
    -   超参调试
    -   架构调整
    -   训练调度测试
