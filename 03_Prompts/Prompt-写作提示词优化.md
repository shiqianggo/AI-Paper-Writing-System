# Prompt-写作提示词优化

> 用于把作者手写的原始章节提示词，优化成更清晰、更强约束、更适合大模型执行的正式写作 prompt。  
> 它对应真实流程中的：
> 1. 人工先写原始提示词
> 2. 再交给模型优化提示词
> 3. 最后再用优化后的提示词生成正文

---

# 1. 使用场景

适用于以下情况：

- 作者已经写了一版原始提示词，但内容口语化、冗长或结构不稳定
- 想让大模型先帮助整理 prompt，再用另一个模型正式写正文
- 想提升 prompt 的清晰度、逻辑性、可执行性和结果质量
- 想减少模型误解任务、乱发挥、写得空泛或越界的风险

尤其适用于：
- Results
- Introduction
- Discussion
- Abstract / Title / Keywords

---

# 2. 核心目标

本 Prompt 的目标不是写论文正文，  
而是把原始提示词优化为一个更适合 AI 执行的正式 prompt，使其具备：

- 更清晰的任务边界
- 更合理的段落结构
- 更明确的材料调用顺序
- 更严格的证据约束
- 更好的输出稳定性

---

# 3. Prompt

```text
You are helping optimize a manuscript-writing prompt for use with a large language model.

Your task is NOT to write the manuscript section itself.
Your task is to rewrite and improve the user's original prompt so that another model can better understand it and generate a stronger SCI-style section.

Please improve the prompt in the following ways:
1. Make the structure clearer
2. Make the section logic easier to follow
3. Make the evidence sources more explicit
4. Add boundary controls to prevent overinterpretation or hallucination
5. Keep the prompt concise but informative
6. Preserve the author's true scientific intent
7. Keep placeholders such as *** or [Data Required] when specific numbers are missing

Requirements:
- Do not write the manuscript section itself
- Do not add unsupported facts, references, or conclusions
- Do not change the author's intended section logic
- If the original prompt is too loose, reorganize it into a more structured writing instruction
- Make the final version more suitable for academic manuscript generation

Input:
Section: {section}
Topic: {topic}
Field: {field}
Study system: {study_system}
Research question: {research_question}
Core novelty: {core_novelty}

Original human-written prompt:
{raw_prompt}

Available materials:
- Figures and legends: {figures}
- Methods: {methods}
- Supplementary materials: {supplementary}
- Validated key results: {validated_results}
- Key numbers table: {key_numbers}
- Target journal style: {journal_style}

Output format:
### 1. Optimized prompt
### 2. Brief note on what was improved