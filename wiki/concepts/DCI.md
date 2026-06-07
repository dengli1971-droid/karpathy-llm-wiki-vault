---
title: "DCI"
type: concept
tags: [光通信, 相干光, EDFA, scale-across, 数据中心互联]
sources:
  - raw/研究纪要/光通信/2026-06-01 光通信产业链调研：DCI与CPO驱动芯片缺口，1.6T龙头优势稳固.md
  - raw/研究纪要/光通信/2026-06-02 DCI大厂调研相关光模块需求量趋势及竞争格局,扩产及物料瓶颈,Scale-across增速预期-聚焦诺基亚思科LumentumCoherent德科立昂纳富士通古.md
last_updated: 2026-06-07
---

## 定义

**DCI（Data Center Interconnect，数据中心互联）** 是数据中心之间（跨园区/跨城）的高速光传输互联场景，采用 **相干光技术 + EDFA 光放大** 实现 40-60km 甚至跨州距离传输，区别于数据中心内部的可插拔光模块（短距）和 [[CPO]] / [[NPO]] / [[OCS]]（机柜内）。**Coherent 2026 OFC 投资者报告明确 DCI 为光通信四大独立技术方向之一**（与可插拔/OCS/CPO 并列）。

## 关键信息

### 需求爆发逻辑（Scale-Across）

- 各大 CSP 早期建数据中心地理分散，现需将同州/同地区数据中心互联以支持大规模训练 + 推理
- **三年集中投资期 2026-2028**
- 谷歌投资 $60 亿
- Oracle 投资 $20-30 亿
- Meta/AWS/Azure 同步推进

### 市场规模

- **三年总市场 ~$200 亿**（2026-2028）
- 相干光模块 2026-27 翻倍
- CAGR **30-50%**

### 受益玩家

#### 海外
- **[[COHR US]]**（市场份额最大，自产 EDFA + 自有 980nm 泵浦）
- **[[LITE US]]**（CW + 泵浦激光器供应商，拟涨价 50%+）

#### 国内（A 股直接受益）
- **[[002281 CH 光迅科技]]**（EDFA 30% 全球份额；客户 Nokia/Ciena/Cisco；自研 MEMS OCS 整机）
- **德科立**（EDFA 15% 全球份额；可代工 Ciena/Nokia）
- 旭创/新易盛布局 DCI 相干光模块作为四方向之一

### 产业链关键环节

#### 980nm 泵浦激光器（EDFA 核心）

- 月需求 10-12 万颗（+50%）
- 供应：Coherent 5.5 万 + Lumentum 4.5 万 + 华为不外供 = 10 万
- Lumentum 拟涨价 **50%+**
- Coherent 已停售芯片自用 EDFA → 推高市场价

#### EDFA 整机

- 单价 $800-2,000
- 年需求 2026 100 万 → 2027 150 万 → 2028 200 万
- multi-rail 系统每 EDFA 用 1-2 个 980nm 泵浦

#### 光纤
- 长飞光纤已进北美供应链
- 亨通/中天/永鼎候选（关键是 NA 客户认证）
- 通信级空心光纤（百亿美金潜力）：24/32 芯 40-60km 距离 $4,000-7,000/公里；微软-康宁-贺利氏 vs 亚马逊-谷歌-长飞-Relativity Networks-领纤

#### 与电信光模块的关系

- 主要玩家：Ciena + Nokia（电信背景）
- 进入壁垒高（技术平台特殊）
- 剑桥科技/联特科技无机会
- 德科立通过为 Ciena/Nokia 代工切入

## 与其他技术方向的边界

| 方向 | 距离 | 形态 | 主流玩家 |
|---|---|---|---|
| 可插拔光模块 | 数据中心内（米级 - 公里）| QSFP/OSFP/CPO | 旭创/新易盛/Coherent/Lumentum |
| [[OCS]] | 机柜间全光路由 | MEMS/液晶 | Google/光迅 |
| [[CPO]] / [[NPO]] | 机柜内 / 板间 | 共封装 | NVIDIA + 三组供应商 |
| **DCI（本概念）** | 数据中心间（40-60km+）| **相干光 + EDFA + multi-rail** | Ciena/Nokia/Coherent/光迅/德科立 |

## 关联连接

- [[摘要-optical-industry-dci-cpo-1.6t-2026-06-01]] — 主要论证来源
- [[摘要-dci-research-2026-06-02]] — DCI 大厂调研（待 ingest）
- [[EDFA]] — 概念页（核心硬件）
- [[CPO]] / [[NPO]] / [[OCS]] / [[OpticalCommunication]] — 四方向之一
- [[CW光源]] — 980nm 泵浦激光器是 EDFA 核心
- [[空心光纤]] — DCI 长距应用
- [[002281 CH 光迅科技]] / [[德科立]] / [[COHR US]] / [[LITE US]] — 受益玩家
- [[GOOGL US]] / [[META US]] / [[MSFT US]] / [[AMZN US]] — 投资方
