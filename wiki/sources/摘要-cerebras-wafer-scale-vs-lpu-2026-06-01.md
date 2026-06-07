---
title: "摘要-Cerebras晶圆级芯片技术创新与LPU路径对比"
type: source
tags: [来源, 研究纪要, Cerebras, 晶圆级, LPU, AI推理, AI训练, OpenAI, AWS]
sources: [raw/研究纪要/半导体/2026-06-01 Cerebras调研：晶圆级芯片方案技术创新点以及局限性，与LPU路径使用场景对比，与OpenAI和AWS合作背景及影响.md]
date: 2026-06-01
origin: acecamptech.com
last_updated: 2026-06-07
---

## 核心摘要

Cerebras 是首家成功量产晶圆级芯片（WSE）的公司，与台积电协同开发——但**不是真正的 System-on-Wafer**（没有 3D 封装/异构集成），核心创新是在传统划片线位埋金属通信线路把所有 die 连成整晶圆。良率近 100%（设计可旁路屏蔽损坏 core），近 90 万个微小 core + 超小 SRAM 单体。**致命架构缺陷**：单片晶圆 SRAM 容量不够装万亿参数大模型，必须跨晶圆通信，但跨晶圆带宽比片上慢数百倍（"小院高墙"），训练/推理都遇瓶颈。**结论：LPU > Cerebras** 在大模型场景，LPU 的层级化片间高速 IO 更适合万亿参数；Cerebras 只在单片承载全模型 + 计算图高度优化的小众场景才优。台积电 SoW 路线图量产时间 2030+，印证当前技术难度。OpenAI/AWS 选择 Cerebras 主要是供应链多元化考量，不构成对 GPU/LPU 的实质性替代。

## 关键数据点

- **晶圆级 core 数**：~90 万个微小 core
- **片上带宽**：~100x LPU 片间带宽
- **跨晶圆带宽下降**：数百倍
- **SoW 量产时间**：2030+（台积电）
- **历史**：90 年代 Amdahl 失败，Cerebras 首家成功
- **5x5 矩阵封装方案**：25 大裸片 + 40 IO die，仍未突破

## 关联连接

- [[Cerebras]] — 主体公司
- [[2330 TT  TSMC]] — 协同开发方
- [[LPU]] — 对标技术路径
- [[OpenAI]] / [[AWS]] — 客户
- [[摘要-cerebras-vs-gpu-inference-2026-06-02]] — 同主题 6/02 续篇
