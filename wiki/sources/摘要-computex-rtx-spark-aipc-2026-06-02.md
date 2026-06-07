---
title: "摘要-COMPUTEX 2026 RTX Spark与AIPC换机潮"
type: source
tags: [来源, 研究, RTX Spark, AIPC, NVIDIA, Microsoft, ARM, Blackwell, 联发科, Agentic AI]
sources: [raw/研究纪要/半导体/2026-06-02 COMPUTEX 2026首日：英伟达RTX Spark落地，AIPC长周期硬件演进路径与巨头竞合研判.md]
date: 2026-06-02
origin: acecamptech.com
last_updated: 2026-06-07
---

## 核心摘要

英伟达 RTX Spark 超级芯片在 Computex 2026 首日发布——**首颗真正能打破 AIPC「鸡肋」格局的本地 Agentic AI 芯片**。技术规格：台积电 3nm + 20 核 Grace ARM CPU（联发科协同设计）+ Blackwell 架构 6,144 CUDA 核心 GPU + 高带宽硅桥互连，**单芯 1 PetaFLOP 本地 AI 算力**，最高 128GB LPDDR5X **统一内存（Unified Memory）**架构。核心突破：(1) 本地零延迟运行千亿参数 LLM + 100 万 token 上下文（vs 初代 AIPC NPU 仅 45 TOPS）；(2) UMA 共享 128GB 内存打破存储墙（vs 传统 16GB DRAM + 8-16GB VRAM 隔离）。软件生态 OpenShell 原生运行层 + Adobe 重构 Photoshop/Premiere 原生支持。**AIPC 换机潮逻辑**：算力 + 内存架构双重跨越 → 颠覆 ARM Windows PC 范式，从「点击运行应用」转向「自然语言驱动 Agentic」。AMD/Intel/Qualcomm 的 X86 + 原 ARM 阵营面临结构性压力。

## 关键数据点

- **RTX Spark 算力**：1 PetaFLOP
- **CPU**：20 核 Grace ARM（联发科协同）
- **GPU**：6,144 Blackwell CUDA
- **内存**：128GB LPDDR5X UMA
- **本地模型**：千亿参数 + 100 万 token 上下文
- **vs 初代 AIPC**：NPU 45 TOPS → 1 PFLOP（×20,000+）
- **传统隔离**：16GB DRAM + 8-16GB VRAM
- **工艺**：台积电 3nm

## 关联连接

- [[NVDA US]] / [[MSFT US]] — 联合发布
- [[2454 TT]] — 联发科协同
- [[ARM]] — 架构
- [[AgenticAI]] — 范式驱动
- [[AIPC]] — 概念页（新）
- [[摘要-vera-cpu-platform-2026-06-01]] — 服务器侧对应
- [[摘要-jensen-huang-vera-rubin-gtc-taipei-2026-06-01]] — GTC 同主题
- [[摘要-consumer-electronics-2026-06-04]] — 6/04 消费电子展望
