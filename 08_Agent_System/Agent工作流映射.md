
---
# Agent输入输出接口规范

本文件用于规定 `08_Agent_System/` 中 5 个 Agent 之间的标准接口。  
目标是确保：

- 输入结构尽可能稳定
- 中间产物可以顺序传递
- 不同 Agent 之间不会因为格式混乱而失联
- revision 过程具有可追踪性、可回退性与可核查性
- 所有评审与修稿动作始终受证据边界约束

---

## 一、总原则

本系统中的 5 个 Agent 不是彼此独立的单轮工具。  
每一个 Agent 的输出，原则上都应成为下一个 Agent 的输入基础。

因此，接口设计必须满足以下要求：

### 1. 结构化
输出不能只是泛泛长文，必须有清晰模块和字段层次。

### 2. 可传递
后续 Agent 应能直接读取前一阶段的关键结论、风险点、优先级与建议。

### 3. 可核查
关键判断应尽量能回溯到 manuscript、figures、methods、supplementary 或前序 reviewer comments。

### 4. 不越权
接口中不能把“未提供的事实”伪装成“已确认事实”。

### 5. 可追踪
尤其在 revision 阶段，每一项修订建议和修订动作都应有来源可查。

---

## 二、适用前提

本接口规范仅适用于以下场景：

- manuscript 已基本完整
- 已完成基础质控
- 已具备稳定的手稿、图表、方法与补充材料
- 用户选择走 `08_Agent_System/` 这条增强版后期路线

本规范**不适用于**：

- 章节初稿生成
- 早期 Prompt 优化
- 单章节局部改写
- 基础文献与数字核查

这些任务应继续使用：

- `02_Workflow/阶段00-14`
- `03_Prompts/`
- `04_Templates/`
- `05_Quality_Control/`

---

## 三、全系统基础输入包

建议所有 Agent 在调用时共享同一层基础输入。

## 基础输入包建议包括

### A. 手稿主体
- Manuscript full text
- Title
- Abstract
- Keywords
- Introduction
- Results
- Discussion

### B. 证据材料
- Figures and legends
- Methods
- Supplementary materials
- Validated key results
- Key numbers table

### C. 期刊与风格信息（如有）
- Candidate journals
- Target journal
- Journal style constraints

### D. 质控与修订上下文（如有）
- Prior QC outputs
- Prior revision notes
- Human author constraints
- Known unresolved issues

---

## 四、五个标准中间产物

本系统建议 5 个 Agent 之间通过以下标准中间产物顺序传递信息：

1. `Review Architecture Package`
2. `Multi-Perspective Review Package`
3. `Editorial Decision Package`
4. `Revision Roadmap`
5. `Final Revision Package`

---

# 1. Review Architecture Package

## 由谁输出
- `Field Analysis & Review Architecture Agent`

## 供谁使用
- `Multi-Perspective Review Board Agent`
- 可供后续所有 Agent 参考

## 核心作用
定义“这篇稿件应该如何被审”。

## 建议结构

### A. Manuscript Positioning
- field
- subfield
- study type
- manuscript type
- target contribution zone

### B. Contribution Framing
- central question
- core novelty
- main claim candidates
- likely significance framing
- likely skepticism points

### C. Evidence Architecture
- main evidence chain
- supporting figure-to-claim mapping
- strongest evidence nodes
- weakest evidence nodes
- likely vulnerable interpretations

### D. Reviewer Routing Plan
- suggested reviewer roles
- role-specific focus
- major risk domains to inspect

### E. Review Priority Map
- highest priority issues
- medium priority issues
- lower priority issues

### F. Boundary Notes
- evidence-limited areas
- claims that require wording restraint
- issues likely not repairable without new data

---

# 2. Multi-Perspective Review Package

## 由谁输出
- `Multi-Perspective Review Board Agent`

## 供谁使用
- `Editorial Synthesis & Decision Agent`
- `Revision Planning & Comment Consolidation Agent`

## 核心作用
模拟多个 reviewer 视角下的结构化审稿结果。

## 建议结构

### A. Reviewer Panel Overview
- included reviewer roles
- review scope
- overall panel summary

### B. Reviewer-by-Reviewer Comments
对于每个 reviewer，建议包含：

- reviewer role
- overall stance
- major issues
- minor issues
- evidence concerns
- interpretation concerns
- methods/statistics concerns（如适用）
- journal fit concerns（如适用）
- actionable recommendations

### C. Cross-Reviewer Convergence
- repeated concerns across reviewers
- conflicting views across reviewers
- consensus major issues
- consensus minor issues

### D. Overall Risk Snapshot
- novelty risk
- evidence risk
- interpretation risk
- methods/statistics risk
- writing/clarity risk
- journal fit risk

---

# 3. Editorial Decision Package

## 由谁输出
- `Editorial Synthesis & Decision Agent`

## 供谁使用
- `Revision Planning & Comment Consolidation Agent`
- `Constrained Manuscript Revision Agent`

## 核心作用
将多 reviewer outputs 综合为更接近编辑判断的单一决策框架。

## 建议结构

### A. Editorial Summary
- overall manuscript status
- main strengths
- main weaknesses
- top decision-driving issues

### B. Decision Tendency
- likely category:
  - reject-like
  - major-revision-like
  - minor-revision-like
  - potentially acceptable after focused revision

### C. Decisive Issues
- must-fix issues
- high-risk unresolved issues
- non-fatal but important issues

### D. Conflict Resolution Notes
- reviewer disagreement summary
- editor-weighted interpretation of conflicts

### E. Revision Direction
- strategic revision priorities
- sections needing strongest intervention
- issues requiring wording downgrade instead of factual repair

---

# 4. Revision Roadmap

## 由谁输出
- `Revision Planning & Comment Consolidation Agent`

## 供谁使用
- `Constrained Manuscript Revision Agent`

## 核心作用
把复杂分散的评论与编辑判断整理成一条可执行的修稿路线。

## 建议结构

### A. Consolidated Issue List
每项建议至少包含：

- issue id（内部编号即可）
- issue category
- source
- issue summary
- affected section(s)
- severity
- fixability level

### B. Priority Tiers
- tier 1: must revise before submission
- tier 2: strongly recommended
- tier 3: optional refinement

### C. Action Plan
每项建议至少包含：

- action objective
- recommended revision type
- allowed evidence basis
- forbidden moves
- expected output

### D. Constraint-Bound Issues
- issues that cannot be truly repaired with current evidence
- issues that require toned-down wording rather than stronger claims
- issues that must remain flagged to the human author

---

# 5. Final Revision Package

## 由谁输出
- `Constrained Manuscript Revision Agent`

## 供谁使用
- 人类作者
- 可供后续终审参考

## 核心作用
记录最终修稿执行结果，而不是只给出一版更顺的全文。

## 建议结构

### A. Revision Summary
- revised sections
- overall revision intent
- key constraints respected

### B. Change Log
每项修改建议至少包含：

- corresponding roadmap issue
- section revised
- type of change
- before/after summary
- evidence basis used

### C. Unresolved Issues
- issues left unresolved
- reason unresolved
- whether manual author decision is needed

### D. Boundary Compliance Notes
- no new facts added beyond source materials
- no unsupported statistics inserted
- no fabricated citations introduced
- no claim strengthening beyond evidence

### E. Final Risk Notes
- remaining major risks
- remaining moderate risks
- submission caution points

---

## 五、标准传递链

建议按以下链路传递：

```text
基础输入包
→ Review Architecture Package
→ Multi-Perspective Review Package
→ Editorial Decision Package
→ Revision Roadmap
→ Final Revision Package
```

---

## 三、与 `阶段15-18` 的关系

### `阶段15-18` 解决什么

- 基础期刊推荐与匹配
- 目标期刊定向润色
- 整稿终稿润色与连贯性修复
- 投稿前终审

### `08_Agent_System` 解决什么

- 审稿架构设计
- 多角色审稿模拟
- 编辑综合判断
- comments 整合与修稿路线规划
- 强约束修稿执行

因此，二者不是简单替代关系，也不是上下游关系，而是：

- `阶段15-18` = 轻量版后期处理
- `08_Agent_System` = 增强版后期处理

---

## 四、Agent 子系统内部映射

虽然它不直接映射到 `阶段15-18`，但如果从功能层面理解，5 个 Agent 仍然对应投稿前后期工作的不同层次：

```
Field Analysis & Review Architecture Agent→ 更高阶的领域定位 + 审稿架构设计Multi-Perspective Review Board Agent→ 更高阶的内部审稿模拟Editorial Synthesis & Decision Agent→ 编辑层综合判断Revision Planning & Comment Consolidation Agent→ 修稿规划层Constrained Manuscript Revision Agent→ 高约束终修执行层
```

注意，这种“类似”只是帮助理解功能分工，  
不代表它们属于 `阶段15-18` 的细分拆解。

---

## 五、Agent 子系统内部工作流

`08_Agent_System/` 内部是严格顺序化的：

```
1. Field Analysis & Review Architecture Agent2. Multi-Perspective Review Board Agent3. Editorial Synthesis & Decision Agent4. Revision Planning & Comment Consolidation Agent5. Constrained Manuscript Revision Agent
```

其逻辑为：

```
先判断“这篇稿应该怎么审”→ 再从多个 reviewer 视角进行审稿→ 再综合成更接近编辑判断的结果→ 再把分散 comments 整理成修稿路线→ 最后在证据边界内执行修稿
```

---

## 六、与前期流程的边界

`08_Agent_System/` 不用于以下任务：

- 章节初稿生成
- Prompt 优化
- 单章节局部改写
- 单章节基础质控
- 文献与数字的基础核查
- 早期结构搭建
- 研究事实材料整理

这些任务仍应优先由以下目录处理：

- `02_Workflow/`
- `03_Prompts/`
- `04_Templates/`
- `05_Quality_Control/`

---

## 七、推荐理解方式

最推荐的理解方式是：

### 先完成主流程

```
阶段00-14
```

### 然后在两条后期路线中二选一

#### 路线 A：非智能体轻量后期路线

```
阶段15-18
```

#### 路线 B：智能体增强后期路线

```
08_Agent_System
```

---

## 八、哪类用户更适合哪条路线

### 更适合 `阶段15-18` 的用户

- 不想使用多智能体
- 希望流程简单、手动可控
- 只需要基础期刊匹配、基础定向润色、基础终审
- 不需要复杂 reviewer routing 和 revision roadmap

### 更适合 `08_Agent_System` 的用户

- 希望在投稿前做更接近真实世界的内部审稿模拟
- 希望得到多 reviewer comments 与编辑综合判断
- 希望系统整理修稿优先级
- 希望在强约束条件下做最后一轮修订

---

## 九、一句话总结

`08_Agent_System/` 不是 `02_Workflow/阶段15-18` 的后续步骤，  
而是与其平行的一条**增强版投稿前评审与修稿路线**。