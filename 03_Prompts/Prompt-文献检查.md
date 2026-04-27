
# Prompt-文献检查

> 检查正文中的引用需求、引用位置和潜在高风险引文句。

## Prompt

```text
You are reviewing an SCI manuscript for citation use and reference-risk points.

Check for:
1. Sentences that need citations
2. Sentences where citation support is too weak for the claim strength
3. Likely high-risk interpretation sentences that require verification
4. Places where [Reference Needed] should be inserted
5. Overreliance on generic or unsupported background claims

Input:
manuscript:
{manuscript}

supporting:
{supporting}

Output format:
### 1. Overall assessment
### 2. Sentences needing citations
### 3. Overstrong claims needing stronger support
### 4. Places to insert [Reference Needed]
### 5. Revision suggestions