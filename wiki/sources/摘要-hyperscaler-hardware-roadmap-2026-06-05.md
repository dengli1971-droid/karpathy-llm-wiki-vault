---
title: "摘要-Hyperscaler硬件-MTIA-Arista-1.6T-NPO-CPO-DRAM-NAND"
type: source
tags: [来源, 研究纪要, MTIA, Hyperscaler, Arista, DRAM, NAND, NPO, CPO, 1.6T, ZR, Coherent-DCI]
sources: [raw/研究纪要/光通信/2026-06-05 Hyperscaler hardware progress in custom silicon roadmaps, server storage supply .md]
date: 2026-06-05
origin: acecamptech.com
last_updated: 2026-06-07
---

## 核心摘要

Meta 硬件视角 Hyperscaler 大型综合：**MTIA 2026 几十万颗**（不是失败而是放慢）：MTIA 200（已生产 ranking/recommendation）+ MTIA 300（2026 主爬坡，主力体量）+ MTIA 400（小初始）；MTIA 400/450/500 2026 晚-2027 Broadcom 多年首阶段部署。**Broadcom ASIC 定价**：compute die（不含 HBM）low-mid $1K；packaged advanced $10K-；full XPU with HBM **$15K-20K+**；MTIA 200 < 300 < 400（die 面积 + I/O + 封装复杂度递增）。**GPU:CPU 配比**：current 4-8:1；frontier 训练 8 GPU:1-2 x86 2026 → 2028 不变；标准 LLM 推理 8:1 → 8-12:1；agentic 5:1 → 8:1；自定义 MTIA 推理 6:1 → 12:1；**agentic 比 chat 更需 CPU**。**DRAM 2026Q2 价格**：HBM3e (12-high) QoQ **+12-20%**；DDR5 RDIMM 128-256GB +8-15%；blended +6-10%。**LTA 四大要素**：12-24 月 forward visibility + take-or-pay 带 +/- 10-15% flex；预付 10-20%（HBM 战略 $1-3 billion 资本预承诺）；公式价格（base floor + quarterly index + yield/stack adjustment）；分散供应 SK Hynix 45-55% + Samsung 25-35% + Micron 15-25%。**DRAM 计算**：bottom-up（GPU host 1.5-3TB / MTIA 推理 host 512GB-1TB / 1P ARM web 384-768GB / 2P x86 1-2TB）+ top-down（4B chat queries + 300M agentic workflows × 0.4-30 vCPU/秒 × 2-32 GB/vCPU）= 2027 目标 **2 exabytes**。**CXL 2027 重要起来**减 stranded memory 10-20%；**Astera Labs 早期领先** + Broadcom 强竞争 + Microchip/Marvell + Rambus/Montage 次之。**SSD**：Q2 2026 NAND 合约价 +70-75% QoQ；2026 90-130 EB（+55-75% YoY）→ 2027 140-210 EB（+50-65% YoY）；**QLC 主导 AI bulk** + TLC checkpointing/cache。**QLC 122TB+ $0.05-0.08/GB**；TLC $0.09-0.14；hybrid SLC/TLC $0.18-0.30。**AMD GPU 部署**：MI350 2026 几万 → 2027 1-3 万；MI400 2026 ~10 万 → 2027 20+ 万（main 平台）；MI450 2026 ~0 → 2027 10 万；ASP $21K/25K/31K。**Arista 支出**：2025 $4B → 2026 $6-9B（+50%）→ 2027 $7-9B+ → 光模块（800G/1.6T）是主要 gating；800G ASIC 封装 + SerDes（最严）；CPO readiness 中等；PSU/电源中等；**Arista chassis 通常有 + 800G/1.6T 不够**。**lead times**：800G optics 20-32 周 / DAC/AEC 12-20 / switch 16-26；**1.6T optics 36-52 周 + switch 30-45 周**（约 9-12 月）。**光模块价格**：800G SR 几百 / DR-FR ~$1,000 / ZR Coherent DCI 几千；1.6T SR 1,000s / FR 几千 / Coherent DCI **$高千-低万**。**1.6T 玩家份额演进**：2026 Coherent 25-35% > InnoLight 20-30% > Eoptolink 10-18% > Lumentum/CloudLight 10-15% > 海信/Source Photonics 5-10% > Fabrinet 生态 8-12%；2028 Coherent 降 18-25% / **InnoLight 升 25-35%** / Eoptolink 升 15-22%。**1.6T ZR coherent DCI Meta 主供**：Coherent 25-35% / Ciena WaveLogic 20-30% / Cisco Acacia 15-25%（选择由 DSP 成熟度 + 功耗 + 长距可靠性而非成本主导）；**Lumentum 不直接出 ZR 整模块**（无 coherent DSP，只供 EML/tunable lasers/光学子组件 BOM）。**Nokia 1.6T 不增**因 operational inertia + DSP 性能一致性 + 故意分散策略。**下个 DCI RFQ**：$1.5-2.5B（1.6T optics $700M-1.1B；8 万-14 万只 1.6T 模块）；Q3-Q4 2026 投标 → 2026 末 down-select → Q4-Q1 2027 PO → 2027H2 出货。**Inventory 部署优先**：①AI GPU/MTIA back-end ②新 AI 训练 + 高密推理 ③DCI AI 园区间 ④front-end leaf/spine ⑤legacy；**透明储备 6-12 个月光模块属合理**。**Pluggable→NPO→CPO 时间线 2026-2028**：800G pluggable 2026 主流 / 2027 高量 / 2028 渐熟；1.6T 2026 早 / 2027 主 / 2028 主；**NPO 2026 lab/pilot → 2027 first meaningful → 2028 selective production（2027 6 万只 / 2028 25 万只）**；**CPO 2026 evaluation → 2027 limited switch fabric pilots → 2028 早产 high-density only（2027 1 万 / 2028 7 万）**；**2027 NPO 85-90% vs CPO 10-15%**；**2028 NPO 75% vs CPO 25%**；CPO 故障难换 → NPO ramp 快。

## 关键数据点

- **MTIA 2026**：几十万颗；MTIA 300 主体；MTIA 400/450/500 2026 末-2027 出
- **Broadcom XPU ASP**：full with HBM $15-20K+
- **DRAM Q2 2026 涨价**：HBM3e +12-20% / DDR5 RDIMM +8-15%
- **NAND Q2 2026**：+70-75% QoQ
- **NAND 需求**：2026 90-130EB → 2027 140-210EB
- **Arista CapEx**：2025 $4B → 2026 $6-9B → 2027 $7-9B+
- **800G/1.6T lead time**：800G optics 20-32 周 / 1.6T 36-52 周
- **1.6T 玩家**：Coherent 25-35% → 2028 18-25%；InnoLight 20-30% → 25-35%
- **DCI RFQ 2027 部署**：$1.5-2.5B / 8-14 万只 1.6T；2027H2 ship
- **NPO 2027 vs CPO**：85-90% vs 10-15%；2028 75% vs 25%
- **NPO 部署**：2027 6 万 → 2028 25 万；CPO 2027 1 万 → 2028 7 万

## 关联连接

- [[摘要-cpo-ocs-supply-chain-2026-06-05]] / [[摘要-cpo-research-2028-3x-2026-06-05]] — 同日 CPO/ELS 详情
- [[摘要-overseas-optical-cpo-2027-2026-06-05]] — 海外大厂 CPO 2027（待 ingest）
- [[CPO]] / [[NPO]] / [[ELSFP]] / [[FAU]] / [[DCI]] / [[EDFA]] — 概念
- [[META US]] / [[AVGO US]] / [[NVDA US]] / [[AMD US]] — 主体
- [[Astera Labs]] / [[Marvell]] / [[Rambus]] — CXL
- [[000660 KS SK Hynix]] / [[005930 KS]] / [[MU US]] — DRAM/HBM
- [[Arista]] / [[InnoLight]] / [[Eoptolink]] / [[Hisense]] — 网络 + 光模块
