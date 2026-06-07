---
title: "摘要-北美AI搜索大厂收入获客与Observability竞争"
type: source
tags: [来源, 研究纪要, Elasticsearch, Pinecone, Weaviate, Splunk, Observability, AI搜索]
sources: [raw/研究纪要/半导体/2026-06-03 北美AI搜索大厂收入增长、获客、价值量和竞争格局展望。客户AI观测预算变化和选择供应商考虑，大厂销售策略重心等。WeaviatePineconeSplunk.md]
date: 2026-06-03
origin: acecamptech.com
last_updated: 2026-06-07
---

## 核心摘要

北美 AI 搜索大厂（Elasticsearch ES 视角）：(1) **企业 Observability 预算难追加**——成本部门定位 + AI 转型预算从原预算挤出。模型厂商日志日 PB 级别，传统 Splunk 流量计费成本吃掉利润 → 优选 ClickHouse + 高压缩比初创。(2) **ES 业务三分**：search / observability / security。增速排序 search > security > observability；2024-2025 search 因企业混合检索 + AI 应用增速最快；security 因 Splunk 被思科收购大单增加；observability 占比下降。(3) **Splunk 被思科收购冲击**：管理层 + 资深工程师 + 销售大部分离职，部分加入 Elastic；产品路线图不清晰；AI 转型慢；外部缝 MongoDB 知识库导致系统复杂迟钝。(4) **Time-series DB 进展**：ES 加 Prometheus / PromQL 支持，性能已超 Prometheus；但缺基准测试社区认可 + 标杆客户案例 → 收入贡献尚未实质化。

## 关键数据点

- **模型厂商日志规模**：PB 级别 / 天
- **ES 业务增速**：search > security > observability
- **Splunk 离职率**：管理 + 工程 + 销售大部分
- **底层架构选择**：ClickHouse 高压缩比

## 关联连接

- [[Elastic]] / [[Pinecone]] / [[Weaviate]] / [[Splunk]] — 主体
- [[Observability]] — 概念
- [[AgenticAI]] — AI Ops 推动
- [[摘要-llm-context-agent-storage-cpu-2026-06-01]] — 同主题 6/01
