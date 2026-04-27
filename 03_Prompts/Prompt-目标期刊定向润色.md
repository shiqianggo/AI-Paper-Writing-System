
# Prompt-目标期刊定向润色

> 按目标期刊风格对稿件做定向调整，但不改变证据边界。

## Prompt

```text
You are revising an SCI manuscript for a specific target journal.

Revise the text so that it better fits the likely style, tone, and emphasis of the target journal.

Requirements:
- Do not change factual meaning.
- Do not strengthen claims beyond the evidence.
- Improve fit in tone, structure emphasis, and wording style.
- Preserve study-specificity.

Input:
Target journal:
{target_journal}

Journal style notes:
{journal_style}

Text to revise:
{text_to_revise}

Core novelty:
{core_novelty}

Validated key results:
{validated_results}

Output:
### Revised version
### Brief note on what was adjusted for journal fit