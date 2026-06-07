---
title: "摘要-卖方逻辑漏洞-SST/HVDC/液冷规模依赖-三档TCO临界"
type: source
tags: [来源, 研究纪要, SST, HVDC, 液冷, TCO, LDT, 巴拿马电源, 阳光电源, 金盘科技, 800V, 排他替代, 规模绑定]
sources: [raw/研究纪要/AI与云计算/2026-06-06 卖方同时唱多SST、HVDC、液冷，这在逻辑上存在漏洞.md]
date: 2026-06-06
origin: acecamptech.com
last_updated: 2026-06-07
---

## 核心摘要

**反共识深度**：卖方同时唱多 SST/HVDC/液冷存在逻辑漏洞——三者**规模依赖排他替代**而非并驾齐驱。**核心物理约束**：48V 直流母线在 130kW 机柜时电流爆炸（1MW 需 20,833A、铜母排 200kg+ 占机柜 60% 空间） → 800V HVDC 是行业唯一技术共识，分歧仅在"谁实现 800V"。**三档 TCO 模型**：
- **100MW LDT 主场**：单机柜 20-50kW、CapEx 敏感首要；LDT ¥1/W vs SST ¥7-8/W → 100MW 园区初始差距 ¥6-7 亿；SST 2-3% 效率年省 ¥2,000 万 → **回本 30 年+ 财务破产**。
- **500MW HVDC 黄金区**：单机柜 100kW、48V 失效；**SST 摊薄成本不够 → "巴拿马电源"（工频变压器 + 800V HVDC 整流柜）**最优；停机损失高（顶级训练集群每小时几十-几百万美元），HVDC 减少链路故障节点降维护 90% → 可靠性溢价 > 能耗节约；100% CDU 冷板液冷与 HVDC 前置刚需共组成 500MW 标配。
- **1GW SST 降维打击**：北美 Hyperscaler AI 工厂、TCO 最高变量=物理空间机会成本；SST 高频化释放 IT 计算空间 ~10%（工程估算）→ 多部署数万 GPU/NPU 年增数十亿算力收入 → CapEx 溢价被抹平、回收 3-5 年；SST 直出 800V + 浸没/两相液冷 = 唯一经济。**时间维度非对称**：800V HVDC 2025 起量元年（5 年 CAGR 高两位数）；**SST 商业化 2030-31**（负载端=GPU/ASIC 原生支持 800V 直流要等 PSU 架构代际切换；部分机构看 2027 北美小批商业招标/2028-29 规模采购但分歧大）；**SST 作为近期催化剂是严重时间错位**。**A 股映射规模绑定**：阳光电源（三档通吃 SST+大容量 BESS 储能 1GW 政策强配）/ 金盘科技（最纯 SST 长期期权 10kV/2.4MW 样机+针对北美 800V，营收 2027-28 才形成）/ 思源电气+麦格米特（500V 架构北美 Hyperscaler 绑定）。

## 关键数据点
- 物理约束：48V 输 1MW 需 20,833A 铜排 200kg+
- 800V 电流降 1/17 / 铜截面减 85% / 效率 90-95% → 97.5%
- LDT ¥1/W vs SST ¥7-8/W；100MW 初始差 ¥6-7 亿
- SST 100MW 回本 30 年+（财务破产）
- 顶级训练集群停机损 = 每小时几十-几百万美元
- HVDC 减少故障节点 → 维护 -90%
- 1GW SST 释放 IT 空间 ~10%
- 1GW 算力百亿美元 / 多部署 GPU 年增数十亿美元收入
- 800V HVDC 5 年 CAGR 高两位数
- SST 规模化营收 2030-31

## 关联连接
- [[摘要-ai-infra-2027h2-supply-demand-reversal-2026-06-06]] — 2027H2 拐点（已 ingest）
- [[摘要-cyclic-extreme-ai-rotation-2026-06-07]] — 阶段性极限 AI 链（已 ingest）
- [[摘要-ai-power-sic-bottleneck-2026-06-04]] — SiC TAM（已 ingest）
- [[摘要-sic-allocation-tam-2026-06-04]] — SiC 分货 + SST/PSU/BBU（已 ingest）
- [[摘要-ai-psu-hvdc-google-2026-06-05]] — PSU/HVDC 谷歌（已 ingest）
- [[摘要-rubin-power-chain-2026-06-05]] — Rubin 电源链（已 ingest）
- [[摘要-server-cooling-rubin-2026-06-05]] — Rubin 散热（已 ingest）
- [[摘要-liquid-cooling-supply-chain-2026-06-03]] — 液冷价值量（同批次）
- [[摘要-nvda-customer-concentration-70-2026-06-02]] — 资金回路风险
- [[摘要-coreweave-duration-mismatch-2026-06-03]] — 久期错配
- [[800V HVDC]] / [[正交背板]] — 概念
- [[Beta_Alpha锚点框架]] — Alpha=电压×电流物理约束；Beta=AI Capex 笼统押注
- [[芒格思维模型]] — "并列推荐"=破坏性竞争反例（产业链应有内部替代关系）
