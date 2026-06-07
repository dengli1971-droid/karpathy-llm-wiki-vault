---
title: "摘要-电源芯片大厂 DrMOS 格局 + FIVR 趋势 + SST 带动"
type: source
tags: [来源, 研究纪要, DrMOS, FIVR, SST, Vicor, 英飞凌, 瑞萨, MPS, ADI, TI, 维谛, 台达, 杰华特]
sources: [raw/研究纪要/半导体/2026-06-05 电源芯片大厂调研DrMOS市场竞争格局,FIVR技术发展趋势,SST需求及带动作用-聚焦英飞凌瑞达ADIVicorTI维谛台达阳光伊顿杰华特纳芯微等.md]
date: 2026-06-05
origin: acecamptech.com
last_updated: 2026-06-07
---

## 核心摘要

**DrMOS 在 NVDA Rubin/Rubin Ultra 仍是主流（多相控制器 + DrMOS）+ 自研 ASIC 也大部分沿用**。**FIVR 是潜在替代（CMOS 工艺 vs DrMOS 模拟 BCD 90/60nm + MIM 电容 + 空心电感）**：Intel 2015 推过 300W 案例 + 苹果 MacBook ARM 主芯用过几十瓦 FIVR，但 300W+ 高功率 FIVR 散热挑战巨大（开关频率 50-100x DrMOS / 体积 1/50 / 损耗 +50x），3-5 年内难落地，Feynman 也来不及；TSMC/三星/Empower（被 ADI 收购）也研发中。**Rubin/Ultra 供应商延续 MPS + IFX + 瑞萨**（AOS 已被淘汰发热劣势）；**Vicor 方案封闭、价格 1-2x、A100 历史曾用后弃**——即便授权也不会回；其优势 = 末级更薄高效低耗，劣势 = 响应速度不如 DrMOS 并联 + 生态封闭。**单机柜 DrMOS 用量**：18 层 × 300 颗（计算托盘）+ 300 颗（交换托盘）= **6000 颗 × 1.5 美元 ≈ 9000 美元 + 电感/电容 → 1 万+ 美元/机柜**；Rubin 单层升到 360 颗。**SST 取代 5.5kW 一级电源（800V 直接到 12V）**；高压电源转换简化但不侵蚀 DrMOS（耐压 20-30V 完全不同领域）。**GaN 12V→1V 良率为主要瓶颈 + EMI 紧邻 GPU 难解 → 主流厂商不投入**，仅英诺赛科推全 GaN 方案。**模拟芯片 2025 H2 触底回升**：TI 三次涨价已落地，工业储能（地缘政治油价 + 电力紧张）+ 智能化（L2 下沉 10 万元车型）+ 数据中心 + 成本端铜银涨价 + 逻辑/存储挤占模拟产能。**产能瓶颈**：IDM 扩产 2-3 年 / Fabless 1-1.5 年；公司规划支撑 40 亿美元营收 + 60 亿规划。

## 关键数据点

- **Rubin 单机柜 DrMOS 用量**：6000 颗（5400 计算 + 600 交换）
- **DrMOS 单价**：1-2 美元（取中 1.5）
- **机柜 DrMOS 总价值**：~9000 美元 + 电感/电容 → 1 万+
- **GPU 功耗演进**：1.24kW → 1.4kW → 2.3kW（Rubin）
- **SiC IGBT Vicor 价格倍数**：1-2x DrMOS
- **FIVR 商业化时间**：3-5 年+（Feynman 来不及）
- **公司产能规划**：40 亿美元 / 60 亿规划

## 关联连接

- [[DRMOS]] / [[800V HVDC]] — 概念
- [[摘要-rubin-power-chain-2026-06-05]] — 同日 18.3kW
- [[摘要-ai-psu-hvdc-google-2026-06-05]] — 同日 PSU/HVDC
- [[摘要-psu-power-architecture-2026-06-05]] — 同日 GaN/SiC
- [[摘要-domestic-drmos-suppliers-2026-06-02]] — 6/02 国产
- [[摘要-drmos-expert-2026-06-04]] — 6/04 DrMOS 国产突破
- [[IFX GY]] / [[6723 JP]] / [[ADI US]] / [[TXN US]] / [[688141 CH 杰华特]]
