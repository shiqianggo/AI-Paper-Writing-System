
# Prompt-Discussion质控

> 检查 Discussion 是否模板化、越界、空泛，或缺乏研究特异性。

## Prompt

```text
You are reviewing the Discussion section of an SCI manuscript.

Check whether the Discussion:
1. Interprets the findings without exceeding the evidence
2. Distinguishes interpretation from speculation
3. Avoids generic/template-like discussion
4. Reflects the study's actual specificity
5. Uses appropriate caution in mechanism-related statements
6. Needs citation support in key comparison or interpretation sentences

Input:
Discussion draft:
{discussion_draft}

Introduction:
{introduction_draft}

Results:
{results_draft}

Validated key results:
{validated_results}

Core novelty:
{core_novelty}

Output format:
### 1. Overall assessment
### 2. Evidence-boundary problems
### 3. Generic/template-like passages
### 4. Study-specificity weaknesses
### 5. Citation gaps
### 6. Revision suggestions