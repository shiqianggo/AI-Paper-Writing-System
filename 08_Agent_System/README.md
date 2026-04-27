# 08_Agent_System

## 目录定位

`08_Agent_System/` 是本系统的**增强版投稿前内部评审与修稿子系统**。  
它服务于已经基本完成的 manuscript，用于模拟“领域分析 → 多角色审稿 → 编辑综合判断 → 修稿规划 → 强约束修稿”的完整内部流程。

它不是正文生成系统，也不是基础质控清单。  
它的定位是：

- 对接近终稿的稿件做更高强度、更系统化的投稿前压力测试
- 用多角色、多阶段、中间产物可传递的方式，模拟更接近真实投稿环境的 review / decision / revision 流程

---

## 它与 `02_Workflow/阶段15-18` 的关系

`08_Agent_System/` **不是** `阶段15-18` 的简单下游，也**不是**它们的附属模块。  
二者更适合被理解为两条**平行的后期路线**：

### 路线 1：非智能体后期路线
适合希望低复杂度、手动控制的用户：

- `阶段15-期刊推荐与匹配`
- `阶段16-目标期刊定向润色`
- `阶段17-整稿终稿润色与连贯性修复`
- `阶段18-投稿前终审`

这条路线适合：
- 不使用智能体的用户
- 只需要简单期刊匹配、简单审稿、基础终审的用户

### 路线 2：智能体增强后期路线
适合希望进行更完整内部评审模拟的用户：

- `08_Agent_System/`

这条路线适合：
- 希望模拟编辑部与 reviewer 系统
- 希望系统整合 comments
- 希望得到 revision roadmap
- 希望在证据边界内做强约束修稿

因此，二者关系更准确的说法是：

- `阶段15-18` = 轻量版、非智能体版后期路径
- `08_Agent_System/` = 增强版、智能体版后期路径

---

## 使用前提

建议仅在以下条件基本满足后使用本目录：

- manuscript 已基本完整
- Results、Introduction、Discussion、Abstract 已形成较稳定文本
- Figures、legends、Methods、Supplementary materials 已相对固定
- 已完成至少一轮基础质控
- 已完成基础文献、数字、事实核查
- 已进入投稿前优化阶段

以下情况不建议进入本目录：

- 仍在章节初稿生成阶段
- 研究事实材料尚未固定
- 结果结构还在频繁变动
- 仍有大量文献、数字、统计未核查项
- 全文还没有基本收束

---

## 本目录解决什么问题

本目录重点解决以下问题：

- 这篇稿件应按什么标准来审
- 它在不同 reviewer 视角下会暴露哪些问题
- 多 reviewer comments 如何综合成更像编辑决策的判断
- 分散评论如何变成可执行的 revision roadmap
- 如何在不越过证据边界的前提下完成最后一轮修稿

因此，本目录关注的不是“再生成一篇稿”，而是：

- 审稿架构设计
- 多角色评审
- 编辑综合判断
- 修稿规划
- 强约束修稿执行

---

## 固定调用顺序

本目录中的 5 个 Agent 构成一条固定 pipeline，而不是 5 个平行工具：

```text
1. Field Analysis & Review Architecture Agent
2. Multi-Perspective Review Board Agent
3. Editorial Synthesis & Decision Agent
4. Revision Planning & Comment Consolidation Agent
5. Constrained Manuscript Revision AgentAgent
```

其逻辑是：
```
先判断“该怎么审”→ 再执行“多视角审稿”→ 再做“编辑综合判断”→ 再整理成“修稿路线图”→ 最后执行“强约束修稿”
```

---

## 各 Agent 的角色边界

### 1. Field Analysis & Review Architecture Agent

负责：

- 领域定位
- 稿件类型判断
- 高风险点预识别
- reviewer routing 设计

不负责：

- 直接写 review comments
- 直接修改正文

### 2. Multi-Perspective Review Board Agent

负责：

- 模拟多个 reviewer 视角
- 输出结构化 review package
- 标记 major / minor issues

不负责：

- 直接做编辑综合决策
- 直接修稿

### 3. Editorial Synthesis & Decision Agent

负责：

- 汇总 reviewer outputs
- 提炼决策主矛盾
- 给出整体 editorial-style judgment

不负责：

- 直接重写全文
- 脱离 reviewer outputs 自行下结论

### 4. Revision Planning & Comment Consolidation Agent

负责：

- 去重、归类、排序 comments
- 建立 revision priority
- 形成 revision roadmap

不负责：

- 直接替代修稿执行
- 把不可修问题伪装成可修

### 5. Constrained Manuscript Revision Agent

负责：

- 在证据边界内执行修稿
- 将 revision roadmap 转化为具体修订动作
- 保证修订可追踪、可核查、可回退

不负责：

- 编造新事实
- 自动补充缺失统计、数字、文献
- 引入输入中不存在的证据

---

## 与其他目录的关系

### 与 `03_Prompts/` 的关系

- `03_Prompts/` 处理单任务执行
- `08_Agent_System/` 处理多阶段编排

### 与 `05_Quality_Control/` 的关系

- `05_Quality_Control/` 提供基础清单式质控
- `08_Agent_System/` 提供更高阶的多角色压力测试与修稿增强

### 与 `02_Workflow/` 的关系

- `02_Workflow/阶段00-14` 是写作主流程
- `02_Workflow/阶段15-18` 是非智能体用户的后期轻量流程
- `08_Agent_System/` 是智能体用户的后期增强流程

---

## 标准中间产物

本目录中的 5 个 Agent 建议通过以下中间产物顺序传递信息：

1. `Review Architecture Package`
2. `Multi-Perspective Review Package`
3. `Editorial Decision Package`
4. `Revision Roadmap`
5. `Final Revision Package`

详细字段说明见：

- `Agent输入输出接口规范.md`

---

## 推荐阅读顺序

建议按以下顺序阅读本目录：

1. `README.md`
2. `Agent总览与调用顺序.md`
3. `Agent工作流映射.md`
4. `Agent输入输出接口规范.md`

---

## 一句话总结

`08_Agent_System/` 是给接近终稿的 manuscript 用的增强版内部评审与修稿系统；  
它与 `阶段15-18` 不是上下游关系，而是“高级版”和“轻量版”的两条后期路线。