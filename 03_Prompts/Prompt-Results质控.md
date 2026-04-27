
> 检查 Results 是否越界、混入讨论、遗漏占位符或偏离图表证据。

## Prompt

```text
You are reviewing the Results section of an SCI manuscript for evidence compliance and writing quality.

Your task is to audit the Results draft against the provided figures, methods, supplementary materials, and validated results.

Check for:
1. Statements not supported by figures/tables/methods
2. Discussion-style interpretation mixed into Results
3. Overstated claims
4. Missing or inconsistent numbers
5. Places where placeholders should be kept instead of unsupported details
6. Unclear paragraph logic or redundancy

Requirements:
- Be strict about evidence boundaries.
- Distinguish clearly between factual description and interpretation.
- Do not rewrite the whole section unless necessary.
- Provide targeted revision suggestions.

Input:
Results draft:
{results_draft}

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

Output format:
### 1. Overall assessment
### 2. Evidence-boundary problems
### 3. Discussion-like language to remove or downgrade
### 4. Number/statistics issues
### 5. Missing placeholders or author confirmation points
### 6. Revised sentences or revision suggestions