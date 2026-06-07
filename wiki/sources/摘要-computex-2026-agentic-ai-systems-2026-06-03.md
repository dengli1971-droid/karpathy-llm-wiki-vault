---
title: "摘要-2026台北电脑展Agentic-AI端云协同系统级硬件"
type: source
tags: [来源, 研究纪要, Computex, RTX Spark, Vera Rubin, AI PC, Xeon 6+, Retimer, Ultra Low Loss CCL]
sources: [raw/研究纪要/光通信/2026-06-03 2026台北电脑展：Agentic AI深化端云协同，系统级配套硬件产业价值凸显.md]
date: 2026-06-03
origin: acecamptech.com
last_updated: 2026-06-07
---

## 核心摘要

**2026 Computex 端云算力权力重构**：英伟达通过 Arm 全栈拓展（云端 Vera Rubin 88 核 Arm CPU + 端侧 RTX Spark 20 核 Grace + Blackwell 3nm + 板级异构集成 1 PFLOPS + 128GB 统一内存）→ 服务器级架构下放到 PC + 打破 CPU 中心格局 + Arm 入侵 Windows 腹地 + 复用 CUDA 生态；英特尔以 Xeon 6+ Intel 18A 工艺 + 288 能效核做服务器整合（1 台替 ~9 台）守 x86 防线；AMD 推 Zen 4 7700X3D + 96MB 3D V-Cache + AM5 平台延寿至 2029 稳存量市场。**Agentic 从纯数字向 Embodied AI**（具身智能/人形机器人/服务机器人）演进。**系统级配套硬件五大增量机会**：
1. **PMIC + 高镍电芯**：RTX Spark 等瞬时功耗剧烈，BOM 边际抬升 5-8%
2. **带独立 SRAM 的高阶 T-CON**：自刷新面板（PSR）标配，屏幕控制芯片厂受益
3. **Retimer 全面下放端侧**：120Gbps 接口在轻薄终端，单台高端 AI PC 1-2 颗，2027-2029 复合 +40%
4. **后端 SLT + Burn-in 测试耗材**：Chiplet/SiP 零容错，测试插座/探针卡需求放量
5. **Ultra Low Loss CCL**：高密度 + 高频要求结构性升级，2027 高阶材料占 PCB 价值 30-40% → **50%+**（Prismark 数据）

**关键洞察"总量收缩 / 单价提升"**：服务器整合压缩 PCB/CCL 总出货面积但单节点复杂度推动高层数高阶高频高速材料 → ASP 溢价驱动利润。**高速互连双轮**：① 机柜内 NVLink 铜缆背板大幅增加（Marvell 等高速互连芯片）② 机柜间 1.6T 光模块 + LPO/CPO 加速；Scale-up（NVLink 私有）+ Scale-out（InfiniBand/RoCEv2）。**端侧 AI PC 双轨**：高算力异构（Arm/RTX Spark）vs 轻量低功耗（x86/Lunar Lake/Ryzen AI 300 NPU 50 TOPS + TDP 15-37W）；2027-2028 出货放量。

## 关键数据点

- **RTX Spark**：20 核 Grace + Blackwell + 3nm + 1 PFLOPS + 128GB 统一内存
- **Vera CPU**：88 核 Arm
- **Xeon 6+ 整合比**：1 台替 ~9 台旧服务器（288 能效核 + Intel 18A）
- **Ryzen AI 300 / Lunar Lake**：NPU 50 TOPS / TDP 15-37W
- **Ultra Low Loss CCL 价值占比**：30-40% → **50%+**（2027）
- **Retimer**：单台高端 AI PC 1-2 颗 / 2027-2029 +40% CAGR
- **PMIC + 电芯 BOM 边际**：+5-8%

## 关联连接

- [[NVDA US]] / [[INTC US]] / [[AMD US]] / [[2454 TT 联发科技]] — 端云竞争三极
- [[MRVL US]] — NVLink 铜缆背板互连芯片
- [[CCL覆铜板]] — Ultra Low Loss CCL 升级
- [[Retimer]] — 概念页（待建）
- [[SLT/Burn-in测试]] — 概念页（待建）
- [[CPO]] / [[LPO]] / [[1.6T光模块]] — 互连演进
- [[Vera CPU]] — 已有概念页
- [[800V HVDC]] — 系统级配套
- [[AgenticAI]] / [[Embodied AI]] — 上层应用
