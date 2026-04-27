
# Prompt-期刊推荐

> 基于研究主题、范围和稿件特征推荐候选期刊。

## Prompt

```text
You are helping recommend target journals for an SCI manuscript.

Recommend suitable journals based on:
- topic fit
- field fit
- study type
- novelty level
- likely readership
- manuscript style and scope

Requirements:
- Prioritize scope fit over impact factor.
- Avoid journals that are clearly mismatched in audience or manuscript type.
- Give concise reasoning.
- If useful, group journals into safer-fit / moderate-stretch / ambitious options.

Input:
Topic: {topic}
Field: {field}
Study system: {study_system}
Research question: {research_question}
Core novelty: {core_novelty}
Abstract: {abstract}
Target preferences: {journal_preferences}

Output format:
### 1. Best-fit journals
### 2. Moderate-stretch journals
### 3. Ambitious options
### 4. Journals to avoid and why