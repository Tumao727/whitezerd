---
title: 啥叫敏捷开发
date: "2020-02-15 17:47:15"
description: "敏捷开发知乎live笔记"
---

### 前言

公司开始每日站会后着实不爽了好一阵子，觉得完全是浪费时间。于是研究了一下所谓高效的敏捷开发究竟是何物ww

以下是听了程墨[相关知乎live](https://www.zhihu.com/lives/997518429552783360)后做的笔记

---


### 敏捷的历史
* agile 12 principles:

![12 principles](https://miro.medium.com/max/1200/1*5poFKYH4OuV3hJpy1W_Fww.png)

* agile values:

![agile values](https://cdn.softwaretestinghelp.com/wp-content/qa/uploads/2018/07/Agile-values.png)


### 敏捷的本质
1. 流程是用制度来弥补人的错，就像 code review 一样，来达到最大产能的价值
2. 敏捷是利于产品开发，而不是产品设计

### 敏捷的误区
* 敏捷不是乱改需求 

### 敏捷的流派
1. **scrum**
   * 实行前提：团队必须要有统一的工作协定，即团队得有纪律，且所有人都必须遵守
   * 3个角色：产品负责人（PO，对接需求），scrum master（有点类似项目经理），开发团队（UI，开发，测试）
   * 4个会议：1个sprint（类似周期的概念，最好不要短于1周，但也不要长于1月）内：
     * sprint计划会
     * 每天站会
     * 评审会议（快结束时）
     * 回顾会议（类似反思会）
   * sprint计划会：做什么，怎么做
   * 每日站会：昨天做了什么，今天打算做什么，有什么东西阻碍我（即使已经克服了也要说明）。目的是以较快的频率知道每人的进度。不要超过15分钟
   * 与 scrum 相关的其他会应该要削减
   * 相关工具：任务板，燃烧（burn down 与 burn up）图（tapd里迭代详情有进度图）
   * 如何估计工作量：story points（按任务），man hours（按人）
   * story 要有价值（用于评定优先级），要有 story points，要有描述（as xxx, I can xxx, so that xxx）
   * 角色观念改变：scrum master 关注任务吞吐量，关注持续改进，是 a leader with service in mind，推动团队进步。PO 必须建立对 scrum 其他团队的信任，保证每个 sprint 做正确的事。开发人员3-9人为好。其中最重要的因素就是人
   * PO如果要在一个sprint实行中改变需求，如果改动不大，那可以接受，如果改动很大，就中止掉这个sprint，开一个新的sprint。如果估计有误，一定要沟通，回顾会议时想想如何更好

2. **xp**
   * 结对编程，CI / CD等
   * 没有 PO，每个人都可以参与
   * 以周为单位来迭代
   * slack 任务（sth that nice to have）
   * 只适用于软件开发

3. **看板**
   * 比 scrum 更敏捷
   * 可以理解为永无止境的 sprint 的 scrum
   * 重要点是保持看板每一列不要过多
   * 给 scrum 的改善建议是可以给每一列加上限
   * 如果有看板是10列，有看板是5列，那负责5列的人要来帮助10列的，做完一个就继续新任务，对开发人员来说不是特别友好

### 多人团队 scrum 怎么运作
* sos（scrum of scrum）
* scrum 周期最好一致，开始和结束时间最好一致
* drum beat（一般4个sprint），是比 sprint 更大的一个周期
* 如果不想被依赖关系所困扰，最好的就是把依赖关系给移除掉？（技术架构层面，例如通用组件等），要能让 scrum 更好独立完成

### 总结
1. 敏捷必须能让团队持续改进
2. 需求变动时，PO 要能帮 scrum 挡第一刀