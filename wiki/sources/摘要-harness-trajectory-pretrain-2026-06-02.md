---
title: "摘要-Harness前置预训练范式进入Agentic Workflow阶段"
type: source
tags: [来源, 研究, Harness, trajectory, 预训练, 后训练, Agentic, KV cache, HBM, DRAM, SSD]
sources: [raw/研究纪要/半导体/2026-06-02 下一代大模型训练方向调研：Harness 前置，预训练范式进入 Agentic Workflow 阶段.md]
date: 2026-06-02
origin: acecamptech.com
last_updated: 2026-06-07
---

## 核心摘要

下一代大模型核心变化 **不是参数变大或 token 增多，而是 Harness 能力从后训练前置到预训练**。Harness = 模型围绕复杂任务的规划/拆解/工具调用/记忆管理/验证/回滚/多步骤执行综合能力。关键数据形态 = **trajectory data 轨迹数据**：完整任务从提出 → 拆解 → 执行 → 工具调用 → 验证 → 修正的过程，模型不只学"答案是什么"而学"任务如何完成"。**训练侧**：算力需求继续上行（来自规模 + 数据增长，非架构突变），Transformer 短期仍主流；**跨数据中心互联 + 数据清洗 + 训练调试能力成核心壁垒**。**推理侧**：Agentic workflow 推高 token 消耗 + KV cache；短期 DRAM 作为 HBM 缓存更现实，长期历史对话/任务状态累积 → SSD 承接更多 KV cache，**存储需求弹性巨大**。

## 关键数据点

- **核心变化**：Harness 从后训练 → 预训练内化
- **关键数据**：trajectory data（任务执行轨迹）
- **短期架构**：Transformer 主流
- **训练壁垒**：跨数据中心互联 + 数据清洗 + 调试
- **推理存储弹性**：HBM → DRAM → SSD 三级
- **Agentic workflow 影响**：token 消耗 + KV cache 显著增长

## 关联连接

- [[Harness]] / [[trajectory data]] — 新概念
- [[AgenticAI]] / [[Agentic Workflow]] — 范式
- [[摘要-llm-context-agent-storage-cpu-2026-06-01]] — 同主题 6/01
- [[摘要-na-llm-pre-vs-post-training-2026-06-01]] — 同主题预训练
- [[KV cache]] / [[HBM]] / [[SSD]] — 存储弹性
