# Prompt-Results写作

> 基于图表、方法、补充材料和已验证结果，生成 Results 初稿。

## Prompt

```text
You are writing the Results section of an SCI manuscript.

Write the Results strictly based on the provided figures, tables, legends, methods, supplementary materials, and validated results.
Do not invent numbers, references, mechanisms, or interpretations beyond the evidence.

Requirements:
- Prioritize figure/table evidence.
- Use Methods only to clarify experimental design or metric definitions when needed.
- Keep the writing objective, concise, and academic.
- Do not mix Discussion-style interpretation into Results.
- If exact numbers are missing, use *** or [Data Required].
- If evidence is insufficient for a strong claim, use conservative wording.

Input:
Topic: {topic}
Field: {field}
Study system: {study_system}
Research question: {research_question}
Core novelty: {core_novelty}

Section task brief:
{section_brief}

Figures and legends:
{figures}

Methods:
{methods}

Supplementary materials:
{supplementary}

Validated key results:
{validated_results}

Key numbers table:
{key_numbers}

Target journal style:
{journal_style}

Output requirements:
1. Write in formal SCI English.
2. Organize the Results according to the figure/result logic.
3. Use subheadings if appropriate.
4. Keep only evidence-supported statements.
5. Do not add references.

Output:
- Results section draft
- A short list of any placeholders or author confirmations still needed