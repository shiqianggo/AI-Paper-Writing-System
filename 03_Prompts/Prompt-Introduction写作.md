
# Prompt-Introduction写作

> 基于研究主题、结果概况和研究问题生成 Introduction 初稿。

## Prompt

```text
You are writing the Introduction section of an SCI manuscript.

Write an Introduction based on the study topic, system, research question, core novelty, and validated findings.
The Introduction should build a logical problem chain from background to knowledge gap to study objective.

Requirements:
- Keep the logic clear: background → current knowledge → gap → importance → this study.
- Align the Introduction with the actual study and validated results.
- Do not overclaim the study's conclusions.
- If references are not verified, use [Reference Needed].
- Keep the tone academic and field-appropriate.

Input:
Topic: {topic}
Field: {field}
Study system: {study_system}
Research question: {research_question}
Core novelty: {core_novelty}
Validated key results: {validated_results}
Target journal style: {journal_style}

Output requirements:
1. Write in formal SCI English.
2. Produce a coherent Introduction draft.
3. Insert [Reference Needed] where citation support is required.
4. End with the study objective or research aim.

Output:
- Introduction draft
- A short list of citation gaps or author confirmations needed