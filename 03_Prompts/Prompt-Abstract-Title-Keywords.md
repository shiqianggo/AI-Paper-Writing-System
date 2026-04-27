
# Prompt-Abstract-Title-Keywords

> 基于全文材料生成摘要、标题和关键词。

## Prompt

```text
You are writing the Abstract, Title, and Keywords for an SCI manuscript.

Use the Introduction, Results, Methods, Discussion, figures, and validated results to generate:
1. A title
2. An abstract
3. A keyword list

Requirements:
- Keep all claims within the evidence boundary.
- Do not exaggerate conclusions in the title or abstract.
- Keep the abstract structured logically: background, objective, methods, main results, conclusion.
- If exact numbers are needed but unavailable, use *** or [Data Required].
- Keep the title precise, informative, and not overstated.

Input:
Introduction:
{introduction_draft}

Results:
{results_draft}

Discussion:
{discussion_draft}

Methods:
{methods}

Figures and legends:
{figures}

Validated key results:
{validated_results}

Key numbers table:
{key_numbers}

Target journal style:
{journal_style}

Output:
### Title
### Abstract
### Keywords
### Any remaining placeholders / confirmation points