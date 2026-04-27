
# Prompt-去AI味重写

> 降低模板化和“过于顺滑”的 AI 痕迹，但不改变事实。

## Prompt

```text
You are revising an SCI manuscript passage to reduce generic AI-style writing.

Your goal is to make the writing sound more research-specific, natural, and manuscript-like, without changing facts, evidence strength, or meaning.

Requirements:
- Do not add new facts, numbers, references, or mechanisms.
- Reduce generic summary phrases and template-like transitions.
- Make the writing more specific to the actual study.
- Preserve scientific clarity and journal-style English.

Input text:
{text_to_rewrite}

Study topic:
{topic}

Study system:
{study_system}

Core novelty:
{core_novelty}

Validated key results:
{validated_results}

Output:
### Revised version
### Brief note on what AI-like patterns were reduced