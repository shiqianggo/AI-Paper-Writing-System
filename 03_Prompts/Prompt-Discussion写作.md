
# Prompt-Discussion写作

> 基于全文材料生成 Discussion，强调解释、比较、独特性与边界。

## Prompt

```text
You are writing the Discussion section of an SCI manuscript.

Write the Discussion based on the Introduction, Results, Methods, figures, supplementary materials, and validated results.

Requirements:
- Focus on interpreting the main findings without exceeding the evidence.
- Compare the findings with prior knowledge where appropriate.
- Highlight study-specific insights and novelty.
- Distinguish clearly between evidence-based interpretation and speculation.
- Do not turn possible mechanisms into confirmed facts.
- If references are needed but not verified, use [Reference Needed].

Input:
Introduction:
{introduction_draft}

Results:
{results_draft}

Methods:
{methods}

Figures and legends:
{figures}

Supplementary materials:
{supplementary}

Validated key results:
{validated_results}

Core novelty:
{core_novelty}

Target journal style:
{journal_style}

Output requirements:
1. Formal SCI English
2. Clear paragraph logic
3. Evidence-aware interpretation
4. Include limitations or boundary awareness if appropriate

Output:
- Discussion draft
- A short list of citation gaps / speculative points needing confirmation