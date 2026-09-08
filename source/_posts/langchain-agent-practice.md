---
title: LangChain Agent 实战：从原理到落地
categories:
  - AI
  - Agent
tags:
  - LLM
  - Agent
  - LangChain
description: 系统讲解 LangChain Agent 的核心组件、ReAct 范式、工具调用与工程化落地。
abbrlink: 2eb68a2e
date: 2026-09-08 11:00:00
---

# LangChain Agent 实战：从原理到落地

> Agent 是大模型从"对话"走向"行动"的关键。本文以 LangChain 为例，讲解 Agent 的核心概念。

## 什么是 Agent

Agent = **大模型（推理）+ 工具（执行）+ 记忆（上下文）**。

传统 LLM 只能生成文本，Agent 让 LLM 能够：

1. 决定是否调用外部工具
2. 选择调用哪个工具
3. 解析工具返回
4. 多步推理直到完成目标

## ReAct 范式

最经典的 Agent 范式是 **ReAct（Reasoning + Acting）**：

```text
Thought: 我需要先查询天气
Action: get_weather
Action Input: 北京
Observation: 晴，25°C
Thought: 现在可以给出穿衣建议了
Final Answer: 北京今天晴，25°C，建议穿短袖。
```

## 核心组件

### 1. Tool（工具）

```python
from langchain.tools import tool

@tool
def get_weather(city: str) -> str:
    """查询指定城市的天气"""
    return f"{city}：晴，25°C"
```

### 2. Agent Executor

负责驱动循环：思考 → 行动 → 观察 → 再思考。

### 3. Memory

短期记忆（对话上下文）+ 长期记忆（向量库）。

## 常见坑

- **工具描述不清晰**：LLM 不知道怎么用
- **循环没有终止条件**：Agent 卡死
- **错误处理缺失**：单个工具失败导致整个链路崩

## 工程化建议

| 维度 | 建议 |
|------|------|
| 工具数量 | 控制在 10 个以内 |
| 工具粒度 | 单一职责，避免组合工具 |
| Prompt | 明确告诉 LLM 何时停止 |
| 日志 | 完整记录 Thought / Action / Observation |
| 评估 | 准备 gold set，定期跑回归 |

## 总结

Agent 不是银弹，但它把 LLM 从"聊天对象"升级为"工作协作者"。本站后续会持续更新 Agent 实战内容。