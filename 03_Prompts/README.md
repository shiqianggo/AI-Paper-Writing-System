
## 本目录包含什么

### 前置构造类
- `Prompt-章节任务说明重构.md`
- `Prompt-写作提示词优化.md`

### 写作类
- `Prompt-Results写作.md`
- `Prompt-Introduction写作.md`
- `Prompt-Discussion写作.md`
- `Prompt-Abstract-Title-Keywords.md`

### 质控类
- `Prompt-Results质控.md`
- `Prompt-Introduction质控.md`
- `Prompt-Discussion质控.md`
- `Prompt-摘要标题质控.md`
- `Prompt-全文一致性检查.md`
- `Prompt-文献检查.md`
- `Prompt-数字统计检查.md`
- `Prompt-投稿前终审.md`

### 重写与增强类
- `Prompt-去AI味重写.md`
- `Prompt-增强研究特异性.md`

### 投稿适配类
- `Prompt-期刊推荐.md`
- `Prompt-目标期刊定向润色.md`

---

## Prompt 的角色

Prompt 适合处理以下任务：

- 单章节生成
- 单章节改写
- 单章节质控
- 局部重写
- 文献或数字核查
- 局部风格适配
- 局部终审

它的特点是：

- 任务边界清楚
- 输入输出相对短
- 更适合单轮调用
- 更适合人手动控制每一步

---

## Prompt 与 Agent 的区别

在系统加入 `08_Agent_System/` 后，需要明确两者的边界。

### Prompt 是什么
Prompt 是**原子任务工具**。  
用于解决某一个具体问题，例如：

- 写一段 Results
- 检查 Introduction 逻辑
- 重写一段 Discussion
- 核查参考文献
- 做摘要标题质控

### Agent 是什么
Agent 是**跨步骤编排系统**。  
用于串联多个角色、多轮评审和中间产物，例如：

- 领域分析
- 多 reviewer 审稿
- 编辑综合判断
- 审稿意见整合
- 强约束修稿

---

## 什么时候用 Prompt，什么时候用 Agent

### 优先用 Prompt 的场景
- 正在写正文
- 需要生成单个章节
- 需要优化某个提示词
- 需要检查局部问题
- 需要对单一任务做快速迭代

### 优先用 Agent 的场景
- 全文已基本完成
- 需要模拟投稿前内部审稿
- 需要做编辑决策综合
- 需要系统整理审稿意见
- 需要在强约束下推进整稿修订

---

## 与其他目录的关系

- 上位规则见：`01_Principles/`
- 标准流程见：`02_Workflow/`
- 输入模板见：`04_Templates/`
- 清单式质控见：`05_Quality_Control/`
- 后期多智能体系统见：`08_Agent_System/`

---

## 使用建议

在使用本目录中的任意 Prompt 前，建议先确认：

1. 输入是否已足够完整
2. 图表、方法、附录是否已准备好
3. 是否已明确证据边界与缺失信息处理方式
4. 当前任务是否真的是“单任务 Prompt”可以解决的
5. 若任务已经变成“多角色、多阶段、多中间产物串联”，则应考虑转入 `08_Agent_System/`

---

## 一句话总结

`03_Prompts/` 解决的是“单任务执行问题”；  
`08_Agent_System/` 解决的是“投稿前多角色审稿与修稿编排问题”。