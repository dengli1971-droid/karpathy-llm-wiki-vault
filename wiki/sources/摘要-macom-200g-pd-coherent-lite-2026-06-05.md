---
title: "摘要-MACOM-200G-PD格局-Driver-TIA-Coherent-Lite-NPO"
type: source
tags: [来源, 研究纪要, MACOM, 200G PD, TIA, Driver, NPO, XPO, Coherent-Lite, DSP绑定]
sources: [raw/研究纪要/光通信/2026-06-05 芯片大厂调研100G200G PD竞争格局及验证进展,当前产能及扩产规划,Coherent-Lite应用情况-聚焦博通住友通美MarvellSemtech英伟达.md]
date: 2026-06-05
origin: acecamptech.com
last_updated: 2026-06-07
---

## 核心摘要

MACOM 视角：**2025 光通信收入占总 30%**（TIA + Driver + PD）；**2025 + 2026 主要增量都是 200G PD**。**100G PD vs 200G PD 代际差异**：光敏面 10+μm → 7-8μm → 必须晶圆级透镜（高难度工艺）；100G PD 8-10 家供应商（芯世杰/光迅/云岭/长光华芯）单价降至几毛美金 MACOM 退出；**200G PD 全球仅 2 家通过认证：MACOM + 博通**；单价 **$2-3**（vs 100G $0.6-0.8 即 5-6×）；Die size 相近（350×350）成本增长小 → 毛利非常可观。**2026 200G PD 全行业需求 2 亿颗**（对应 2,500 万只 1.6T 模块）；MACOM 月产能 > 博通；**MACOM 极限产能 7,000-8,000 万颗 / 博通 4,000-6,000 万 = 合计满足市场 60%**。**衬底瓶颈**：MACOM 全部用住友 + 正导入通美未量产；新进入者（GCS / 希烽光电 / 滨松）2026 下半年量产 2027 占份额；**最终都竞争上游有限磷化铟衬底**。**MACOM 磷化铟厂产能利用率**：从需求爆发前 30%（25G DFB 为主）→ **60%+ 接近满产**；为 200G PD 暂停 100G EML/CW 交付。**2027 产能翻倍**计划。**TIA/Driver 与 DSP 绑定关系**：
- 400G/800G 单模：Marvell/Broadcom DSP 集成 Driver → MACOM 单模 Driver 份额 ~0
- 800G 多模 VCSEL：DSP 不集成 Driver → MACOM 多模 TIA+Driver 套片年 400-500 万套
- **2026 800G 模块 5,000 万只**（单模 4,000 万 + 多模 1,200 万）
- **1.6T NVIDIA DSP 不集成 Driver**（需外挂）→ MACOM 1.6T Driver 主对 NVIDIA 方案；Marvell/Broadcom DSP 仍集成
- 1.6T TIA：MACOM 比 Semtech 晚 1 月送样，2026 底量产；导入周期半年（模块厂 2-3 月 + CSP 2-3 月）

**Marvell 1.6T 性能弱于 Broadcom → 捆绑销售**（DSP + TIA 近免费 vs 单独买 Marvell TIA 很贵），锁客户。**NVIDIA 2026 1.6T 1,000 万只 → 2027 2,000+ 万只**；DSP 策略：40% 自研 DSP（2026 ~400 万模块）+ 60% 开放（模块厂自选 DSP，新易盛/旭创/Lumentum/Coherent）。**新产品定价策略**：二三供 20% 折让 + 50%+ 毛利率底线 + 60%+ 新产品目标。**NPO/XPO 技术要求大变**：
- 电芯片尺寸 -50% + 功耗 -30%
- **NPO 取消 DSP**（光引擎靠近 SerDes 直接驱动；64 通道 XPO 加 DSP 功耗 200-300W 过高）
- Driver 需集成 EQ 功能（CTLE 从 2-3dB 提到 8-10dB）
- TIA EQ 影响小（本来就 2-3dB）

**NPO 量产时点 2027H2**：MACOM Driver/TIA 重新设计样品 2026/10 推 + 测试 1-2 季度 → 2027H2 选定供应商。**NPO/XPO 倒装封装（PD 倒在 TIA 上或 TIA 倒在硅光）2.5D**：旭创等头部光模块厂自做。**NPO 取消 DSP → PD+TIA 套片销售**（如 50-60% 200G PD 份额带动 TIA 份额）。**北美 NPO 三玩家**：亚马逊 3.2T / NVIDIA NVLink 7.2T (8×9 矩阵) / 谷歌 6.4T；**Marvell-Google 旧 DSP 关系不再决定 NPO 份额**。**NPO 单 Driver $40-50 至 $70-80**。**NPO 2027 需求**：800-1,000 万只预期（早）。**TIA/Driver 价值演进**：8 通道 1.6T $20-30 → 32 通道 NPO 至少翻倍（虽单通道 -50%）；Driver $50-60（增 EQ 功能 +10%）。**锗硅工艺产能**：GF + ST + Tower 三家，4-6 月流片周期（不像 EML 50+ 周）。

**轻相干 Coherent-Lite**：MACOM 是 **Google 2.4T（2×1.2T）项目独家 Driver+TIA 供应商**；亚马逊 400G/800G 轻相干（800G = 2×400G）；轻相干 vs ZR 关键区别：CW 固定波长 vs 可调（96/120 波长）+ DSP 简化（10-20km 1310nm 零色散无需色散/非线性/PMD 补偿）。**MACOM 是相干技术核心优势**：华为受限前年采购 $5,000 万相干 Driver。**轻相干 TIA/Driver 套片价值远高于 PAM4**：PAM4 $20 vs 轻相干 ~$100+；800G ZR $7,000-8,000 vs 800G Coherent Lite $2,000-3,000；2.4T 轻相干 $4,000-5,000。**CW Laser**：MACOM 有产能但不推（产能不足，等 2027 释放后量产）。**SpaceX 业务**：射频功率放大器（地面基站类，特殊太空设计）；Wolfspeed 此前竞争者被 MACOM 收购。

## 关键数据点

- **200G PD 2026 全行业需求**：2 亿颗 / MACOM 7,000-8,000 万 + 博通 4,000-6,000 万 = 60% 满足
- **200G PD 单价**：$2-3（vs 100G $0.6-0.8 即 5-6×）
- **NVIDIA 1.6T**：2026 1,000 万 / 2027 2,000+ 万（40% 自 DSP / 60% 开放）
- **NPO 2027 需求**：800-1,000 万（早预期）
- **NPO 单 Driver**：$40-50 → $70-80
- **800G PAM4 TIA**：$20-30 / 32 通道 NPO 至少 $40-50（翻倍）
- **轻相干 2.4T 模块**：$4,000-5,000 / 套片 ~$100+
- **MACOM SpaceX**：Wolfspeed 收购入囊
- **磷化铟产能**：30% → 60%+（满产）

## 关联连接

- [[摘要-cpo-research-2028-3x-2026-06-05]] / [[摘要-cpo-ocs-supply-chain-2026-06-05]] / [[摘要-overseas-optical-cpo-2027-ramp-2026-06-05]] / [[摘要-overseas-optical-cpo-fiber-2026-06-05]] — 同日 CPO 系列
- [[MACOM]] — 主体
- [[200G PD]] / [[NPO Driver/TIA]] / [[Coherent-Lite]] — 概念
- [[AVGO US]] — 200G PD 二供 + 1.6T DSP
- [[MRVL US]] / [[Semtech]] — TIA 竞争
- [[NVDA US]] / [[GOOGL US]] / [[AMZN US]] — NPO 三大客户
- [[5802 JP]] — 住友磷化铟衬底
- [[688048 CH 长光华芯]] — 国内 100G PD
- [[002281 CH 光迅科技]] — 国内 PD 同业
- [[WOLF US]] — 被 MACOM 收购
- [[STM US]] / [[GFS US]] / [[TSEM US]] — 锗硅代工
- [[NPO]] / [[XPO]] / [[CPO]] / [[硅光]] — 上下游
- [[磷化铟]] — 衬底瓶颈
