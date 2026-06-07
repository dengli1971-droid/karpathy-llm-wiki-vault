---
title: "摘要-日系电容专家-北美CSP导入流程-LIC-Sidecar-平台电压"
type: source
tags: [来源, 研究纪要, 超级电容, LIC, EDLC, 武藏精密, 北美CSP, MSFT, Meta, GOOG, NVDA, GB200, SST, HVDC, 巴拿马电源]
sources: [raw/研究纪要/AI与云计算/2026-06-03 日系电容专家谈北美客户导入流程、CSP进展及扩产等.md]
date: 2026-06-03
origin: acecamptech.com
last_updated: 2026-06-07
---

## 核心摘要

日系电容（武藏）专家北美 CSP 导入流程更新。**国内尚无订单**仅 design-in 阶段——产品性价比 + 产能限制；北美订单巨大优先。**导入流程**：①武藏交规格书给 PSU 厂（台达/光宝/麦格米特/华为/维谛）认定 → ②单体样品测试 → ③模组化（类锂电包）测试 → ④按终端工况（MSFT/GOOG/Meta/ORCL）测试 → ⑤入 NVDA 推荐设计（但不标配）。**关键决策方=CSP 而非芯片厂**——北美 CSP 自 2024 底预见峰值功耗超电网冗余 → 提需求 → Flex/Delta 找储能；测试发现 LIC 工况契合最高+空间利用比 EDLC 优。**MSFT 最早**（首给功率图、首发论文）→ Meta 推快 → NVDA → GOOG **最终 GOOG 方案认可度最高**。**电解电容 vs 超容**：不可替代关系；电解装 PCBA 滤波/补充能量、但**内阻大功率差 + 循环寿命短**（AI 服务器秒级高频充放 → 电解一天耗尽）；电解仅补充毫秒级。**GB200 集群规模虽大但功率补偿需求不突出**；GB300 起明显。**国内浪潮反馈**：波动毫秒级小用铝电解解决，与大集群波动非同概念。**功率波动**：训练峰值 = 额定 1.5×、推理峰值 = 额定 1×；NVL72 132kW 机柜需配 132kW 超容模块。**方案对比**：①Flex CSS Power Shelf（28 电芯 × 14×2 = 20kW，132kW 需 7 模 = 196 电芯）；②**Sidecar HVDC 800V 6U 空间，每 U 输出 30kW = 180kW，180 电芯**——更高集成度。**平台电压提升核心目的**=减少电力转换次数降损耗（巴拿马/SST/HVDC 800V 三方案目标一致）。

## 关键数据点
- 北美 CSP 推进顺序：MSFT > Meta > NVDA > GOOG（认可度倒序）
- NVL72 132kW 机柜：Flex Power Shelf 7 模 196 电芯 / Sidecar 6U 180 电芯
- Sidecar 输出每 U 30kW / 6U 共 180kW
- 训练峰值 = 1.5× 额定 / 推理 = 1× 额定
- 电解电容 AI 服务器 1 天耗尽（高频充放）

## 关联连接
- [[摘要-ai-server-capacitor-domestic-2026-06-01]] — 国内东阳光视角
- [[摘要-japan-capacitor-na-csp-progress-2026-06-01]] — 同武藏前篇
- [[摘要-ai-capacitor-deep-compare-part1-2026-06-02]] / [[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] — 电容深度比较
- [[摘要-shenglan-connector-liquid-cooling-2026-06-01]] — 液冷接头
- [[800V HVDC]] — 概念
- [[Beta_Alpha锚点框架]] — Alpha=功率波动物理刚性需求
