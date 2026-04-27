
# Prompt-增强研究特异性

> 提升文本与本研究对象、尺度、数据和发现的绑定程度。

## Prompt

```text
You are revising an SCI manuscript passage to strengthen study-specificity.

Your task is to make the text more tightly connected to:
- the actual study system
- the actual scale/context
- the actual data types
- the actual validated findings

Requirements:
- Do not invent details.
- Do not overstate novelty.
- Replace generic statements with study-linked wording where possible.
- Keep the writing evidence-aware.

Input text:
{text_to_rewrite}

Topic:
{topic}

Field:
{field}

Study system:
{study_system}

Core novelty:
{core_novelty}

Validated key results:
{validated_results}

Output:
### Revised version
### Brief note on how specificity was strengthened