
## 一、先明确：它们适用于哪类用户

这 5 个 Agent 适合：

- 手稿已基本完成的用户
- 希望做更强投稿前压力测试的用户
- 希望模拟多 reviewer 审稿与编辑综合判断的用户
- 希望获得结构化 revision roadmap 的用户

它们不适合：

- 还在写章节初稿的用户
- 只想做简单期刊匹配和基础终审的用户
- 不希望引入较高复杂度流程的用户

如果你只想做轻量级后期处理，可改走：

- `02_Workflow/阶段15-18`

---

## 二、固定调用顺序

```text
1. Field Analysis & Review Architecture Agent
2. Multi-Perspective Review Board Agent
3. Editorial Synthesis & Decision Agent
4. Revision Planning & Comment Consolidation Agent
5. Constrained Manuscript Revision Agent

---

## 三、顺序逻辑

整条链路对应的是一个清晰的投稿前内部流程：
先判断“该怎么审”→ 再执行“多视角审稿”→ 再综合成“编辑判断”→ 再整理成“修稿计划”→ 最后执行“强约束修稿”
```

如果顺序打乱，就会出现：

- 没有 review architecture 就直接审稿，角色分配会混乱
- 没有 reviewer outputs 就直接 editorial synthesis，容易空泛
- 没有 editorial decision 就直接列 revision plan，主次不清
- 没有 revision roadmap 就直接修稿，容易改散、改乱、改越界

---

## 四、五个 Agent 的职责总览

## 1. Field Analysis & Review Architecture Agent

### 主要任务

- 判断稿件所属领域、子领域与研究类型
- 识别核心贡献与高风险点
- 设计 reviewer 视角组合
- 搭建后续审稿架构

### 输出

- `Review Architecture Package`

### 它回答的问题

- 这篇稿件应该按什么标准来审？
- 哪些位置最可能被 reviewer 攻击？
- 后续需要哪些审稿视角？

---

## 2. Multi-Perspective Review Board Agent

### 主要任务

- 按既定架构模拟多个 reviewer 视角
- 输出结构化 review comments
- 区分 major issues 与 minor issues
- 暴露不同角色下的问题分布

### 输出

- `Multi-Perspective Review Package`

### 它回答的问题

- 如果真的进入多 reviewer 评审，这篇稿件会被怎么挑问题？

---

## 3. Editorial Synthesis & Decision Agent

### 主要任务

- 汇总 reviewer outputs
- 提炼关键冲突与主矛盾
- 给出整体 editorial-style decision
- 判断当前稿件的整体风险等级

### 输出

- `Editorial Decision Package`

### 它回答的问题

- 如果像编辑一样综合各 reviewer 意见，这篇稿件当前整体处于什么状态？

---

## 4. Revision Planning & Comment Consolidation Agent

### 主要任务

- 去重、归类、排序 reviewer comments
- 区分必须修改、建议修改、无法直接修复的问题
- 形成可执行 revision roadmap

### 输出

- `Revision Roadmap`

### 它回答的问题

- 这么多意见，究竟该先改什么、后改什么、哪些能改、哪些只能降级表达？

---

## 5. Constrained Manuscript Revision Agent

### 主要任务

- 在证据边界内执行修稿
- 将 revision roadmap 转化为具体修改动作
- 保证修稿可追踪、可核查、可回退

### 输出

- `Final Revision Package`

### 它回答的问题

- 如何在不编造新事实的前提下，把这篇稿件真正改好？

---

## 五、最简版本理解

如果只记一句话：

### Agent 1

决定“怎么审”

### Agent 2

负责“具体审”

### Agent 3

负责“综合判”

### Agent 4

负责“整理改”

### Agent 5

负责“真正改”

---

## 六、调用边界

### 不建议跳过前置 Agent

除非有人类已经完成等价工作，否则不建议直接跳到后面 Agent。

### 不建议并行乱用

这 5 个 Agent 不是 5 个平行 prompt。  
它们依赖前一个 Agent 的输出。

### 不建议前置调用

在 manuscript 尚未基本完成前，不建议调用本系统。

---

## 七、一句话总结

这 5 个 Agent 不是“五个会写论文的工具”，而是一条面向接近终稿 manuscript 的**增强版内部审稿—决策—修稿工作流**。