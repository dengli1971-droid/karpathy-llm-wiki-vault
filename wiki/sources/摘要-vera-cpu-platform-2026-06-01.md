---
title: "摘要-Vera CPU英伟达为何重做CPU底座"
type: source
tags: [来源, 研究, NVIDIA, Vera CPU, Olympus, LPDDR5X, NVLink-C2C, AgenticAI]
sources: [raw/研究纪要/半导体/2026-06-01 Vera CPU 登场：英伟达为什么要在 GPU 之外重做算力底座？.md]
date: 2026-06-01
origin: acecamptech.com
last_updated: 2026-06-07
---

## 核心摘要

英伟达发布 Vera CPU，是面向 AI 工厂的自研服务器 CPU。**核心架构**：88 个 Olympus 核 / 176 线程 + 最高 1.5TB LPDDR5X / 1.2TB/s 内存带宽 + NVLink-C2C 1.8TB/s 一致性互联 + PCIe Gen6 + CXL 3.1 + 机密计算。**为什么必须重做 CPU**：Agentic AI 改变负载结构——AI 不再是单次问答，而是模型 → 工具调用 → 沙盒执行 → 结果返回的多轮闭环；CPU 端等待直接拖累 GPU 利用率与 token 成本。**三个产业链影响**：(1) 价值分配从「只看 GPU」扩展到 CPU + LPDDR5X + SOCAMM + CXL + 主板 + 电源 + 液冷 + 软件栈；(2) 云厂商采购从「买算力」转向「买有效产出」单位 token 成本；(3) Intel/AMD 在 AI 工厂增量场景面临纵向整合压力。Vera 不冲击存量企业应用市场，但锁死 Agent + 长上下文 + 高并发工具执行新增量。

## 关键数据点

- **Vera 规格**：88 Olympus 核 / 176 线程
- **内存**：最高 1.5TB LPDDR5X / 1.2TB/s 带宽（SOCAMM 模块化形态）
- **NVLink-C2C**：1.8TB/s 一致性
- **总线**：PCIe Gen6、CXL 3.1
- **vs Grace 升级方向**：缓存 / 内存容量 / 带宽 / C2C / I/O 全面升级，非堆核心
- **架构定位**：CPU 从「服务器配套」→「AI 工厂执行层 + 数据层」

## 关联连接

- [[NVDA US]] — 主体
- [[Vera Rubin]] — 平台
- [[AgenticAI]] — 负载范式变化驱动
- [[摘要-cpu-pricing-competitive-2026-06-01]] — 同日捆绑策略
- [[摘要-jensen-huang-vera-rubin-gtc-taipei-2026-06-01]] — GTC 演讲
- [[摘要-vera-cpu-share-roadmap-2026-06-03]] — 同主题 6/03 续
