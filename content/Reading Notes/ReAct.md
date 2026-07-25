---
title: "ReAct: Synergizing Reasoning and Acting in Language Models"
tags:
  - paper
  - research/agent
date: 2026-07-25
---

> 示例论文笔记，展示推荐的记录格式。ICLR 2023, [arXiv:2210.03629](https://arxiv.org/abs/2210.03629)

## Motivation

LLM Agent 需要同时具备推理（Reasoning）和行动（Acting）能力，但此前两者是割裂研究的。

## Key Idea

将推理轨迹与任务动作交错生成：

$$
\text{Thought} \rightarrow \text{Action} \rightarrow \text{Observation} \rightarrow \cdots
$$

- **Thought**：对当前状态的自然语言推理
- **Action**：调用外部工具（如搜索）
- **Observation**：工具返回的结果，作为下一步推理的输入

## My Thoughts

- 未来可以结合推荐系统：把用户交互当作 Observation
- 与 [[Research/Agent|Agent]] 方向的多轮对话状态管理有天然联系
