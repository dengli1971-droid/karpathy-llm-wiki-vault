---
title: "摘要-谷歌TPU推理成本与ASIC差异化产能展望"
type: source
tags: [来源, 研究纪要, TPU, 谷歌, ASIC, 推理成本, NVIDIA, CoWoS, 博通, 联发科, Marvell]
sources: [raw/研究纪要/半导体/2026-06-02 谷歌TPU推理成本分析，与其他ASIC差异化及未来产能展望.md]
date: 2026-06-02
origin: acecamptech.com
last_updated: 2026-06-07
---

## 核心摘要

**TPU v7 单 token 推理总成本 = NVIDIA GB300 的 1/3**（含算力+功耗+网络+折旧）。**TPU 单芯 ~$8,000 vs NVIDIA GPU $30,000+**（1/4 价）。成本优势来源：(1) 架构专用化（针对 Gemini 深度优化，可去除 50% 冗余晶体管，算力利用率 90-95% vs GPU ~70%）；(2) Google 不收高毛利（NVIDIA 70-80% 毛利 vs Google 自用 + 云服务）。**护城河**：规模效应 + 高切换成本 + 深度绑定博通/联发科/Marvell 封闭生态 → 客户跨平台迁移难。**2027 TPU 出货千万颗级**。**核心瓶颈：CoWoS 产能**——NVIDIA 占台积电 60%+，谷歌计划 20-30% 产能外放给 Intel 18A + 利用联发科代工配额变相扩产。

## 关键数据点

- **TPU v7 单 token 成本 vs GB300**：1/3
- **TPU v7 单芯**：$8,000
- **NVIDIA GPU 单芯**：$30,000+
- **TPU 利用率 Gemini**：90-95%
- **TPU 冗余晶体管节省**：50%
- **NVIDIA 毛利率**：70-80%
- **2027 TPU 出货**：~千万颗级别
- **CoWoS 产能瓶颈**：NVIDIA 占 60%+
- **谷歌产能外放计划**：20-30% Intel 18A

## 关联连接

- [[TPU]] / [[Google]] — 主体
- [[NVDA US]] — 对标
- [[AVGO US]] / [[MRVL US]] / [[2454 TT]] — 绑定生态
- [[CoWoS]] / [[INTC US]] — 产能外放
- [[摘要-asic-broadcom-openai-google-tpu-2026-06-01]] — 同主题 6/01
- [[摘要-google-liquid-cooling-pcb-2026-06-02]] — 同日 GoogIe 液冷
- [[摘要-tpu-emib-rubin-ultra-2026-06-05]] — 6/05 EMIB Rubin
