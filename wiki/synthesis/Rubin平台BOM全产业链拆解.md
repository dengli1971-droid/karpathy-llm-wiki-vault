---
title: "Rubin / Rubin Ultra 平台 BOM 全产业链拆解"
type: synthesis
tags: [Rubin, RubinUltra, BOM拆解, AI服务器, 产业链, 国产替代, 单机柜价值量, 800V HVDC, NVIDIA]
date: 2026-06-07
last_updated: 2026-06-07
sources: [
  摘要-jensen-huang-vera-rubin-gtc-taipei-2026-06-01,
  摘要-vera-cpu-platform-2026-06-01,
  摘要-rubin-power-chain-2026-06-05,
  摘要-secondary-power-hvdc-nvda-google-2026-06-03,
  摘要-domestic-drmos-suppliers-2026-06-02,
  摘要-drmos-expert-2026-06-04,
  摘要-power-chip-drmos-fivr-2026-06-05,
  摘要-mlcc-drmos-pricing-anchor,
  摘要-mlcc-domestic-progress-2026-06-04,
  摘要-domestic-mlcc-high-cap-2026-06-01,
  摘要-mlcc-tape-casting-machine-2026-06-02,
  摘要-pcb-drill-pin-rubin-2026-06-04,
  摘要-rubin-ultra-orthogonal-ptfe-2026-06-07,
  摘要-ccl-rubin-glass-fiber-2026-06-01,
  摘要-msap-process-pcb-2026-06-02,
  摘要-glass-substrate-interposer-2026-06-01,
  摘要-tsmc-cowos-soic-glass-2026-06-02,
  摘要-na-asic-2-cowos-emib-2026-06-03,
  摘要-ai-server-passive-tantalum-2026-06-03,
  摘要-tantalum-capacitor-2026-06-05,
  摘要-passive-2-tantalum-inductor-2026-06-03,
  摘要-supercap-lic-edlc-ai-2026-06-03,
  摘要-ai-server-capacitor-domestic-2026-06-01,
  摘要-japan-capacitor-cap-import-2026-06-03,
  摘要-ai-capacitor-deep-compare-part1-2026-06-02,
  摘要-ai-capacitor-deep-compare-part2-2026-06-04,
  摘要-server-cooling-rubin-2026-06-05,
  摘要-google-liquid-cooling-pcb-trainium-2026-06-02,
  摘要-liquid-cooling-supply-chain-2026-06-03,
  摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01,
  摘要-ptfe-strategic-material-2026-06-02,
  摘要-hbm-tsv-equipment-leadtime-2026-06-07,
  摘要-storage-supply-gap-2027-2026-06-02,
]
---

# Rubin / Rubin Ultra 平台 BOM 全产业链拆解

> **一句话内核**：Rubin（VR NVL72，2026/11-12 量产）到 Rubin Ultra（NVL576/Kyber，2027H2）的 BOM 不是「在 GB300 基础上等比放大」，而是 **GPU TDP 2300W + 单柜 120-500kW + 800V HVDC + 224Gbps PAM4 四条物理约束共同强制重构** 的产物——整机柜价值量从 GB300 的 ~$4M 跳到 Rubin Ultra ~$12-15M（+200-275%），但价值量增量并非均匀分布：**PCB +233% / 电源链 +大幅 / 被动元件 +15-20× / GPU 本身仅 +57%**，剪刀差就是 Alpha 来源。

## 一、平台代际对比

| 维度 | H100 / Hopper | B200 / Blackwell | GB200 NVL72 | GB300 NVL72 | Rubin NVL72 (VR) | Rubin Ultra NVL576 (Kyber) |
|------|---------------|------------------|-------------|-------------|------------------|-----------------------------|
| **量产时间** | 2023 | 2024 | 2025 | 2026 H1 | 2026/11-12 [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] | 2027 H2 [[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]] |
| **单 GPU TDP** | 700W [[摘要-mlcc-drmos-pricing-anchor]] | 1000W [[摘要-mlcc-drmos-pricing-anchor]] | ~1.24kW [[摘要-power-chip-drmos-fivr-2026-06-05]] | ~1.4kW [[摘要-power-chip-drmos-fivr-2026-06-05]] | ~2.3kW [[摘要-mlcc-drmos-pricing-anchor]] | ≥2.3kW [[摘要-power-chip-drmos-fivr-2026-06-05]] |
| **核心电压** | ？(待补) | ？(待补) | 0.8V [[摘要-mlcc-drmos-pricing-anchor]] | 0.8V→更低 | 0.8V→更低 [[摘要-ai-server-passive-tantalum-2026-06-03]] | ？(待补) |
| **单 GPU 瞬时电流** | ？(待补) | ？(待补) | >1250A [[摘要-mlcc-drmos-pricing-anchor]] | ？(待补) | ？(待补) | ？(待补) |
| **单机柜功耗** | 10-20kW [[摘要-ai-capacitor-deep-compare-part1-2026-06-02]] | ？(待补) | 120-150kW [[摘要-ai-capacitor-deep-compare-part1-2026-06-02]] | 120-140kW [[摘要-supercap-lic-edlc-ai-2026-06-03]] | ？(待补) | 200-500kW→MW 级 [[摘要-ai-capacitor-deep-compare-part1-2026-06-02]] |
| **DrMOS 相数** | ？(待补) | ？(待补) | 8 相 [[摘要-passive-2-tantalum-inductor-2026-06-03]] | 8 相 | 12 相 [[摘要-passive-2-tantalum-inductor-2026-06-03]] | 12-16 相 [[摘要-ai-server-passive-tantalum-2026-06-03]] |
| **散热方式** | 风冷 [[摘要-server-cooling-rubin-2026-06-05]] | 水冷 + IHS | 水冷 + 裸 Die + 相变 TIM [[摘要-server-cooling-rubin-2026-06-05]] | 水冷 + 多小冷板 [[摘要-server-cooling-rubin-2026-06-05]] | 水冷 + 裸 Die + 石墨烯 TIM（2026/5 定）[[摘要-server-cooling-rubin-2026-06-05]] | 水冷 + 石墨烯 TIM |
| **微通道间距** | n/a | n/a | 0.15mm [[摘要-server-cooling-rubin-2026-06-05]] | 0.15mm | 0.1mm [[摘要-server-cooling-rubin-2026-06-05]] | 0.05mm 理想未达 [[摘要-server-cooling-rubin-2026-06-05]] |
| **整柜 PSU 数** | n/a | n/a | ？(待补) | 36 颗 × 5.5kW（6 Shelf × 6）[[摘要-rubin-power-chain-2026-06-05]] | 18.3kW 模块定制 [[摘要-rubin-power-chain-2026-06-05]] | 18.3kW 模块定制 [[摘要-rubin-power-chain-2026-06-05]] |
| **配电架构** | 54V DC | 54V DC | 54V DC | 54V DC + 二次电源 | 800V HVDC（小批量）[[摘要-secondary-power-hvdc-nvda-google-2026-06-03]] | 800V HVDC（Kyber 参考架构）[[摘要-ai-capacitor-deep-compare-part1-2026-06-02]] |
| **CoWoS 类型** | CoWoS-S（8-12 HBM）[[摘要-tsmc-cowos-soic-glass-2026-06-02]] | CoWoS-S | CoWoS-S/L | CoWoS-L | CoWoS-L + CoWoS-R（Vera CPU）[[摘要-tsmc-cowos-soic-glass-2026-06-02]] | CoWoS-L + EMIB 备份 [[摘要-na-asic-2-cowos-emib-2026-06-03]] |
| **HBM 配置** | HBM3（80GB） | HBM3e | HBM3e | HBM3e/HBM4 | HBM4 | HBM4（更高堆叠）[[摘要-hbm-tsv-equipment-leadtime-2026-06-07]] |
| **互联** | NVLink 4 | NVLink 5 | NVLink 5 / 72 卡 | NVLink 5 | NVLink 72 + CX9 [[摘要-jensen-huang-vera-rubin-gtc-taipei-2026-06-01]] | NVLink 576 + 正交背板（224Gbps PAM4）[[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]] |
| **CPU** | x86（Intel/AMD） | x86 | Grace ARM | Grace ARM | Vera CPU（88 Olympus 核）[[摘要-vera-cpu-platform-2026-06-01]] | Vera CPU |
| **整柜售价（参考）** | ？(待补) | ？(待补) | NVL36 ¥198 万 [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] | NVL36 ¥210 万 / NVL72 ¥410 万 [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] | NVL36 ¥350 万 / NVL72 ¥650 万 / NVL144 ¥1,100 万 [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] | ~$12-15M [[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] |

## 二、核心 BOM 矩阵（PM 工作底稿）

> **使用说明**：单机柜口径除非另注；H100 / Rubin / Rubin Ultra 三档对比；** 倍数 ** 列以 H100 或 GB300 为基准（已标注）；** 来源 ** 列必查；空 cell `？(待补)`；价值量数字以 USD 为主，CNY 按 7.2:1 换算时另注。

### 2.1 算力核心与封装

| 组件 | H100 / GB300 用量 / 价值量 | Rubin / Rubin Ultra 用量 / 价值量 | 倍数 | 国产替代窗口 | 受益龙头 | 来源 |
|---|---|---|---|---|---|---|
| **GPU Die 本身（CoWoS 后）** | H100 高毛利 | Rubin GPU 涨幅仅 +57%（vs PCB +233%）[[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]] | 1.6× | 不可替代（NVDA 自研 + TSMC 4nm/2nm） | [[NVDA US]] / [[2330 TT  TSMC]] | [[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]] |
| **CoWoS-S/L（GPU 封装）** | GB300：12 HBM CoWoS-L | Rubin 主用 CoWoS-L | ？(待补) | 中国厂商无路径 | [[2330 TT  TSMC]] / [[AMKR US]] / [[3711 TT 日月光投资控股]] | [[摘要-tsmc-cowos-soic-glass-2026-06-02]] |
| **CoWoS-R（Vera CPU chiplet）** | n/a | Vera CPU 占 NVDA 需求 15%，CoWoS-R 总需求 80-100K，100% 外包（安靠 70% + 日月光 30%）[[摘要-tsmc-cowos-soic-glass-2026-06-02]] | 新增 | OSAT 国产无 | [[AMKR US]] / [[3711 TT 日月光投资控股]] | [[摘要-tsmc-cowos-soic-glass-2026-06-02]] |
| **HBM3e / HBM4** | GB300：HBM3e | Rubin Ultra：HBM4 多层 TSV，纯交期 >6 月 + 拉长 [[摘要-hbm-tsv-equipment-leadtime-2026-06-07]] | ？(待补) 量×（按 NVL576 die 计 单 GPU HBM 跃升） | 长鑫/长江完全无路径，国产卡死 | [[MU US]] / [[000660 KS]] / [[005930 KS]]；TSV 设备美/日系议价权决定 | [[摘要-hbm-tsv-equipment-leadtime-2026-06-07]]、[[摘要-storage-supply-gap-2027-2026-06-02]] |
| **Vera CPU（自研 ARM）** | n/a（H100 配 x86）| 88 Olympus 核 + 176 线程 + 1.5TB LPDDR5X + 1.2TB/s 带宽 + NVLink-C2C 1.8TB/s [[摘要-vera-cpu-platform-2026-06-01]] | 新增价值层 | 国产化路径=华为鲲鹏，不进 NVDA 链 | [[NVDA US]] 自研 → [[2330 TT  TSMC]] 代工 | [[摘要-vera-cpu-platform-2026-06-01]]、[[摘要-jensen-huang-vera-rubin-gtc-taipei-2026-06-01]] |
| **TGV 玻璃基板 / interposer** | 量产 0（仍 ABF）[[摘要-glass-substrate-interposer-2026-06-01]] | 5-15% 渗透率（未来 3-5 年） [[摘要-glass-substrate-interposer-2026-06-01]] | 增量 | 主推=[[GLW US]] 康宁 + 台积电 + 日月光 + Intel；国产无量产 | [[GLW US]] / [[INTC US]] / [[2330 TT  TSMC]] / [[3711 TT 日月光投资控股]] | [[摘要-glass-substrate-interposer-2026-06-01]]、[[摘要-tsmc-cowos-soic-glass-2026-06-02]] |

### 2.2 PCB / CCL / 基板

| 组件 | H100 / GB300 用量 / 价值量 | Rubin / Rubin Ultra 用量 / 价值量 | 倍数 | 国产替代窗口 | 受益龙头 | 来源 |
|---|---|---|---|---|---|---|
| **PCB 子系统（单机柜总价值）** | Hopper $10K / GB300 $35K [[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]] | **Rubin Ultra $117K（11.7 万美元）** [[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]] | **~10× vs Hopper / 3.3× vs GB300（+233%）** | 制造端：欣兴 60-70% compute + TTM 15%；switch tray 欣兴 40-55% + TTM 10-20%；胜宏/深南/沪士打样 [[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]] | [[002463 CH 沪电股份]] / [[002916 CH 深南电路]] / [[002938 CH 鹏鼎控股]] / [[300476 CH 胜宏科技]] | [[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]]、[[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] |
| **正交背板 PCB** | n/a（5,000+ 铜缆，吨级）[[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] | 单块 **78 层 × 1.2m × 0.2m × 1cm 厚（量产无人区）** [[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]]；40 层基础 $800/片，NVL576 用 168 层专属大背板 [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] | 新增 | 沪电/深南/鹏鼎已认证 + 胜宏 PVT2；代工厂倾向沪电拿一半 [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] | [[002463 CH 沪电股份]] / [[002916 CH 深南电路]] | [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]]、[[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]] |
| **CCL M9 / M8.5 高频高速** | GB300 用 M7/M8 [[摘要-ccl-rubin-glass-fiber-2026-06-01]] | Rubin → M8.5/M9；Rubin Ultra ≥M9 [[摘要-ccl-rubin-glass-fiber-2026-06-01]]；M9 Dk 3.0-3.5 / Df 0.002-0.004 [[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]] | M6 ¥250 → M8 ¥1,000+ /平米（4×）[[摘要-ccl-rubin-glass-fiber-2026-06-01]] | 生益 Switch 二/三供 + GB 系列 20-30% 份额，难升一供（地缘）[[摘要-ccl-rubin-glass-fiber-2026-06-01]] | [[600183 CH 生益科技]] / [[2383 TT]]（台光） | [[摘要-ccl-rubin-glass-fiber-2026-06-01]] |
| **Low Dk 二代玻璃布** | ？(待补) | 国际复材月供 50-60 万米 → 240 万米 CCL 年产能 → 1.5 万个 72 卡机柜年产能 [[摘要-ccl-rubin-glass-fiber-2026-06-01]]；价格 25 年底 ¥80-90 → 当前 ¥100+/米（仍涨）[[摘要-ccl-rubin-glass-fiber-2026-06-01]] | 价 +20%+ | **国际复材唯一通过 2025 认证**，新供应商 1-2 年；池窑 1500-1600℃ + 丰田织布机 + 高目数漏板 | 国际复材 / 宏和科技 [[603256 CH 宏和科技]] | [[摘要-ccl-rubin-glass-fiber-2026-06-01]] |
| **Q 布 / T-glass（Rubin Ultra）** | n/a | NVDA 单家需求 **400-500 万米/月（2026）** [[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]]；钻嘴寿命 100-200 孔 vs FR-4 1,500-2,000（+10-15× 损耗）[[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]] | 新增 | **日东纺接近垄断**（[[3407 JP]]），2025/8 扩 3× 但 2027-28 才释放 [[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]] | [[3407 JP]] | [[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]] |
| **PTFE 树脂（Rubin Ultra 候选）** | n/a | Dk 2.1-2.6 / Df 0.0002-0.001（vs M9 优 10×）[[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]]；M8+PTFE 成本 <1/3 M9+Q 布；加工 >320℃ 良率 ~70% 报废万美元/块 [[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]] | 战略材料化（百倍价差）[[摘要-ptfe-strategic-material-2026-06-02]] | M10 PTFE 由大金/罗杰斯把控（金属离子 ppb 级）；国内圣泉 M9 碳氢百吨级 / 东材+迪赛 BCB 千吨级试产 [[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]] | 巨化股份 / 东岳集团 / 昊华科技 / 三美股份（大宗）[[摘要-ptfe-strategic-material-2026-06-02]]；电子级仍进口 | [[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]]、[[摘要-ptfe-strategic-material-2026-06-02]] |
| **HVLP4 镜面铜箔** | ？(待补) | 全球月需 400-500 吨（三井金属 + 国内金居各半）[[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]]；HVLP4 ¥19 万/吨（vs 普通 ¥9 万）[[摘要-msap-process-pcb-2026-06-02]] | 2.1×（HVLP4 / 普通）[[摘要-msap-process-pcb-2026-06-02]] | **三井 vs 德福双寡头**；德福已过 NVDA + GOOGL 认证 [[摘要-msap-process-pcb-2026-06-02]]；国产铜箔进 M10 试样 [[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]] | 德福（国内）/ [[三井金属]]（[[5706 JP]]） | [[摘要-msap-process-pcb-2026-06-02]]、[[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]] |
| **PCB 钻针** | 200 系列一拖二（3 刀）/30 倍长径比 / 寿命 1,500 孔 [[摘要-pcb-drill-pin-rubin-2026-06-04]]；GB300 5-6 万孔 [[摘要-pcb-drill-pin-rubin-2026-06-04]] | **Rubin 一拖四（5 刀）/30+40+50 倍 / 寿命 200 孔**；Rubin 正交背板 **10 万孔**（vs GB300 5-6 万）[[摘要-pcb-drill-pin-rubin-2026-06-04]]；50 倍价 ¥十几元（40 倍 ¥6-8 / 30 倍 ¥3-4）[[摘要-pcb-drill-pin-rubin-2026-06-04]] | **价 2×+ × 寿命 -86%（消耗 7.5×）× 孔数 2× ≈ 30× 总耗** | 50 倍国内：本公司 + 日本佑能（佑能月 3,000+ 万支主供日韩）[[摘要-pcb-drill-pin-rubin-2026-06-04]] | [[鼎泰高科]] / [[尖点科技]] | [[摘要-pcb-drill-pin-rubin-2026-06-04]]、[[摘要-msap-process-pcb-2026-06-02]] |
| **MSAP 高端 PCB（载板/光模块/网络板）** | 25% 渗透率（2026）[[摘要-msap-process-pcb-2026-06-02]] | 2027 45% / 2028 70%（高端取代 HDI）[[摘要-msap-process-pcb-2026-06-02]]；Rubin Ultra/Feynman 全用 MSAP | 价 +50-100% vs HDI（800G 良率 88-92% vs HDI <80%）[[摘要-msap-process-pcb-2026-06-02]] | 设备瓶颈：亚洲电镀 ¥2,800 万 + 东威 ¥2-2.2K 万；下单交付 1.5 年 [[摘要-msap-process-pcb-2026-06-02]] | 第一梯队 [[002938 CH 鹏鼎控股]] / [[002916 CH 深南电路]] / [[002463 CH 沪电股份]]；二梯 [[300476 CH 胜宏科技]] / 方正 / 兴森 | [[摘要-msap-process-pcb-2026-06-02]] |

### 2.3 电源链（最大边际增量）

| 组件 | H100 / GB300 用量 / 价值量 | Rubin / Rubin Ultra 用量 / 价值量 | 倍数 | 国产替代窗口 | 受益龙头 | 来源 |
|---|---|---|---|---|---|---|
| **PSU 模块（一次电源）** | GB300：36 颗 × 5.5kW = 198kW（6 Shelf × 6） [[摘要-rubin-power-chain-2026-06-05]] | **Rubin/Ultra：18.3kW 模块定制**；18.3kW 价值量大增（全液冷 + SiC 一次 + GaN 二次 + HVDC + 超容集成）[[摘要-rubin-power-chain-2026-06-05]] | 单模块 3.3×（5.5→18.3kW）+ 工艺溢价 | **国内 Power Shelf 落后海外 2 代**；5.5kW 中国小批量；18.3kW 国内尚无量产；国产 2027 才小批量介入 [[摘要-rubin-power-chain-2026-06-05]] | 海外双供：某台湾 PSU 40% + 全汉 60% [[摘要-rubin-power-chain-2026-06-05]]；国产 [[2308 TT DELTA]] / [[光宝科技]] / 维谛 / 麦格米特 / 欧陆通 [[摘要-secondary-power-hvdc-nvda-google-2026-06-03]] | [[摘要-rubin-power-chain-2026-06-05]] |
| **PSU 功率器件 MOS（IFX）** | GB300 5.5kW MOS：英飞凌主供 + 50% 美方瓜分 [[摘要-rubin-power-chain-2026-06-05]] | 18.3kW 同 IFX 主供；测试中电容鼓包后美方 ~60% [[摘要-rubin-power-chain-2026-06-05]]；IFX+ON 合计 60-70% BOM | ？(待补) | 国产 MOS 进 PSU 难 | [[IFX GY]] / 安森美 [[ON US]] | [[摘要-rubin-power-chain-2026-06-05]] |
| **二次电源砖（48V→12V）** | 主流单砖 2,000W；1,500/3,000W 共存；3,000W 即将量产 [[摘要-secondary-power-hvdc-nvda-google-2026-06-03]] | Rubin 用量随 GPU 功耗 [[摘要-secondary-power-hvdc-nvda-google-2026-06-03]] | ？(待补) | ADI 套片（主控+MOS+DRIVER）+ 新雷能 + 铂科磁芯 [[摘要-secondary-power-hvdc-nvda-google-2026-06-03]] | 新雷能 / 铂科新材 / [[ADI US]] / 伟创力 / [[2308 TT DELTA]] | [[摘要-secondary-power-hvdc-nvda-google-2026-06-03]] |
| **DrMOS（三次电源 / GPU 多相）** | GB300 单 GPU 8 相 × 8-10 DrMOS × 2 Die [[摘要-passive-2-tantalum-inductor-2026-06-03]] | **单机柜 6,000 颗 = 5,400 计算 + 600 交换**（18 层 × 300 计算 + 300 交换）[[摘要-power-chip-drmos-fivr-2026-06-05]]；单颗 $1.5（90A ¥25）→ **~$9,000/柜**（+电感电容 → $10K+）[[摘要-power-chip-drmos-fivr-2026-06-05]][[摘要-drmos-expert-2026-06-04]]；Rubin 相数 8→12（单 GPU 增 50%）[[摘要-passive-2-tantalum-inductor-2026-06-03]] | 量 +50% × 单价稳/微涨 | NVDA 主供 = IFX/瑞萨/MPS/AOS [[摘要-domestic-drmos-suppliers-2026-06-02]]；新供进 Rubin/Ultra 才有窗口；MPS 在 Rubin 已出局 [[摘要-power-chip-drmos-fivr-2026-06-05]]；**国产仍走华为/海光/寒武纪/谷歌台达代供链**；**杰华特已是华为 DrMOS #1** [[摘要-drmos-expert-2026-06-04]] | [[IFX GY]] / [[6723 JP]]（瑞萨）/ MPS / AOS（海外）；[[688141 CH 杰华特]] / [[688368 CH 晶丰明源]] / 芯朋微 / 矽力杰（国产） | [[摘要-power-chip-drmos-fivr-2026-06-05]]、[[摘要-domestic-drmos-suppliers-2026-06-02]]、[[摘要-drmos-expert-2026-06-04]] |
| **TLVR 电感（GPU 周围）** | GB300 单 GPU 8-10 TLVR + 1 LC × 2 Die；NVL72 ~1,440 颗 [[摘要-passive-2-tantalum-inductor-2026-06-03]] | Rubin 12 相 → 单 GPU 12 颗 → NVL72 ~1,728 颗（推算）；单价 >$1/颗 [[摘要-passive-2-tantalum-inductor-2026-06-03]] | 量 +20% / 价博弈下行 | NVDA 通过 MPS + IFX 间接供应（顺络单笔过亿）[[摘要-passive-2-tantalum-inductor-2026-06-03]] | 海外乾坤 #1 [[摘要-passive-2-tantalum-inductor-2026-06-03]]；国产 [[002138 CH 顺络电子]]（2025 营收 ~¥2 亿）/ 铂科新材 / 麦捷 / 龙磁 | [[摘要-passive-2-tantalum-inductor-2026-06-03]] |
| **800V HVDC 转换器 / SST** | n/a | 800V HVDC Vera Rubin Ultra Kyber 参考架构 [[摘要-ai-capacitor-deep-compare-part1-2026-06-02]]；SST 1200V+ SiC MOSFET / >250 kHz；2026H2 小批量 [[摘要-secondary-power-hvdc-nvda-google-2026-06-03]]；铜截面 -45% / 效率 +5% / 变压器 -50% 体积；节电 2-3%（美电费敏感）[[摘要-rubin-power-chain-2026-06-05]] | 新增系统层 | **HVDC 主供：[[2308 TT DELTA]] + 光宝 + 维谛 + 麦格米特 + 欧陆通** [[摘要-secondary-power-hvdc-nvda-google-2026-06-03]]；5kW HVDC 一次电源芯片+器件 ~¥300 RMB [[摘要-drmos-expert-2026-06-04]] | [[2308 TT DELTA]] / 光宝 / 维谛 / 麦格米特 / 欧陆通 / 阳光电源 | [[摘要-rubin-power-chain-2026-06-05]]、[[摘要-secondary-power-hvdc-nvda-google-2026-06-03]] |

### 2.4 被动元件

| 组件 | H100 / GB300 用量 / 价值量 | Rubin / Rubin Ultra 用量 / 价值量 | 倍数 | 国产替代窗口 | 受益龙头 | 来源 |
|---|---|---|---|---|---|---|
| **MLCC（高端高容）** | H100 → GB200 单机架 **15-20× 跳升** [[摘要-mlcc-drmos-pricing-anchor]]；GB200 60 万颗/柜（80% 高端 = 48 万颗）[[摘要-mlcc-domestic-progress-2026-06-04]] | Rubin 12 相 + 0.1V 更低 + 01005 微缩 + X6S/X7R 升维；单颗 ASP +30-50% [[摘要-mlcc-drmos-pricing-anchor]] | **15-20× 跳升 vs H100 / Rubin 在此基础上 +50% 量价** | 风华 vs 日韩落后 **2 代**（0805 量产 22μF vs 日 100μF）[[摘要-domestic-mlcc-high-cap-2026-06-01]]；三环量产规模 150 亿颗 → 极限 400-450 亿颗 [[摘要-mlcc-domestic-progress-2026-06-04]]；流延机国产替代核心 [[摘要-mlcc-tape-casting-machine-2026-06-02]] | 海外 [[村田]] 45% / [[三星电机]] 30% / [[太阳诱电]] 15%；国产 [[300408 CH 三环集团]] / [[000636 CH 风华高科]] | [[摘要-mlcc-drmos-pricing-anchor]]、[[摘要-mlcc-domestic-progress-2026-06-04]]、[[摘要-domestic-mlcc-high-cap-2026-06-01]]、[[摘要-mlcc-tape-casting-machine-2026-06-02]] |
| **MLCC 全市场口径** | 2026 服务器 MLCC 出货 1,000 亿颗 [[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] | 2030 4,000 亿颗（CAGR ~40%）[[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] | 4× | — | — | [[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] |
| **钽电容** | 企业 SSD 单台 15-20 颗 [[摘要-tantalum-capacitor-2026-06-05]] | **Rubin 单机柜 5,000 颗**（传统单机难想象）[[摘要-tantalum-capacitor-2026-06-05]]；单价小壳 ¥几毛 / 大壳 ¥1-3 | 5,000 颗规模 / 2025 累计涨价 50-60% / 交期 8-10 月 [[摘要-tantalum-capacitor-2026-06-05]] | 全球 CR4=96%（KEMET 46% / AVX 26% / Panasonic 14% / Vishay 10%）[[摘要-ai-capacitor-deep-compare-part2-2026-06-04]]；**国产 = [[300726 CH 宏达电子]]**（S 公司 PCB 引脚结构专利）[[摘要-tantalum-capacitor-2026-06-05]] | [[300726 CH 宏达电子]] / [[KEMET]] / [[AVX]] | [[摘要-tantalum-capacitor-2026-06-05]]、[[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] |
| **超级电容（LIC/EDLC）** | GB200 选配 $2-4 [[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] | **GB300 标配** = 武藏混合 LIC **396 颗 × $40-50 = $12K-15K/柜**（机柜内最大新王）[[摘要-ai-capacitor-deep-compare-part2-2026-06-04]]；NVL72 132kW Sidecar 6U 180 电芯 [[摘要-japan-capacitor-cap-import-2026-06-03]] | 从选配 → 标配，**单柜 +$10-12K** | 武藏 650 万颗规划 vs 1,500-1,800 万需求；东阳光新建专线月 1,500 万 → 2027 月 2,000 万；国内单价 ¥30-40 [[摘要-ai-server-capacitor-domestic-2026-06-01]] | 武藏（[[7224 JP]]）/ [[600673 CH 东阳光]] / [[002484 CH 江海股份]] | [[摘要-supercap-lic-edlc-ai-2026-06-03]]、[[摘要-ai-server-capacitor-domestic-2026-06-01]]、[[摘要-japan-capacitor-cap-import-2026-06-03]]、[[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] |
| **薄膜电容（Rubin Ultra 800V 用）** | GB200/300 极少（54V 架构）[[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] | **Rubin Ultra 单柜 $18K-36K**（800V HVDC 兆瓦级，电源 BOM 400 万 RMB × 5-10%）[[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] | **从 ~0 跳升到 $18-36K（机柜最大新王 #2）** | 法拉电子全球 ~20% 份额，毛利 33.4-38.6% / ROE 19-22%；自愈型 KV 级 [[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] | [[300861 CH 法拉电子]] | [[摘要-ai-capacitor-deep-compare-part2-2026-06-04]]、[[摘要-ai-capacitor-deep-compare-part1-2026-06-02]] |
| **铝电解（牛角型 / MLPC）** | GB300：HVDC 100kW 集中 18-22 颗 475V；300kW IT 柜 ~60 颗 [[摘要-ai-server-capacitor-domestic-2026-06-01]] | **Rubin Ultra 800V 架构需求 ∝ 1/V²，远期价值打 0.6 折** [[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] | 价值衰减但短期仍在 | 东阳光台达 ¥8.5/颗 vs 日系尼吉康 ¥十几元；新建专线月 1,500 万 [[摘要-ai-server-capacitor-domestic-2026-06-01]] | [[600673 CH 东阳光]] / [[002484 CH 江海股份]] / [[002484 CH 艾华集团]] | [[摘要-ai-server-capacitor-domestic-2026-06-01]]、[[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] |
| **电容总价值（机柜口径）** | GB300 电容总 $19-25K（整柜 ODM $4M 的 0.5-0.63%）[[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] | **Rubin Ultra 整柜电容估算 ~$120-150K（整柜 $12-15M 的 ~1.0%）** [[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] | **6-7×** | — | — | [[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] |

### 2.5 散热 / 液冷

| 组件 | H100 / GB300 用量 / 价值量 | Rubin / Rubin Ultra 用量 / 价值量 | 倍数 | 国产替代窗口 | 受益龙头 | 来源 |
|---|---|---|---|---|---|---|
| **水冷板** | GB200 单大冷板 ~$150 [[摘要-server-cooling-rubin-2026-06-05]]；GB300 多小冷板 | Rubin 回归大冷板 + 0.1mm 微通道；单价 **$100-150** [[摘要-server-cooling-rubin-2026-06-05]] | 同价位、技术换代 | 铲齿工艺、门槛不高 → 大量参与：俊强/AVC/台达/健策/双鸿 [[摘要-server-cooling-rubin-2026-06-05]] | [[3653 TT 健策精密工业]] / [[2308 TT DELTA]] / AVC / 俊强 / 双鸿 | [[摘要-server-cooling-rubin-2026-06-05]] |
| **TIM（石墨烯）** | GB200 霍尼韦尔相变 TIM $3/GPU [[摘要-server-cooling-rubin-2026-06-05]]；GB200 IHS $5 | **Rubin 2026/5 定石墨烯 TIM**（弃液态金属，铟镓合金一致性差）[[摘要-server-cooling-rubin-2026-06-05]] | 工艺换代 | 多家备选：鸿富诚 / 富烯（常州）/ 海外 Parker [[摘要-server-cooling-rubin-2026-06-05]] | 富烯 / 鸿富诚 / Parker | [[摘要-server-cooling-rubin-2026-06-05]] |
| **液冷自供（管/板/manifold/快接头）** | GB 系列 50% 自供 [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] | **VR 系列 75%+ 自供 → 单机价值 ~$8-10K** [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] | 自供份额 +50% / 价值 $5K → $8-10K | 竞争对手 2027/4 后才介入 [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] | [[2317 TT Hong Hai]]（鸿海独家）/ [[3653 TT 健策精密工业]] | [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] |
| **机壳** | GB200 D7000 $28K [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] | **VR NVR36 $35K** [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] | 1.25× | 鸿海主导 | [[2317 TT Hong Hai]] | [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] |
| **数据中心一次侧（1GW 口径）** | 风冷 ¥18-20 亿 [[摘要-liquid-cooling-supply-chain-2026-06-03]] | 干冷器 **¥35 亿**（+75-94%）/ 冷却塔水冷主机 **¥40 亿**（+100%）[[摘要-liquid-cooling-supply-chain-2026-06-03]] | 1.75-2× | 国产突破点：申菱 / 英维克 / 阳光电源 / 高澜 [[摘要-google-liquid-cooling-pcb-trainium-2026-06-02]]、[[摘要-liquid-cooling-supply-chain-2026-06-03]] | [[002837 CH 英维克]] / [[300499 CH 高澜股份]] / 申菱 / 阳光电源 | [[摘要-liquid-cooling-supply-chain-2026-06-03]]、[[摘要-google-liquid-cooling-pcb-trainium-2026-06-02]] |

### 2.6 网络互联 / CPO

| 组件 | H100 / GB300 用量 / 价值量 | Rubin / Rubin Ultra 用量 / 价值量 | 倍数 | 国产替代窗口 | 受益龙头 | 来源 |
|---|---|---|---|---|---|---|
| **CPO 交换机（与 Rubin 同步）** | n/a | **2026/8 量产**（早 VR 两三月），月产能 6,000 → 11 月 10-11K；**单价 ~$100K**；NVDA 接近独家供应 [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] | 新增 | NVDA 独家 → 大概率走鸿海等 ODM | [[2317 TT Hong Hai]] / 中际旭创 / 新易盛 / [[CPO]] | [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] |
| **Pogo Pin / 高精密连接器** | n/a | 0.1mm 直径，背部连接四方案（铜缆/光纤/光模块/正交背板）通过 pogo pin 适配 [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] | 新增 | 美系 Molex/TE 主导 + 台湾中国探针辅助 [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] | Molex / TE / [[300679 CH 电连技术]] | [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] |

## 三、瓶颈与节奏分析

### 3.1 当前已知的硬约束（按 Rubin 量产时间倒序）

| 瓶颈环节 | 约束机制 | 缓解节奏 | 卡死方 |
|---|---|---|---|
| **HBM4 TSV 设备交期** | 多层 DRAM 堆叠 TSV 高深宽比刻蚀/铜种子层沉积；纯交期 >6 月还在拉长；美光台湾月产能 2-3 万 → 2029 才 10-11 万片（4×）[[摘要-hbm-tsv-equipment-leadtime-2026-06-07]] | 2027-29 真正释放；美系设备交付优先级=美光 > 韩系 | TSV 设备厂（美/日系） |
| **Q 布（日东纺）** | NVDA 单家需求 400-500 万米/月 vs 远低有效产能；2025/8 扩 3× 但 **2027-28 才释放** [[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]] | Rubin Ultra（2027H2 量产）正好碰窗口 | [[3407 JP]] 日东纺垄断 |
| **CoWoS 产能** | TSMC 2026 总 1,200K 片（NVDA 占 50-55% = 600K）；2028 仍紧 [[摘要-tsmc-cowos-soic-glass-2026-06-02]]；博通 20-30% 转 Intel EMIB（2027H2 实施）[[摘要-na-asic-2-cowos-emib-2026-06-03]] | 2027 安靠 27K + 美国厂量产 | TSMC + AMKR + 日月光 |
| **Low Dk 二代玻璃布** | 国际复材唯一通过 2025 认证，月供 50-60 万米 → 1.5 万机柜/年 [[摘要-ccl-rubin-glass-fiber-2026-06-01]]；新供应商认证 1-2 年 | 价格仍涨 ¥100+/米 | 国际复材独家 |
| **18.3kW PSU** | 国内 Power Shelf 落后海外 2 代；首发 = 某台湾 PSU 40% + 全汉 60%；国内 2027 才小批量 [[摘要-rubin-power-chain-2026-06-05]] | 国产 2027+ | 国内电源公司 vs 台资 |
| **MSAP 设备（电镀）** | 亚洲 + 东威总产能 300-350 线/年；下单到交付 1.5 年 [[摘要-msap-process-pcb-2026-06-02]] | 2026-27 满载 | 亚洲（台）/ 东威（中） |
| **DRAM 通用** | 缺口至 2027 年底；Q1 涨 80-100%（vs TrendForce 50%）[[摘要-storage-supply-gap-2027-2026-06-02]] | 2027 后期 | 三星/SK/美光 |

### 3.2 国产替代窗口期分级

| 节奏 | 2026 H2 | 2027 | 2028+ |
|---|---|---|---|
| **已有量产小批量** | 国产 DrMOS 进华为/海光/寒武纪（杰华特、晶丰）；国产铝电解（东阳光、艾华）；液冷板（健策）；钽电容（宏达电子） | 18.3kW PSU 国产小批量；PCB 钻针 50 倍 国产突破；M9 CCL 生益升 GB 一供（仍难）；国产 LIC（东阳光 1,500 万扩产 → 2027 月 2,000 万） | M10 PTFE/Q 布国产化（日东纺扩产释放窗口）；国产高容 MLCC（风华+三环 6S 200μF）；HVLP4 国产铜箔进 M10 |
| **机会但 NVDA 链卡死** | DrMOS 进 NVDA 仅 Rubin/Ultra 新料号窗口 [[摘要-domestic-drmos-suppliers-2026-06-02]]；MLCC 高容 vs 日韩落后 2 代 | TLVR 国产顺络/铂科仍 indirect via MPS/IFX 间接供应 | 800V HVDC 主供已锁=台达/光宝/维谛/麦格米特 |
| **物理上几乎不可替代** | HBM4 / CoWoS / Vera CPU / TGV / 5706 三井铜箔 | 同左 | 同左 |

### 3.3 "日系/海外寡占 + 国产排不进去" 清单（最坚固的 Beta）

- **HBM**：美光+海力士+三星，TSV 设备美/日寡占，国产 0 路径
- **CoWoS**：TSMC + AMKR + 日月光寡占，国产 0
- **Q 布 / T-glass**：日东纺垄断（94 年）
- **流延机**：日本 Hirano Tecseed 等寡占 [[摘要-mlcc-tape-casting-machine-2026-06-02]]
- **HVLP4 铜箔**：三井金属 + 国内德福双寡头 [[摘要-msap-process-pcb-2026-06-02]]
- **高端 MLCC**：村田 45% + 三星电机 30% + 太阳诱电 15%（全球 CR3 = 90%）[[摘要-mlcc-domestic-progress-2026-06-04]]
- **钽电容**：CR4 96%（KEMET+AVX+Panasonic+Vishay）[[摘要-ai-capacitor-deep-compare-part2-2026-06-04]]
- **电源 MOS**：英飞凌+安森美 60-70% [[摘要-rubin-power-chain-2026-06-05]]

## 四、价值量分布与 Alpha 集中度

### 4.1 整柜价值估算（Rubin Ultra Kyber，~$12-15M / 柜）

按 Rubin Ultra 整柜 USD 估算[[摘要-ai-capacitor-deep-compare-part2-2026-06-04]]：

| BOM 类别 | 单柜估值（$） | 占比 | 备注 |
|---|---|---|---|
| GPU + HBM + CoWoS（核心算力） | 数百万 USD | **大头但 +57% 涨幅最小** | [[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]] |
| PCB 子系统（含正交背板） | $117K | ~1% | **+233% 涨幅，剪刀差最大** [[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]] |
| 电源链（PSU+DrMOS+磁/电感） | $10K+（DrMOS）+ PSU 大头 | ？(待补) | 18.3kW 模块价值量大增 [[摘要-rubin-power-chain-2026-06-05]] |
| 电容总（薄膜+LIC+钽+MLCC+电解） | $120-150K | ~1% | **6-7× vs GB300** [[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] |
| 液冷自供 | $8-10K | <0.1% | [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] |
| 水冷板 | ~$150 × 多颗 | <0.1% | [[摘要-server-cooling-rubin-2026-06-05]] |
| 机壳 | $35K | ~0.3% | [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] |
| 电容总（MLCC 48 万颗 × 平均价 + 钽 5,000 + LIC 396 + 薄膜 + 牛角）| ~$120-150K | ~1% | **机柜内 #1 新王 = LIC + 薄膜** |
| 钽电容 5,000 颗 × ¥1-3 / 颗 = ¥5-15K = ~$700-2,000 | ~$700-2K | <0.1% | [[摘要-tantalum-capacitor-2026-06-05]] |
| 单 LIC：396 颗 × $40-50 | **$12-15K** | ~0.1% | [[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] |
| 单薄膜电容（Rubin Ultra 新王）| **$18-36K** | ~0.2-0.3% | [[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] |

> **关键结论**：单一组件价值量虽小（<1% 整柜），但**「弹性 × 倍数」最大** 的环节集中在 PCB 子系统 + 电容（LIC/薄膜/钽/MLCC）+ 电源链。GPU 本身涨幅最小（+57%）= 涨价被 NVDA 自己截走；产业链能切到的 Alpha 在 **物理刚性强制下游升级且供应商 CR 高** 的环节。

### 4.2 配 [[Beta_Alpha锚点框架]] 的判别

| 组件 | Beta（下游量纲）| Alpha（物理刚性 / CR）| 总评 |
|---|---|---|---|
| **PCB（正交背板/78 层/PTFE）** | NVDA 出货 + 机柜数 | 224Gbps PAM4 + 56GHz Nyquist + 趋肤深度 0.28μm 物理刚性 + 沪电/深南/欣兴/TTM CR4 | **Alpha 上限最高** |
| **MLCC（高容）** | 服务器台数（被宏观/CapEx 拖）| 物理刚性=DRMOS 多相 × 0.8V × 1250A 强制 + X6S/X7R + 01005 + 30-50% ASP 溢价；村田+三星电机 CR2 = 75% | **Alpha = "定价锚点 DrMOS" 物理刚性** [[摘要-mlcc-drmos-pricing-anchor]] |
| **钽电容** | AI 服务器 + 企业 SSD | 五氧化二钽多孔结构 + 宽温 -55~+150℃；CR4 96% | **Alpha 最高（CR 最高）** |
| **超级电容 LIC** | GB300+ 标配 / NVL72 132kW | μs-ms 暂态真空区物理刚性；武藏 650 vs 1,500-1,800 万缺口 | **Alpha 强（先发 + 缺口）** |
| **薄膜电容（Rubin Ultra）** | 800V HVDC 演进时点 | 自愈 KV 级耐压物理刚性；法拉电子 ROE 19-22% | **Alpha 高（非线性阶跃）** |
| **DrMOS** | GPU 数 × 相数 | 6,000 颗/柜 × ASP；CR=IFX+瑞萨+MPS | Alpha 中（无新供应商窗口）|
| **PSU 18.3kW** | NVDA 整柜出货 | 全液冷 + SiC + HVDC + 超容集成壁垒 | Alpha 高但**国产 2 代差** |
| **HVDC + SST** | Rubin Ultra 渗透率 | 1200V SiC + 高频开关 + 系统集成 | Alpha 高，国产台达/光宝/维谛/麦格米特先发 |
| **液冷板/TIM** | 整柜数量 | 铲齿工艺技术门槛低，CR 低 | **Beta 为主，Alpha 弱** |
| **PCB 钻针 50 倍** | NVDA 机柜数 | 50 倍长径比物理工艺极限；国内本公司+佑能寡占 | **Alpha 极强** |

## 五、可投资清单（按价值弹性 + 国产化窗口排序）

### 5.1 第一梯队（确定性高 + 国产已切入）

| 排名 | 公司 | 受益逻辑 | 风险 |
|---|---|---|---|
| 1 | [[002463 CH 沪电股份]] | Rubin Ultra 正交背板代工厂倾向给一半份额；PCB 子系统 $117K/柜 [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]]、[[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]] | PTFE 工艺良率 70% / 2026 Q3-Q4 NVDA code 批准窗口 |
| 2 | [[300861 CH 法拉电子]] | Rubin Ultra 800V 薄膜电容单柜 $18-36K 跳升；ROE 19-22% / 毛利 33-39% [[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] | 800V HVDC 落地节奏不及预期 |
| 3 | [[300726 CH 宏达电子]] | 钽电容 CR4=96% + Rubin 5,000 颗/柜 + 涨 50-60% + S 公司 PCB 引脚专利 [[摘要-tantalum-capacitor-2026-06-05]] | KEMET/AVX 扩产挤压国产空间 |
| 4 | [[600673 CH 东阳光]] | LIC 月 25 万 → 扩产 1,500 万 → 2027 月 2,000 万；台达 ¥8.5/颗；AI 收入 ¥10 亿目标 [[摘要-ai-server-capacitor-domestic-2026-06-01]] | 武藏 650 万产能扩张 + 价格博弈 |
| 5 | [[300476 CH 胜宏科技]] | PCB 二梯队冲刺 MSAP / Rubin Ultra PVT2 阶段 + 包欧姆龙 X 光对位机产能 | 一线沪电/深南/欣兴产能锁单 |
| 6 | [[600183 CH 生益科技]] | M8/M9 CCL 升级；NVDA Switch 20-30% 份额 [[摘要-ccl-rubin-glass-fiber-2026-06-01]] | 难升一供 / Low Dk 二代玻璃布国际复材瓶颈 |
| 7 | [[002138 CH 顺络电子]] | TLVR 电感 NVDA 间接供应；2025 营收 ¥2 亿 [[摘要-passive-2-tantalum-inductor-2026-06-03]] | Rubin 厚度要求 + 价格博弈 |
| 8 | [[300408 CH 三环集团]] | MLCC 唯一纯产能扩张玩家：150 → 400-450 亿颗；湿法工艺替代 [[摘要-mlcc-domestic-progress-2026-06-04]] | vs 村田/三星电机 2 代差 |
| 9 | [[688141 CH 杰华特]] / [[688368 CH 晶丰明源]] | DrMOS 国产领先；杰华特已是华为 #1 [[摘要-drmos-expert-2026-06-04]] | NVDA 链卡死，主要走华为/海光/谷歌台达代供 |

### 5.2 第二梯队（高弹性但风险偏大）

- **PCB 钻针**：鼎泰高科 + 尖点科技（50 倍长径比 + 月 1.2 亿支 2026 底产能）[[摘要-pcb-drill-pin-rubin-2026-06-04]]
- **液冷一次侧**：[[002837 CH 英维克]] / [[300499 CH 高澜股份]] / 申菱 / 阳光电源
- **PTFE 上游**：巨化 / 东岳 / 昊华 / 三美（电子级仍需突破）[[摘要-ptfe-strategic-material-2026-06-02]]
- **铝电解（中短期）**：东阳光 / 江海股份 / 艾华集团
- **HVDC 主供**：[[2308 TT DELTA]] / 光宝 / 维谛 / 麦格米特 / 欧陆通 / 阳光电源
- **18.3kW PSU 国产突破**：[[2308 TT DELTA]] / 全汉 + 国内 2027 入场
- **TGV 玻璃基板**：康宁 [[GLW US]] / 台积电 / 日月光（国产 0）

### 5.3 海外龙头（NVDA 链上锁定的 Alpha）

- [[NVDA US]]：核心 + Vera CPU + CX9 软件栈
- [[2330 TT  TSMC]]：CoWoS + 4N/3N
- [[AMKR US]] / [[3711 TT 日月光投资控股]]：CoWoS-R 100% 外包
- [[MU US]] / [[000660 KS]] / [[005930 KS]]：HBM4 寡头
- [[IFX GY]] / [[6723 JP]] / MPS：DrMOS 海外三巨头 + PSU MOS
- [[2317 TT Hong Hai]]：液冷自供 75%+ + CPO 交换机独家
- [[3407 JP]]（日东纺）：Q 布垄断 → Rubin Ultra 关键
- [[村田]] / [[三星电机]] / [[太阳诱电]]：高端 MLCC CR3 90%
- KEMET / AVX：钽电容 CR2 72%
- [[5706 JP]]（三井金属）：HVLP4 铜箔双寡头之一
- [[2308 TT DELTA]] / 光宝 / 维谛：HVDC + 18.3kW PSU

## 六、关键不确定性

1. **Rubin GPU TDP 2300W 是否真能落地**：物理上 0.8V × 1250A+ 已逼近 PCB / DrMOS 散热极限 → 2.3kW 需 Rubin Ultra 时 0.1mm 微通道 + 12 相 DrMOS + 12V→1V 直降；若延后到 0.8V → 0.6V，整套 BOM 推迟。[[摘要-mlcc-drmos-pricing-anchor]]
2. **800V HVDC 渗透节奏**：2026H2 小批量；NVDA 主导 800V vs 谷歌 ±400V；薄膜电容 $18-36K/柜的跳升完全锁在 800V 上 → 若延迟一年 Alpha 兑现节奏推迟。[[摘要-secondary-power-hvdc-nvda-google-2026-06-03]]、[[摘要-ai-capacitor-deep-compare-part2-2026-06-04]]
3. **Q 布日东纺 2027-28 扩产释放节奏**：若提前一年=PTFE 路线变压力小、M9+Q 布主流；若延后=PTFE 必须工程突破，Rubin Ultra 出货推迟。[[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]]
4. **PTFE 良率 70% → 75%+**：单块报废损失万美元级；Rubin Ultra 量产能否在 2027 H2 准时 = NVDA code 2026 Q3-Q4 批准 + 良率窗口 2026 Q4-2027 Q2。[[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]]
5. **HBM4 TSV 设备交期**：纯交期 >6 月还在拉长；通霄厂 FY28 仅 2-3 万片 = 杯水车薪。决定 NVDA/AMD 究竟能拿多少 HBM。[[摘要-hbm-tsv-equipment-leadtime-2026-06-07]]
6. **CoWoS 2028 仍紧张 vs 博通转 Intel EMIB 20-30%**：若 Intel EMIB 良率不及 60%，TPU 600 万颗 2027 拿不到产能，NVDA 反享更多 CoWoS。[[摘要-na-asic-2-cowos-emib-2026-06-03]]
7. **国产 DrMOS 进 NVDA 链**：分析师口径"Rubin/Ultra 才有新料号窗口"——但 NVDA 选 IFX/瑞萨/MPS 不缺货，国产实际进入概率多大？[[摘要-domestic-drmos-suppliers-2026-06-02]]、[[摘要-power-chip-drmos-fivr-2026-06-05]]
8. **整柜价值量 $12-15M 测算口径**：来自 [[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] "Rubin Ultra 整柜估算"，与单柜实际报价的对应关系待 2026 H2 发布验证；目前 VR NVL72 报价 ¥650 万 ≈ $90K 是小柜版本 [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]]。
9. **市场基准 290-367 亿 RMB（CoWoP/CPO 下 145-193）**：若 CPO 大规模替代正交背板 → 正交背板市场被压一半。[[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]]

## 七、关联连接

### 概念
- [[Beta_Alpha锚点框架]] — 抓 Alpha 应锚定底层物理刚性（DRMOS 相数 / 趋肤深度 / TSV 深宽比）而非外生周期
- [[DRMOS]] — Rubin BOM 定价锚点
- [[MLCC_AI服务器需求]] — 量价齐升双驱动
- [[800V HVDC]] — Rubin Ultra Kyber 参考架构
- [[CCL覆铜板]] — Rubin M8.5/M9 升级倒逼
- [[MSAP]] — Rubin Ultra/Feynman 全用
- [[正交背板]] — Rubin Ultra 新增 PCB 子系统
- [[TGV玻璃基板]] — 5-15% 渗透率（未来 3-5 年）
- [[3.2T技术路线]] — 下一代光通信路线
- [[CPO]] — 与 Rubin 同步绑定 6 月验证期
- [[DataCenterArchitecture]] — AI 工厂演进

### Sources（全部 33 篇）
**算力核心**：
- [[摘要-jensen-huang-vera-rubin-gtc-taipei-2026-06-01]] — GTC keynote 主旨
- [[摘要-vera-cpu-platform-2026-06-01]] — Vera CPU 重做底座

**电源链**：
- [[摘要-rubin-power-chain-2026-06-05]] — 18.3kW PSU 价值量大增
- [[摘要-secondary-power-hvdc-nvda-google-2026-06-03]] — 二次电源 + HVDC 时点
- [[摘要-domestic-drmos-suppliers-2026-06-02]] — 国产 DrMOS 进展
- [[摘要-drmos-expert-2026-06-04]] — DrMOS 国产突破
- [[摘要-power-chip-drmos-fivr-2026-06-05]] — DrMOS/FIVR/SST 大厂
- [[摘要-mlcc-drmos-pricing-anchor]] — 定价锚点框架

**PCB / CCL / 基板**：
- [[摘要-pcb-drill-pin-rubin-2026-06-04]] — Rubin 一拖四 50 倍长径比
- [[摘要-rubin-ultra-orthogonal-ptfe-2026-06-07]] — 78 层正交背板 + PTFE
- [[摘要-ccl-rubin-glass-fiber-2026-06-01]] — Rubin CCL 升级 + 玻璃布瓶颈
- [[摘要-msap-process-pcb-2026-06-02]] — MSAP 取代 HDI
- [[摘要-glass-substrate-interposer-2026-06-01]] — 玻璃基板渗透节奏
- [[摘要-ptfe-strategic-material-2026-06-02]] — PTFE 战略材料化

**被动元件**：
- [[摘要-ai-server-passive-tantalum-2026-06-03]] — AI 服务器钽电容 + 芯片电感
- [[摘要-tantalum-capacitor-2026-06-05]] — Rubin 5,000 颗钽电容
- [[摘要-passive-2-tantalum-inductor-2026-06-03]] — TLVR 电感
- [[摘要-mlcc-domestic-progress-2026-06-04]] — GB200 60 万颗/柜 + 国产进展
- [[摘要-domestic-mlcc-high-cap-2026-06-01]] — 风华 vs 日韩 2 代差
- [[摘要-mlcc-tape-casting-machine-2026-06-02]] — MLCC 流延机
- [[摘要-supercap-lic-edlc-ai-2026-06-03]] — LIC/EDLC 分工
- [[摘要-ai-server-capacitor-domestic-2026-06-01]] — 东阳光铝电解+LIC
- [[摘要-japan-capacitor-cap-import-2026-06-03]] — 武藏导入 + Sidecar
- [[摘要-ai-capacitor-deep-compare-part1-2026-06-02]] — 电容横向比较（上）
- [[摘要-ai-capacitor-deep-compare-part2-2026-06-04]] — 电容横向比较（下，单柜 ASP 矩阵）

**散热 / 液冷**：
- [[摘要-server-cooling-rubin-2026-06-05]] — Rubin 石墨烯 TIM + 0.1mm 微通道
- [[摘要-google-liquid-cooling-pcb-trainium-2026-06-02]] — 谷歌一拖八 + HVDC
- [[摘要-liquid-cooling-supply-chain-2026-06-03]] — 1GW 液冷价值量 ¥35-40 亿
- [[摘要-rubin-liquid-cooling-cpo-switch-elasticity-2026-06-01]] — VR 自供 75% + CPO 独家

**封装 / CoWoS / HBM**：
- [[摘要-tsmc-cowos-soic-glass-2026-06-02]] — CoWoS 产能 + Vera CPU CoWoS-R
- [[摘要-na-asic-2-cowos-emib-2026-06-03]] — Intel EMIB 备份路径
- [[摘要-hbm-tsv-equipment-leadtime-2026-06-07]] — HBM TSV 设备交期是总闸门
- [[摘要-storage-supply-gap-2027-2026-06-02]] — DRAM/NAND 缺口至 2027

### 主要 Entities
- [[NVDA US]] / [[2330 TT  TSMC]] / [[AMKR US]] / [[3711 TT 日月光投资控股]] / [[MU US]] / [[000660 KS]] / [[005930 KS]] / [[IFX GY]] / [[6723 JP]] / [[2317 TT Hong Hai]] / [[2308 TT DELTA]] / [[GLW US]] / [[INTC US]] / [[AMD US]] / [[GOOGL US]] / [[META US]] / [[AVGO US]]
- [[002463 CH 沪电股份]] / [[002916 CH 深南电路]] / [[002938 CH 鹏鼎控股]] / [[300476 CH 胜宏科技]] / [[600183 CH 生益科技]] / [[300861 CH 法拉电子]] / [[300726 CH 宏达电子]] / [[600673 CH 东阳光]] / [[002484 CH 江海股份]] / [[300408 CH 三环集团]] / [[000636 CH 风华高科]] / [[002138 CH 顺络电子]] / [[688141 CH 杰华特]] / [[688368 CH 晶丰明源]] / [[002837 CH 英维克]] / [[300499 CH 高澜股份]] / [[3653 TT 健策精密工业]]

---

*最后更新：2026-06-07*
*这是 5 批 ingest（161 篇 sources）后的第二篇横向综合分析。BOM 矩阵共 30+ 行覆盖算力/封装/PCB/CCL/基板/电源/被动/散热/网络七大类，含数 cell 与「？(待补)」cell 比 ~75:25——未填的主要在 H100/B200 历史口径数据与 Rubin Ultra 整柜价值结构内部分配。后续可在 NVDA 2026 Q3 财报 + Rubin 量产实测数据后补全。*
