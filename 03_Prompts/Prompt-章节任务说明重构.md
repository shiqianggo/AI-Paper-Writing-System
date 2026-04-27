# Prompt-章节任务说明重构

> 用于把作者脑中的“这一章要写什么”重构为结构清晰、可直接交给 AI 的章节任务说明。  
> 它对应 Workflow 中的：
> - `阶段01-人工写章节任务说明`
> - `阶段02-优化章节提示词`

---

# 1. 使用目的

这个 Prompt 不是直接写论文正文，  
而是先把作者已有的章节意图整理为：

- 明确的章节目标
- 明确的信息来源
- 明确的写作边界
- 明确的段落任务
- 明确的输出要求

这样做的好处是：

1. 防止 AI 一开始就“自由发挥”
2. 把作者的真实写作意图结构化
3. 让后续写作 Prompt 更稳定
4. 降低章节跑偏、混入错误任务、越界表述的风险

---

# 2. 适用场景

适用于以下情况：

- 作者脑中知道这一章“大概要写什么”，但还没有形成高质量 prompt
- 已经有一版口语化或零散的任务描述，需要转成专业任务说明
- 想先拆清章节结构，再进入正式写作
- 想让 AI 帮忙把“写作要求”整理成更清晰、更强约束的形式

尤其适用于：
- Results
- Introduction
- Discussion

其中对 Results 最重要，因为 Results 最依赖结构拆解和证据边界控制。

---

# 3. 输入材料

可输入以下一种或多种材料：

- 作者自己写的口语化章节要求
- 粗略段落规划
- 图表分组说明
- 已知研究主线
- 想强调的核心发现
- 希望避免的问题
- 目标期刊风格信息
- 已有简略 prompt 草稿

---

# 4. 标准 Prompt 模板

```text
You are helping transform a rough chapter-writing idea into a clear, professional, and evidence-aware task brief for AI-assisted SCI manuscript writing.

Your task is NOT to write the chapter itself yet.
Your task is to reconstruct the author's rough instructions into a structured chapter task specification that can later be used to generate the actual section.

Please work strictly based on the information provided by the author.
Do not add unsupported claims, missing numbers, fabricated references, or speculative conclusions.

## What you need to do
Based on the author's input, rewrite the chapter task into a structured writing brief that includes:

1. Section objective
2. Core content to cover
3. Suggested internal structure or paragraph logic
4. Evidence sources to prioritize
5. Boundaries and things that must not be over-interpreted
6. Missing information that should remain as placeholders or require author confirmation
7. Output expectations for the later writing step

## Requirements
- Preserve the author's real scientific intent.
- Make the task brief clearer, more structured, and more executable.
- If the section is Results, prioritize figure/table-driven structure.
- If some information is missing, explicitly mark it as “to be confirmed” or “data required”.
- Do not directly draft the manuscript section.
- Do not convert speculative ideas into confirmed conclusions.
- Keep the tone professional, concise, and operational.

## Input from the author
Section to prepare: {section}
Research topic: {topic}
Field: {field}
Study system: {study_system}
Research question: {research_question}
Core novelty: {core_novelty}

Author's rough section instruction:
{rough_instruction}

Available materials:
- Figures and legends: {figures}
- Methods: {methods}
- Supplementary materials: {supplementary}
- Validated key results: {validated_results}
- Key numbers table: {key_numbers}
- Target journal style: {journal_style}

## Output format
Please provide the output in the following structure:

### 1. Reconstructed section mission
### 2. Recommended content blocks
### 3. Suggested paragraph-level logic
### 4. Evidence priority order
### 5. Boundary controls / what not to overstate
### 6. Missing information / placeholders to keep
### 7. Final task brief for downstream AI writing