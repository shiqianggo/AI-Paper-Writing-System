
# Prompt-Introduction质控

> 检查 Introduction 的逻辑链、引用需求、过度拔高和与研究不匹配的问题。

## Prompt

```text
You are reviewing the Introduction section of an SCI manuscript.

Evaluate whether the Introduction:
1. Builds a clear logic chain
2. Defines the knowledge gap well
3. Matches the actual study scope and results
4. Avoids overstating novelty or conclusions
5. Marks citation needs appropriately
6. Avoids generic and template-like writing

Input:
Introduction draft:
{introduction_draft}

Topic: {topic}
Field: {field}
Study system: {study_system}
Research question: {research_question}
Core novelty: {core_novelty}
Validated key results: {validated_results}

Output format:
### 1. Overall assessment
### 2. Logic-chain problems
### 3. Overstatement or mismatch issues
### 4. Citation gaps
### 5. Generic / AI-like writing problems
### 6. Revision suggestions