---
title: "摘要-DeepSeek技术对存储CPU影响 LPU内存池化"
type: source
tags: [来源, 研究纪要, DeepSeek, KV cache, DRAM, NAND, SSD, LPU, 内存池化, CXL, Astera Labs, Cerebras WSE-4]
sources: [raw/研究纪要/半导体/2026-06-03 DeepSeek技术创新对存内存需求影响，CPU价格或陷入价格战。英伟达LPU内存池化的实现，Cerebras WSE-4性能提升、对OSC的采用可能、需求展望.md]
date: 2026-06-03
origin: acecamptech.com
last_updated: 2026-06-07
---

## 核心摘要

**DeepSeek V4 KV Cache 缩减 90%（仅 6GB 即可推理）**，重要性堪比 Attention 机制创新，2026Q3 主流模型普遍跟进。对存储影响：**DRAM 短期需求波动风险**（KV Cache 不再大量占 DRAM），**NAND 利好**（依赖 SSD + In-Graph Memory 体系架构替代 DDR）。长江存储 2026H2-2027 产能释放进一步利好 NAND。**CPU 不涨反入价格战**：至强四/五等老 CPU 2029 仍可胜任 AI；CSP 看 TCO 不看采购价；新一代 CPU 线程数 2-3x 速度增长 vs 业务 3-5x 增长 → 快速平衡。**内存池化大趋势**：(1) 谷歌 FFN + Marvell 配套 2026 末-2027 Q1；(2) 英伟达 LPU + Astera Labs PCIe Gen7 CXL 池化接口（LP-35 型号支持 PCIe 4.0）；(3) 亚马逊类似项目。**LPU 演进**：LP-30（Groq 收购）→ LP-35 把 CPU 移出 LPU 机柜，PCIe 通道与远端 CPU 机柜互联 → CPU + CXL 池化存储柜需求增加。**Cerebras WSE-4**：性能持续提升，可能采用 OSC（光学 SerDes）。

## 关键数据点

- **DeepSeek V4 KV Cache**：6GB（缩减 ~90%）
- **CPU 价格走势**：价格战
- **新 CPU 线程数增长**：2-3x
- **业务需求增长**：3-5x
- **LPU SRAM 容量**：500MB / 颗
- **LPU 机柜配置**：8 LPU + 1 Intel CPU（LP-30）→ 移出 CPU（LP-35）
- **谷歌 FFN + Marvell 配套**：2026Q4-2027Q1

## 关联连接

- [[DeepSeek]] / [[KV cache]] — 创新核心
- [[LPU]] / [[Cerebras]] — 推理芯片
- [[Astera Labs]] / [[CXL]] / [[内存池化]] — 概念
- [[长江存储]] — 国产 NAND
- [[摘要-llm-context-agent-storage-cpu-2026-06-01]] — 同主题 6/01
- [[摘要-3d-dram-photon-2026-06-05]] — 6/05 3D DRAM
