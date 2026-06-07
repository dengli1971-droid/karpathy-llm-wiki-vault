---
title: "摘要-高通 AWS AI200 + Marvell TPU v9 + OpenAI ASIC + MAIA200 + EMIB"
type: source
tags: [来源, 研究纪要, 高通, AWS, AI200, Trainium, Marvell, TPU v9, OpenAI ASIC, Anthropic, MAIA200, EMIB, 海力士, CoreWeave, IREN, Nebius, Neocloud]
sources: [raw/研究纪要/半导体/2026-06-05 高通或向AWS供应AI200搭配Trainium，Neocloud资源扩张和获客进展。Marvell在TPU v9的合作内容，OpenAI ASIC回片反馈，A.md]
date: 2026-06-05
origin: acecamptech.com
last_updated: 2026-06-07
---

## 核心摘要

**高通向 AWS 提供两套芯片**：(1) AI200 推理（小批量 2026 起，对接 Bedrock 模型库，<100B 参数模型补 AWS 推理算力缺口，因 Anthropic 占用 Trainium 大量产能）+ (2) Echo SOC（家庭网关音箱，turnkey 定制）。**AI250 2027 推出，算力规格大幅提升**；**风险**：AWS 2027 Trainium 是否上量挤占；高通与字节合作 = 部分交钥匙（核心 IP 字节自带避美政府 IP 转移禁令）。**Marvell 与谷歌 TPU**：V8 已设计完成，**Marvell 主导 V9 近存计算（增 SRAM 空间 vs Cerebras）+ scale-out 网络方案**，但 V9 最终代工 = 博通 vs MTK vs Marvell 谷歌还在谈（博通已确定继续），Marvell 主要提供 IP 不独立设计整颗。**OpenAI ASIC（博通）已回片 = 7 月中下旬交付 OpenAI 测试 2-3 个月 → Q4 小批量 + 2027 量产**（节奏未提速，先推理后训练）。**Anthropic 与微软 MAIA200**：性能接近 B200（功耗 <1000W vs B200 1000W），支持 IP8/IP4 低精度 + 系统互联；MAIA100 已部署 3000 颗、MAIA200 2026 下半年小规模、2027 上量；微软策略 = Azure 提供 Anthropic Claude API + Copilot 接入 Claude 跑 MAIA。**Intel EMIB 产能**：新墨西哥月产 28-29k 片（先进封装厂、扩到 4 万 2027 + 30-40%）；马来传统转 EMIB（13-14k → 30k 2027）；越南只做传统封装；爱尔兰只做晶圆。**EMIB 授权三星**：2026 底 小批量、2027 快速放量（谷歌 TPU + AMD MI500 + 特斯拉 + 其他）；英特尔仅赚授权费、三星拿大头。**海力士 HBM4 + Intel EMIB 整体封装验证中**（Vera Rubin 小批量、谷歌/AMD/CSP 后续可能采用）。**高通下一代 AI200 也用 EMIB 封装**（TSMC 拿不到更多产能）。

## 关键数据点

- **高通 AI200 AWS 部署节奏**：2026 小批量 / 2027 AI250 升级
- **高通 AWS 服务模型规模**：<100B 参数
- **MAIA100 部署量**：3000 颗
- **MAIA200 功耗**：<1000W（vs B200 1000W）
- **Intel 新墨西哥 EMIB 月产能**：28-29k 片 → 4 万 2027
- **Intel 马来 EMIB**：13-14k → 30k 2027
- **OpenAI ASIC 节奏**：Q4 2026 小批量 / 2027 量产
- **EMIB 三星授权放量时间**：2027

## 关联连接

- [[摘要-na-asic-3-qualcomm-npu-2026-06-04]] — 6/04 高通 AI200 端侧 AI
- [[摘要-intel-18a-emib-rubin-ultra-2026-06-05]] — 同日 Intel 18A/EMIB
- [[摘要-asic-broadcom-openai-google-tpu-2026-06-01]] — 6/01 博通 ASIC
- [[摘要-top-csp-capex-self-chip-2026-06-01]] — 6/01 CSP 自研
- [[QCOM US]] / [[AMZN US]] / [[MRVL US]] / [[GOOGL US]] / [[AVGO US]] / [[MSFT US]] / [[INTC US]] / [[000660 KS]] / [[005930 KS]] / [[CRWV US]] / [[IREN US]] / [[NBIS US]]
