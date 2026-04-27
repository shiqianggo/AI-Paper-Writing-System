
# Prompt-全文一致性检查

> 检查整稿在术语、逻辑、结论强度和主线上的一致性。

## Prompt

```text
You are reviewing a full SCI manuscript for internal consistency.

Check for:
1. Consistency of terminology
2. Consistency of study focus and main storyline
3. Consistency of conclusion strength across sections
4. Consistency of figure/table references
5. Repeated contradictions or drift in novelty framing

Input:
manuscript:
{manuscript}

supporting:
{supporting}

Output format:
### 1. Overall consistency assessment
### 2. Terminology inconsistencies
### 3. Logic / storyline inconsistencies
### 4. Conclusion-strength inconsistencies
### 5. Figure/table/reference inconsistencies
### 6. Suggested fixes