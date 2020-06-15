---
layout:     post
title:      个人杂谈之IDEA_1
date:       0000-01-01
author:     cyq
catalog: true
tags:
    - 个人杂谈

---



一些可以进一步探索的点：

- 最近看到ACL2019的一篇论文《Compositional Questions Do Not Necessitate Multi-hop Reasoning》，这篇论文以HotpotQA数据集进行实验，想要说明即使一个单跳模型也可以处理部分组合问题。比如，有些看似是组合问题，但如果忽略问题中冗余的信息，它其实就是一个单跳问题，，或者通过确定答案的具体实体类型，就可以在非开放域的情况下（仅有部分候选文档）通过单跳计算得到答案。（个人感觉这篇论文的最大意义在于揭示目前的多跳QA数据集构造的缺陷之处，即模型可以找到一些漏洞，实际并没有学习到多跳推理能力。同时也提出了一个研究点，即检索系统如何能够检索出更好的候选文档集合，使得组合问题真正需要多跳推理才能被解决，从而促使模型真正学到多跳推理能力。）

- 对于开放域QA的相关段落检索问题：

  - 在retrieval阶段利用语义：PIQA
  - reader接触更多的文档和最小化噪声的trade-off问题：
    - Paragraph Ranker、引入ranker模块
    - 如果在训练时都是远监督的正例，那训练出来的模型容易在测试时受不相关的段落的干扰。
    - 探究选择top多少文档输入到reader阶段才最合适：Adaptive Retrieval
  - 对于需要多跳推理的问题，一次性很难从相关性的角度找全所需的段落。

- 融合多文档信息进行reader。

  目前的方法有concat、TraCRNet（使用2层Transformer架构，但最后只能用生成式结构处理抽取式QA任务）。【自己的想法：模拟人的解决过程，快速浏览多个相关段落，然后可以利用memory network记忆和问题相关的，最后进行结合多个片段得到答案。可以参考Neural speed reading via Skim-RNN、Learning to skim text、Episodic Memory Reader: Learning What to Remember for Question Answering from Streaming Data、其他关于多文档RC的论文】











结合KB和text作为外部知识进行QA：

- [ ] Neural architecture for question answering using a knowledge graph and web corpus. 2019
- [ ] More accurate question answering on freebase. 2015













##### 上课：（跟着老师的复习节奏、重点听不会的题、记笔记！！！）

- 复习知识点时认真听
- 讲题时记笔记，尤其是做的时候标记的不会的地方

##### 下课：

- 休息
- 不会的题问老师、同学（当节课上没听懂的地方或题）
- 巩固当节课老师讲的内容，把错题的思路过一遍，一次没弄完接着自习课继续看。

##### 自习时间（复习巩固、做题时标记不会的题）

- 做老师布置的作业（不要追求速度和数量，要保证质量，遇到不会的要复习该知识点）

- 巩固当天老师复习过的内容，看错题

- 不会的题问老师、同学

- 复习上周末补习班老师讲的内容、复习错题

- 预习下周末补习班老师准备讲的内容（提前看知识点、做题）

  





























