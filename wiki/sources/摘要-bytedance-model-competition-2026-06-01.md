---
title: "摘要-头部大模型公司调研-Kimi-DeepSeek-千问-B端使用-2026-06-01"
type: source
tags: [来源, 研究纪要, 大模型, Kimi, DeepSeek, 千问, 智谱, B端, ROI, Token, Cache, H20, 910C]
sources: [raw/研究纪要/AI与云计算/2026-06-01 头部大模型公司调研：2026年以来国内大模型竞争变化，B端企业客户具体使用方式以及核心考量点，未来国内大模型发展预期.md]
date: 2026-06-01
origin: acecamptech.com
last_updated: 2026-06-07
---

## 核心摘要

**Kimi 视角**国内大模型 B 端竞争。**会计水分**：To B 合同 10-15% 坏账、API/订阅 20-30% 含水（赠送/分销/退订）。**国内 B 端竞品**：Kimi K2.6 vs 通义千问 3.6 PLUS（¥28/百万 token）vs 智谱 GLM-5.2 vs MiniMax 2.5 vs DeepSeek V4 Flash。**DeepSeek V4 三大致命问题**：①EEM 上下文缓存（128token→1 KV cache）压缩失真→稳定性差；②首 token 100 并发延迟 20 秒；③为适配 910C/910B/950 Pro 7nm 国产芯片牺牲多模态→前端编码场景不可用；用户回流 Kimi K2.6 但增收限——质变需架构不同的 K3。**B 端 AI 治理**：2026/2 起建监控系统、海外 Claude/GPT-5 成本超 ¥100 万/月触发管控；20+ 客户里 3-4 家完成（3 工程师 × 1 月）；两层控制 = ①每日 ¥50/人 + 月 ¥1,500 上限 + T+1 报表；②按部门/模型/算法服务统计。**ROI 难量化**：例 = 空调闲聊功能 Claude 主 80% + 千问备，纯成本看亏但提升市值数百亿= 正向 ROI。**B 端八大场景**：Coding（最大）→ Agent 管理 → 智能客服 → 法务 → 智能推荐 → 企业问答 → 底稿生成 → 具身智能。**C 端**：编程 + Kimi Claw 自动化（消耗前二）+ 长文档 + 多文档批处理 + 学术 + 表格 + 深度思考。**Token 经济**：免费用户日消耗 5-6T、多端去重日活 700 万、人均 2.3 次/天 × 6.2 轮/次。**Cache hit 几乎零成本**（占 CPU/内存，廉价）；100 万 token ¥7 含 GPU+内存+电费+机房。**部署规模**：Kimi K2.6 单实例 32 张 H20 (96GB)；DeepSeek V4 (1.5T) 用 910C 需 128 张；卡数按 2 的倍数扩。

## 关键数据点
- 国内 B 端竞品价：千问 3.6 Plus ¥28/M token
- DeepSeek V4 100 并发 首 token 延迟 20 秒
- B 端 AI 治理：员工日 ¥50 / 月 ¥1,500 上限
- Kimi 日活 700 万 / 日 token 5-6T 免费消耗
- 100 万 token ¥7 全栈成本（含电+机房）
- Kimi K2.6 单实例 32×H20；DPSK V4 (1.5T) 128×910C
- 部署卡数 2 的倍数扩

## 关联连接
- [[摘要-llm-pretrain-post-train-2026-06-05]] — 国内大模型范式（已 ingest）
- [[摘要-glm-coding-iteration-2026-06-01]] — 智谱视角（已 ingest）
- [[摘要-domestic-models-bytedance-wechat-agent-2026-06-07]] — 字节系列
- [[摘要-tencent-workbuddy-codebuddy-2026-06-01]] — 腾讯 Agent 矩阵
- [[摘要-token-pricing-tier-2026-06-03]] — Token 降价分层
- [[Anthropic]] / [[Claude]] / [[DeepSeek]] / [[Gemini]] — 关联实体
- [[Beta_Alpha锚点框架]] — Token 单位经济（推理 ROI 是 Alpha 锚）
