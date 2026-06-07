---
title: "摘要-上下文Agent集群对存储与CPU需求 Anthropic在TPU/Trainium效率"
type: source
tags: [来源, 研究纪要, AI推理, KV cache, HBM, SSD, Harness, Anthropic, Trainium, TPU, ASIC, GPU TCO]
sources: [raw/研究纪要/半导体/2026-06-01 大模型调研-北美AI工程师：AI推理时代上下文长度增加及Agent集群发展对不同类型存储及CPU需求影响，发展超大规模推理集群的必要性以及算力利用率提升方式，A.md]
date: 2026-06-01
origin: acecamptech.com
last_updated: 2026-06-07
---

## 核心摘要

北美 AI 工程师深度视角：(1) **KV cache 与上下文长度线性增长**，上下文翻倍 → GPU 卡数至少翻倍；HBM 每代仅 +30%，超出部分 offload 到 CPU DRAM；中国更激进 offload 到 SSD（避免重算）。推理瓶颈是**内存带宽和容量** ≠ 算力。(2) **未来 6 个月推理主线**：从「强 coding」→「弱 coding + harness engineer」核心，调度子 agent + tool calling。Google I/O 路径领先，OpenAI 跟进，Anthropic 准备 IPO 多发宏大叙事少落地。(3) **Harness 产品差异极大**，Harvey AI/EvenUp 法律文书重 RAG + Reasoning（亲 DeepSeek/GLM 开源），coding 类亲 tool calling。(4) **Claude 在 Trainium vs TPU 运行效率**：TPU 体系架构更适合 Claude 模型 token 经济性更佳；Trainium 是供应链多元化的 fallback。(5) **ASIC vs GPU TCO**：单位 token 成本 ASIC 优势在头部 hyperscaler 自研场景显著（已重数倍 TPU 投入支撑）；GPU 在通用性 + 软件栈仍领先。

## 关键数据点

- **上下文与 KV cache**：线性关系
- **HBM 容量代际增长**：~30%/代（远不够补偿上下文增长）
- **典型推理集群迁移**：H100/H200 → GB200/GB300（更多 HBM + NVLink）
- **8 卡 → 128 卡承载单模型**：单卡权重从 1/8 → 1/128
- **中国 offload 策略**：HBM → CPU DRAM → SSD（差速读但避重算）
- **未来 6m**：harness + 多 sub-agent + tool calling
- **Harvey AI 模型偏好**：DeepSeek / GLM（强 Reasoning）

## 关联连接

- [[AgenticAI]] / [[Harness]] — 概念框架
- [[HBM]] / [[KV cache]] — 推理瓶颈
- [[Anthropic]] / [[OpenAI]] / [[Google]] — 主战大厂
- [[Trainium]] / [[TPU]] / [[ASIC]] — 自研芯片
- [[摘要-vera-cpu-platform-2026-06-01]] — CPU 端协同
- [[摘要-na-llm-pre-vs-post-training-2026-06-01]] — 同日预/后训练
- [[摘要-deep-seek-tech-impact-storage-cpu-2026-06-03]] — 6/03 续
