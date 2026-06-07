---
title: "摘要-PSU 功率器件与架构演进 GaN/SiC + 转换层级"
type: source
tags: [来源, 研究纪要, PSU, GaN, SiC, 800V HVDC, SST, 近芯片侧供电, 英诺赛科, TI, MPS, 英飞凌]
sources: [raw/研究纪要/半导体/2026-06-05 PSU功率器件与架构演进调研 GaN在8kW以上PSU中的用量提升, HVDCSST转换层级减少与近芯片侧供电, SiC标配范围及高功率PSU单瓦价值变化 - .md]
date: 2026-06-05
origin: acecamptech.com
last_updated: 2026-06-07
---

## 核心摘要

**GaN 在 8kW 以上 PSU 渗透阶梯**：5.5kW 没用 / 8kW 4 颗（价值占功率器件 25%）/ 12kW 8 颗 / 18kW 12 颗（占 50%）。**HVDC GaN 非标配（SiC 才是）**，但 GaN 让 2.4MW HVDC 占地从 300 平米降到 100 平米 + 效率从 95% 提到 97.5%。**近芯片侧供电是 GaN 新战场**（TI/MPS/IFX/英诺赛科已出方案 800V→50V / 12V / 6V → 1V），原因是高频高效率 + 体积压缩 + 散热低。**终极方案 = 800V→1V 一级转换**（合并 1/2/3 级）。**电源转换层级 2030 vs 2026 减半-减 1/3**：SST 普及后 AC 进直接 800V，UPS 三次转换简化到一次（减 2/3）。**推理 ASIC 单芯片功耗 2030 vs 2026 = ~2x（CAGR 20%）**。**PSU 单瓦价格演进非线性**：18.3kW 反而比 12kW 单瓦便宜（空间从 1U 到 3U，碳化硅可少用换硅基 MOSFET + 大磁元件，每瓦降 1+ 美分）。**5.5kW 整机谷歌批发价 ~3600 RMB / BOM ~2000 RMB（30%）；18.3kW BOM 占比可达 40%**。**SiC 渗透**：5.5kW+ 标配、3kW 以下 <10% 占特殊场景；5.5kW SiC 占材料成本 5%。

## 关键数据点

- **GaN PSU 用量**：5.5kW 0 / 8kW 4 / 12kW 8 / 18kW 12
- **GaN 价值占功率器件**：8kW 25% / 18.3kW 50%
- **HVDC GaN 占地优化**：300→100 平米
- **效率**：95% → 97.5%（用 GaN）
- **5.5kW 整机售价/BOM**：3600 / 2000 RMB（30%）
- **18.3kW BOM 占比**：30-40%
- **5.5kW SiC 占材料成本**：5%
- **2030 vs 2026 转换层级**：减少 1/3-1/2
- **2030 推理 ASIC 单芯片功耗**：~2x（CAGR 20%）

## 关联连接

- [[800V HVDC]] — 架构概念
- [[摘要-ai-psu-hvdc-google-2026-06-05]] — 同日 PSU/HVDC
- [[摘要-rubin-power-chain-2026-06-05]] — 同日 18.3kW Rubin
- [[摘要-power-chip-drmos-fivr-2026-06-05]] — 同日 DrMOS/FIVR/SST
- [[摘要-sic-allocation-tam-2026-06-04]] — 6/04 SiC TAM 测算
- [[GOOGL US]] / [[NVDA US]] / [[IFX GY]] / [[TXN US]]
