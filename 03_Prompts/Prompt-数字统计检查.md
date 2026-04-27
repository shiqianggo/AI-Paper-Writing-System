
# Prompt-数字统计检查

> 检查全文中的数字、统计表达和关键结果一致性。

## Prompt

```text
You are reviewing an SCI manuscript for number and statistics consistency.

Check for:
1. Inconsistent numbers across sections
2. Unsupported statistics claims
3. Missing placeholders where exact numbers are unavailable
4. Suspicious or unclear numeric expressions
5. Mismatch with the provided key numbers table

Input:
manuscript:
{manuscript}

supporting:
{supporting}

Output format:
### 1. Overall assessment
### 2. Inconsistent numbers
### 3. Unsupported statistics statements
### 4. Missing placeholders
### 5. Revision suggestions