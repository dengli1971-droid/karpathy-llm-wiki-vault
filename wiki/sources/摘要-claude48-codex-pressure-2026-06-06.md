---
title: "摘要-Claude4.8发布-Fast Mode-禁入放开-ARR年底预期"
type: source
tags: [来源, 研究纪要, Anthropic, Claude4.8, Fast Mode, Codex, GPT5.5, Gemini, ARR, 编程, SWE-Bench]
sources: [raw/研究纪要/AI与云计算/2026-06-06 Claude 4.8发布：市场好评不断  禁入条款放开、Codex给的压力不小  算力支撑到位，ARR年底预期有望达成.md]
date: 2026-06-06
origin: acecamptech.com
last_updated: 2026-06-07
---

## 核心摘要

Claude 4.8 发布（2026/5 底，距 4.7 仅 1+ 月）+ 谷歌 Gemini 3.5 Flash 同月。**核心提升 3 项**：①不确定性表达增强（标记疑点） ②无依据结论倾向大降（对齐近 Mythos 预览版） ③代码安全性 = 4.7 的 1/4 概率允许缺陷未提示。**测评 6 项中 5 项第一**（仅 Terminal-Bench 略输 GPT-5.5 78.2 vs 74.6%，但差距 12.1pct → 3.6pct）：SWE-Bench Pro 69.2% 领先 GPT-5.5 10.6pct；Humanity Last Exam 无工具 49.8% / 有工具 57.9%；OSWorld-Verified 83.4%；GDPval-AA 1890 分领先 GPT-5.5 121/Gemini 3.1 Pro 576 分。**Fast Mode 发布**：/fast 速度 2.5×、价格 = 标准 2×；**vs Opus 4.7 Fast Mode 仅 1/3 价格**（4.7 $30/$150 → 4.8 $10/$50）；标准模式 $5/$25。**两大市场反馈问题**：①简单交互花 $0.2（思考过度消耗 Token = 隐性涨价）②裸 API 调用时模型自称千问/DeepSeek（蒸馏双标争议；推测=第三方 API 中继转 DPSK 端点；Anthropic 此前公开指责国内蒸馏）。**禁入条款放开 + 算力支撑到位**：联合多家厂商解决算力 → 稳定可靠挣钱服务 + Codex 高歌猛进压力下竞争反应；ARR 年底预期有望达成。**OpenAI GPT-5.6 泄漏**（Codex 看到）+ Codex 加大迭代 → 工程应用版本迭代提速。**总结**：AI 赛道从发散→聚合模式，统一朝 Anthropic 推崇的 AI Coding/长任务/复杂模式发力；谷歌多模态/端侧仍处量变阶段。

## 关键数据点
- Claude 4.8 距 4.7 = 1+ 月
- SWE-Bench Pro：4.8 69.2% vs GPT-5.5 58.6%（领先 10.6pct）
- Terminal-Bench：4.8 74.6% vs GPT-5.5 78.2%（差距收窄 12.1→3.6pct）
- GDPval-AA：4.8 1890 / GPT-5.5 1769 / Gemini 3.1 Pro 1314
- 价格：Opus 4.8 标准 $5/$25；Fast Mode $10/$50
- vs 4.7 Fast：$30/$150 → 4.8 1/3
- 简单交互成本约 $0.2

## 关联连接
- [[摘要-google-gemini35-allin-coding-2026-06-01]] — Gemini 3.5 短板（Coding/长任务）
- [[摘要-google-search-gemini-agent-2026-06-03]] — Gemini Flash 3.5 免费档表现
- [[摘要-token-pricing-tier-2026-06-03]] — Token 定价分层（Anthropic 顶部）
- [[摘要-ai-observability-na-2026-06-06]] — Anthropic 2C 场景
- [[摘要-bytedance-model-competition-2026-06-01]] — Kimi 视角国内对比
- [[Anthropic]] / [[Claude]] / [[NVDA US]] / [[AVGO US]] / [[AMZN US]] — 实体
- [[Beta_Alpha锚点框架]] — Alpha=对齐内生稀缺性；Beta=价格战
- [[芒格思维模型]] — 差异化竞争（vs 降价）
