---
title: "摘要-谷歌液冷PCB电源HVDC国产机会Trainium vs TPU"
type: source
tags: [来源, 研究纪要, 谷歌, 液冷, PCB, HDI, HVDC, 电源, Trainium, TPU, 国产替代, 英维克]
sources: [raw/研究纪要/半导体/2026-06-02 谷歌调研-液冷、PCB更新，电源方案及国产厂家机会，Trainium与TPU在推理场景的对比.md]
date: 2026-06-02
origin: acecamptech.com
last_updated: 2026-06-07
---

## 核心摘要

谷歌新一代服务器液冷升级：CDU 改为 **一拖八**；V8 在 TPU 四个 IO 端口下增加小冷板（每个 TPU 4 块 × 16 IO 口），输液管 5mm 直供。**V8T 30% 机柜将用 HDI PCB**。**HVDC 电源演进路线**：V7 + V8T 用 0-800V 方案，V8I 用 ±400V 方案——原 PSU 被电源管理板（千美元级别）取代，靠近主板布置；主供台达 + 光宝 + 维谛。国产液冷机会：英维克 / 阳光电源 / 高澜股份。**Trainium vs TPU 推理对比**：TPU 在 Gemini 模型场景成本优势显著（同模型同集群），Trainium 适配 Claude 但在 AWS 边际部署中存在生态成熟度差距。V9 仍在概念阶段，整机柜即将进 EVT。

## 关键数据点

- **CDU 组网**：一拖八
- **V8 小冷板数**：4 块/TPU × 4 IO 端口
- **输液管直径**：5mm
- **V8T HDI 占比**：30%
- **HVDC 方案**：V7/V8T 0-800V；V8I ±400V
- **电源管理板价值**：千美元级别
- **HVDC 主供**：台达 / 光宝 / 维谛
- **液冷国产**：英维克 / 阳光电源 / 高澜

## 关联连接

- [[GOOGL US]] — 主体
- [[英维克]] / [[阳光电源]] / [[高澜股份]] — 国产液冷
- [[800V HVDC]] — 概念
- [[Trainium]] / [[TPU]] — ASIC
- [[摘要-google-tpu-inference-cost-asic-2026-06-02]] — 同日 TPU 成本
- [[摘要-taiwan-power-csp-sic-2026-06-03]] — 同主题 6/03 台系电源
