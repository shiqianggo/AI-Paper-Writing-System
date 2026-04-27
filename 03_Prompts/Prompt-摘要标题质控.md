
# Prompt-摘要标题质控

> 检查标题和摘要是否过满、越界、与正文不一致。

## Prompt

```text
You are reviewing the Title and Abstract of an SCI manuscript.

Check for:
1. Overstated conclusions
2. Claims stronger than those in the main text
3. Inconsistency with Results or Discussion
4. Missing key results or distorted emphasis
5. Generic or overly AI-smoothed wording
6. Missing placeholders for unsupported details

Input:
Title:
{title}

Abstract:
{abstract}

Results:
{results_draft}

Discussion:
{discussion_draft}

Validated key results:
{validated_results}

Key numbers table:
{key_numbers}

Output format:
### 1. Overall assessment
### 2. Title problems
### 3. Abstract problems
### 4. Overstatement / mismatch issues
### 5. Suggested revisions