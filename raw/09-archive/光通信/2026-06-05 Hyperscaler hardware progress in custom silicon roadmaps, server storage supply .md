---
title: "2026-06-05 Hyperscaler hardware progress in custom silicon roadmaps, server storage supply tightness, and Next-Gen optical network scaling"
aliases:
  - "Hyperscaler hardware progress in custom silicon roadmaps, server storage supply tightness, and Next-Gen optical network scaling"
date: 2026-06-05
source: acecamptech.com
type: expert
url: "https://www.acecamptech.com/article/detail/70563004"
tags: ['AI推理', 'AI训练', 'ASIC', 'Scaling Law', 'TMT']
companies: ['AMD', 'Astera Labs', 'Broadcom', 'Coherent', 'Lumentum', 'Marvell', 'Meta', 'Micron', 'NVIDIA', 'Rambus', 'SK Hynix', 'Samsung', 'TI']
tickers: ['000660 KS', '005930 KS', 'AMD US', 'AVGO US', 'BC94 LN', 'COHR US', 'LITE US', 'META US', 'MRVL US', 'MU US', 'NVDA US', 'RMBS US', 'TXN US']
---

# Hyperscaler hardware progress in custom silicon roadmaps, server storage supply tightness, and Next-Gen optical network scaling

**日期**: 2026-06-05 | **来源**: acecamptech.com | **公司**: AMD, Astera Labs, Broadcom, Coherent, Lumentum, Marvell, Meta, Micron, NVIDIA, Rambus, SK Hynix, Samsung, TI | **标签**: AI推理, AI训练, ASIC, Scaling Law, TMT | **Ticker**: 000660 KS, 005930 KS, AMD US, AVGO US, BC94 LN, COHR US, LITE US, META US, MRVL US, MU US, NVDA US, RMBS US, TXN US

## 问答
### Q1: What are the expected XPU ASIC volumes for 2026 and 2027, what is the current status of the Broadcom project, and how does this relate to GPU saturation and CPU attach ratios?

Near-term XPU ASIC volumes are projected to reach substantial levels, primarily comprising major cloud provider TPU-class, MTIA-class, and custom ASIC programs for leading AI labs. Moving into the medium term, these volumes are expected to see significant growth, contingent on advanced packaging, high-bandwidth memory, and high-speed Ethernet supply remaining on track. The primary semiconductor vendor involved has reported strong AI momentum with multi-billion dollar quarterly revenues, driven by custom XPUs and AI networking.
The project is progressing but is adjusting from its original schedule. The constraints are better described as supply-limited and phased rather than delayed. The primary bottlenecks are not in silicon production but in packaging, memory allocation, rack integration, firmware maturity, and scale-out networking. Consequently, the immediate focus is on high-confidence inference and training pods, with true high-volume deployment anticipated in the subsequent phase.
As GPU saturation increases—though traditional GPU clusters remain the standard for frontier model training—hyperscalers are shifting a notable portion of their inference and internal training workloads to XPUs once those workloads stabilize. This shift is driven by the potential for a significantly lower cost per token on XPUs. In this context, the CPU attach ratio is expected to remain standard, with a single server CPU complex supporting multiple XPUs.

### Q2: What is the total volume forecast for MTIA in 2026, and could you provide a breakdown by different MTIA versions?

The total volume for MTIA in 2026 is estimated to be in the hundreds of thousands of accelerators. The project is not considered failed or delayed but is ramping up more slowly than initially planned. The breakdown by version for 2026 is as follows: MTIA 200 is projected to account for a significant volume, primarily for inference workloads already in production for ranking and recommendation. The MTIA 300 is expected to be of a comparable magnitude, representing the main ramp for 2026. The MTIA 400 is forecasted at a smaller initial volume. Meta has confirmed that the MTIA 300 is deployed and operational, with the MTIA 400, 450, and 500 models staged for rollout in late 2026 and throughout 2027 as part of a massive, multi-year first-phase deployment with Broadcom.

### Q3: What is the ASP structure for Broadcom's XPU sales to hyperscalers at different levels of integration, and how does the per-chip ASP vary across MTIA versions?

The ASP for Broadcom's silicon varies by the level of integration. The compute die alone, excluding HBM and packaging, is priced in the mid-single-digit thousands of dollars. A packaged XPU with advanced packaging costs slightly below ten thousand dollars. The full XPU module with HBM attached has an ASP ranging from the mid-teens to over twenty thousand dollars for the hyperscaler customer. At the chip level, excluding HBM, the blended ASP is in the mid-thousands of dollars. This varies by MTIA version: the MTIA 200 chip is priced at the lower end of this range; the MTIA 300 chip sits in the middle of the range; and the MTIA 400 chip is positioned at the higher end. The price for the MTIA 400 is higher due to its larger die area, increased I/O, and greater packaging complexity, reflecting Meta's demand for higher performance per accelerator.

### Q4: What is the current GPU-to-CPU attach ratio for AI workloads, and how is it expected to change by 2028?

The current attach ratio is generally 4 to 8 GPUs per one host CPU socket. For frontier training workloads, the ratio is 8 GPUs to 1-2 x86 CPU sockets in 2026 and is expected to remain at 8 GPUs to 1-2 CPUs in 2028. For standard LLM inference, the ratio is 8 GPUs to 1 CPU in 2026, evolving to a range of 8-12 GPUs per CPU by 2028. For agentic inference involving tools and RAG, the ratio is currently 5 GPUs to 1 CPU and is projected to become 8 GPUs to 1 CPU in 2028. For custom inference with MTIA, the ratio is 6 accelerators to 1 CPU in 2026 and is expected to shift to 12 accelerators to 1 CPU by 2028. Agentic workloads are proving to be less GPU-centric than standard chat inference, driving more CPU-side work.

### Q5: What are the Q2 2026 sequential price increases for server DRAM, and what is the structure of the Long-Term Agreements being established with suppliers?

In Q2 2026, server DRAM prices are increasing significantly. For HBM3e (12-high), the quarter-over-quarter price increase is 12-20%. For DDR5 RDIMMs (128GB to 256GB), the increase is 8-15%. The blended price for standard server DRAM is up 6-10% quarter-over-quarter. HBM remains the most constrained component due to AI accelerator demand outpacing packaging capacity.
The LTAs with suppliers like SK Hynix, Samsung, and Micron are structured around four key elements:
· Volume Reservation: Committing to wafer starts or gigabyte capacity with 12-24 months of forward visibility and quarterly take-or-pay bands, which include a flex window of +/- 10-15%.
· Prepayment and Deposits: Upfront prepayments of 10-20% for strategic components like HBM are common to secure allocation priority, amounting to $1-3 billion in capital pre-commitments across suppliers.
· Formula-Based Pricing: Prices are not fixed but are set using a formula that includes a base floor, a quarterly index reset, and a yield/stack adjustment, protecting both the supplier and the buyer from pure spot market volatility.
· Supplier Diversification: A typical supply split is 45-55% from SK Hynix, 25-35% from Samsung, and 15-25% from Micron to avoid over-dependence on a single vendor.

### Q6: What is the general framework for determining DRAM volume requirements for GenAI compute, considering both bottom-up and top-down approaches?

Total DRAM requirements are determined by running bottom-up and top-down models in parallel to reconcile physical deployments with workload forecasts.
· Bottom-Up Model: Calculates total demand by multiplying hardware counts by average DRAM per system. Standard allocations include: 1P ARM web servers (384–768 GB), 2P x86 general servers (1–2 TB), GPU host servers (1.5–3 TB), and MTIA inference hosts (512 GB–1 TB).
· Top-Down Model: A workload-driven framework consisting of three steps:
1. Forecast Compute Demand: Projecting requests, such as 4 billion daily chat queries or 300 million agentic workflows (averaging 40 tool calls daily).
2. Convert to vCPU Requirements: Translating request volume into total vCPU seconds based on complexity (e.g., 0.4–0.8 vCPU/sec for simple chat vs. 8–30 vCPU/sec for agentic workflows).
3. Apply Memory-per-vCPU Ratios: Multiplying vCPU counts by workload-specific memory ratios, ranging from 2–4 GB for web serving, 6–12 GB for caching, 8–16 GB for agentic inference, up to 16–32 GB for vector databases.
Example Projection (2027): A fleet running 250 million concurrent vCPUs at a blended 6 GB/vCPU yields a baseline of 1.5 exabytes of installed DRAM. After factoring in buffers (20% headroom,10% stranded capacity, and 5% spares), the final procurement target reaches 2 exabytes, which is then mapped to annual hardware refresh and expansion cycles.

### Q7: What are the significant trends in the DRAM market, and which vendors are leading in CXL technology?

Several key trends are shaping the DRAM market. HBM is cannibalizing conventional DRAM capacity as major manufacturers reallocate wafers and capex towards HBM, which keeps the DDR5 server DRAM market tighter than usual. Server DRAM attach rates are rising faster than CPU unit growth, particularly for AI host servers and retrieval systems. Additionally, CXL memory pooling is becoming important starting in 2027, not to replace DRAM, but to reduce stranded memory by 10% to 20%. Consequently, DRAM is evolving from a commodity component into a capacity bottleneck for AI, similar to networking and power.
Regarding CXL providers, Astera Labs is the strongest pure-play CXL and memory connectivity vendor. Broadcom is a strong contender, especially if CXL becomes integrated into broader PCI Ethernet ASIC platforms. Following them are Microchip and Marvell, with other players including Rambus and Montage. Astera Labs is positioned to win in the early CXL market.

### Q8: What is the current pricing trend for enterprise SSDs, what are the procurement forecasts for 2026 and 2027, and what is the structure of the long-term agreements for NAND?

·  Market&Pricing: Enterprise SSD supply is tighter than DRAM. In Q2 2026, NAND contract prices surged 70%–75% QoQ, driven by intense AI and server demand diverting capacity from consumer segments.
·  Demand Forecast: Driven by AI data workloads, NAND procurement is projected to reach 90–130 exabytes in 2026 (+55%–75% YoY) and 140–210 exabytes in 2027 (+50%–65% YoY).
·  LTA Structure: Hyperscalers secure 12–24 month capacity (up to 36 months strategically) with major suppliers (Samsung, SK Hynix, Solidigm, Micron, WD). These LTAs feature take-or-pay bands, quarterly formula-based price resets,10%–20% volume flexibility, and 5%–15% upfront prepayments.
·  TLC vs. QLC Shifts: High-capacity QLC is rapidly becoming the dominant tier for bulk AI storage (datasets, embeddings, retrieval) where cost-per-terabyte matters more than endurance. TLC remains reserved for high-write workloads like checkpointing and hot caching.

### Q9: What is the assessment of hybrid SLC/TLC high-IOPS SSDs, their use cases, and their impact on DRAM and TLC SSD procurement?

High-IOPS hybrid SLC/TLC SSDs are being tested for performance-tier applications such as AI checkpoint staging, log ingestion, and write buffers. They are not considered a bulk NAND tier. Their primary use case is for hot write cache and metadata, where their excellent latency and endurance are beneficial. In contrast, standard enterprise TLC SSDs are used for production hot cache and high-write workloads, while high-capacity QLC SSDs serve as the warm AI data tier for vector pages and RAG corpora, offering the best cost per terabyte.
These hybrid drives constitute 5% to 10% of SSD procurement and are deployed only when the bottleneck is random write IOPS or tail latency, not capacity. They can slightly reduce pressure on DRAM, perhaps by 3% to 8%, but their main impact is reducing the need to over-procure standard TLC SSDs.

### Q10: What is the current pricing for different types of enterprise SSDs, and how have prices increased recently?

The pricing per gigabyte varies significantly across different SSD tiers. For hybrid SLC/TLC high-IOPS SSDs, the price is $0.18 to $0.30 per GB. Standard TLC enterprise SSDs are priced at $0.09 to $0.14 per GB. High-capacity QLC SSDs (122 TB or higher) are the most cost-effective at $0.05 to $0.08 per GB.
The price increases in Q2 2026 were not uniform. The high-IOPS SSDs saw a 12% to 18% quarter-over-quarter increase. Standard TLC enterprise SSDs experienced a higher increase of 18% to 28%. The high-capacity QLC SSDs had the sharpest rise, with prices increasing by 25% to 40% quarter-over-quarter.

### Q11: What are the procurement forecasts for AMD's MI350, MI400, and MI450 GPUs for 2026 and 2027, along with their respective ASPs?

The procurement plans for AMD GPUs are as follows:
· MI350: Several tens of thousands of units in 2026, decreasing to a smaller volume of roughly ten to thirty thousand units in 2027. The ASP is in the low-to-mid twenty thousand dollar range, with a budget midpoint around twenty-one thousand dollars.
· MI400: Close to a hundred thousand units in 2026, increasing significantly to well over two hundred thousand units in 2027, making it the main platform. The ASP spans from the low-to-high twenty thousand dollar range, with a budget midpoint around twenty-five thousand dollars.
· MI450: Minimal to negligible volume in 2026, ramping up significantly to around one hundred thousand units in 2027. The ASP is in the around thirty thousand dollar range, with a budget midpoint of thirty-one thousand dollars.

### Q12: What is the total spending forecast on Arista for 2025-2027, and are there any supply constraints affecting them?

The spending on Arista was projected at around four billion dollars in 2025, representing a mid-double-digit percentage year-over-year increase. For 2026, the forecast rises to the mid-to-high single-digit billions of dollars, reflecting a near-fifty percent increase. For 2027, spending is expected to scale further into the high single-digit billions, maintaining a strong double-digit growth rate.
There are supply constraints, with the most significant being optical transceivers, specifically 800G and 1.6T models, which are the primary gating items. Other constraints include switch ASIC packaging and SerDes for the latest Tomahawk and Jericho-class chips, which is a high-severity issue. Co-packaged optics readiness is a medium-severity concern, along with PSUs and power shelves. The main bottleneck is optics, not the switch chassis itself. Often, the Arista chassis is available, but scaling the cluster is limited by the availability of sufficient 800G and 1.6T optics and cables.

### Q13: What are the current lead times for 800G and 1.6T networking components?

Current lead times for high-speed networking components are extended. For 800G, optical transceivers have a lead time of 20 to 32 weeks, DAC/AEC cables are 12 to 20 weeks, and switch systems are 16 to 26 weeks. For 1.6T, the lead times are even longer: optical transceivers are 36 to 52 weeks, and switch systems are 30 to 45 weeks, depending on Broadcom or NVIDIA ASIC availability and thermal validation. In summary, 800G components have a lead time of roughly 5 to 8 months, while 1.6T components require 9 to 12 months for any significant volume.

### Q14: How are optical transceivers procured, and what is the current pricing for 800G and 1.6T models?

Procurement of optical transceivers is handled through a hybrid model. Direct procurement from vendors like Coherent, InnoLight, Eoptolink, and Lumentum accounts for a clear majority share, roughly two-thirds of the total. This approach provides better allocation control, lower unit costs, and multi-vendor qualification. The remaining share is procured as bundled components: around a quarter with Arista switch systems and the remaining minority share with NVIDIA networking and NVL systems for InfiniBand/Ethernet GPU clusters.
Current and projected pricing for transceivers is as follows:
· 800G SR: Mid-hundreds of dollars in 2026, dropping to the lower-to-mid hundreds in 2027.
· 800G DR/FR: Around one thousand dollars in 2026, dropping to the high hundreds in 2027.
· 800G ZR Coherent DCI: Several thousand dollars in 2026, dropping slightly to a lower multi-thousand-dollar range in 2027.
· 1.6T Short Reach: In the lower thousands of dollars range in 2026, dropping toward the low-to-mid one thousand dollar range in 2027.
· 1.6T FR: Multi-thousand dollars in 2026, dropping to around two to three thousand dollars in 2027.
· 1.6T Coherent DCI: High single-digit to low double-digit thousands of dollars in 2026, dropping to the mid-to-high single-digit thousands in 2027.

### Q15: What is the expected market share evolution for 1.6T optical transceiver vendors from 2026 to 2028?

In 2026, the 1.6T market is concentrated among a few qualified vendors. Coherent leads with a 25-35% share, followed by InnoLight at 20-30%. Eoptolink holds 10-18%, Lumentum and CloudLight have 10-15%, Hisense and Source Photonics have 5-10%, and the Fabrinet ecosystem has 8-12%.
Over time, the supplier base is expected to diversify to reduce concentration. By 2028, Coherent's share is projected to decrease to 18-25%, while InnoLight's share will increase to 25-35%. Eoptolink is expected to grow to 15-22%. Lumentum and CloudLight's share will adjust to 8-12%, while Hisense, Source Photonics, and others will grow to 10-15%. The Fabrinet ecosystem's share is expected to remain stable at 8-12%.

### Q16: Who are the dominant vendors for 1.6T ZR coherent DCI modules, and what is Lumentum's role in this market?

The market for 1.6T ZR coherent DCI modules is narrow. The dominant vendors supplying Meta are Coherent (25-35% share), Ciena/WaveLogic (20-30% share), and Cisco/Acacia (15-25% share). Other suppliers include Lumentum/CloudLight (10-15%), Marvell (8-15% content share), and Infinera/Nokia (5-10%). The selection in this segment is driven more by DSP maturity, power envelope, thermal performance, and long-haul operational reliability than by module cost alone.
Lumentum primarily functions as a key component supplier, providing EMLs, tunable lasers, and optical subassemblies to the module manufacturers, rather than shipping fully integrated 1.6T coherent transceiver modules directly. While they have full pluggable transceiver-like modules, they lack a coherent DSP. The final pluggable system is integrated by vendors like Coherent, Ciena, and Cisco, who incorporate DSPs from providers like Marvell and Cisco. Therefore, when considering who ships the final working ZR module, the main suppliers are Coherent, Ciena, and Cisco, with Lumentum being a critical supplier within their bill of materials.

### Q17: Why is Nokia's share in the 1.6T coherent DCI vendor mix expected to remain stable rather than increase, despite their available manufacturing capacity?

Nokia's share is not increasing materially for several reasons, as capacity is not the sole determining factor for allocation. The primary considerations are system risk-adjusted deployability and operational factors.
First, there is significant operational inertia with the installed base of Ciena and Cisco systems. Expanding aggressively with a new vendor would require new telemetry integration, different sparing pools, and managing different DSP behaviors in production, creating substantial operational switching costs.
Second, DSP and link performance consistency are critical. The network is highly sensitive to power-per-bit, reach margin, and bit error rate performance. Even with available capacity, a vendor with better real-world performance consistency, like Ciena, may be preferred for critical routes.
Third, a deliberate supplier concentration strategy is in place to maintain pricing leverage and avoid over-reliance on any single vendor, even one with ample capacity. The focus is on deployable, qualified throughput, where factors like route qualification, interoperability, and operational scaling are the true bottlenecks, not just module manufacturing availability.

### Q18: What are the expected vendor shares for the upcoming DCI request for quotes, and what factors might influence the final allocation?

For the next DCI coherent optics order, the expected awarded share for Ciena is 28% to 35%, benefiting from its incumbent operational advantage. Coherent is projected to secure 25% to 30% due to strong module performance, while Cisco is expected to receive 18% to 25% based on its strong DSP and coherent roadmap. Nokia is positioned as a credible challenger with an anticipated share of 10% to 18%, which could increase if its pricing is aggressive. Other vendors are expected to collectively receive less than 10% for tactical fills in regional deployments. The most significant swing factor is pricing aggressiveness. For instance, if Nokia offers a very aggressive price, especially when bundled with its line system, software, and support, its share could move from 10% closer to the 15% to 20% range. However, the final decision is driven primarily by operational continuity, which is why Ciena is still likely to win the largest share, even if Nokia has more open capacity.

### Q19: What is the expected total value and unit volume for the next DCI and coherent optics order?

The upcoming Request for Quotation for DCI and coherent optics, intended for the 2027 deployment window, is estimated to have a total award value of approximately $1.5 billion to $2.5 billion. The portion specifically for 1.6T optics is expected to be between $700 million and $1.1 billion. In terms of unit volume, this translates to roughly 80,000 to 140,000 coherent 1.6T module equivalents, with the final number depending on the product mix and pricing.

### Q20: What is the anticipated timeline for the DCI RFQ process, from issuance to the finalization of vendor shares?

The RFQ is expected to be issued in the near term, likely within the next one to two quarters, as the technical requirements are now frozen. The process is projected to unfold as follows: the RFQ will be issued to vendors in the next one to two months. Bids are expected to be returned and pricing rounds will occur during Q3 and early Q4 2026. The vendor down-selection and allocation decisions are scheduled for late Q4 2026. Subsequently, purchase orders will be placed and capacity reservations will be made in Q4 2026 and Q1 2027, with the shipment ramp-up beginning in the second half of 2027. Therefore, the vendor shares will be economically decided during Q4 2026, even though final purchase orders and delivery schedules may extend into early 2027.

### Q21: Given the significant inventory buildup of transceivers, how will future data center deployments be prioritized, and will this affect the deployment of other components like AECs?

The existing inventory of optics changes the primary constraint from procurement to strategic deployment. Future deployments will be prioritized based on the highest ROI per optic consumed, rather than solely on data center shell readiness. The deployment priority is as follows: first, the AI GPU MTIA back-end fabric, due to its high compute utilization leverage. Second, new AI training and high-density inference clusters, as they are directly tied to revenue and the model roadmap. Third, DCI between AI campuses, which becomes necessary as clusters scale across sites. Fourth, general front-end leaf and spine expansion, which can be more easily deferred. The last priority is legacy refreshes and upgrades for lower-utilization data centers. This inventory was built intentionally by overbuying to mitigate unpredictable lead times and long qualification cycles for 2025-2026 optics; carrying a six to twelve-month supply is considered rational. With elevated inventories, the strategy is to deploy them into the highest-power AI sites first and rebalance optics across campuses.

### Q22: With inventories of both optical transceivers and Credo's AEC products on hand, how will their deployment be sequenced and prioritized?

While both optical transceivers and AECs are in inventory, their deployment will be sequenced together where possible, but optics receive priority pull-through. This is because a stranded transceiver is operationally more expensive than a stranded AEC cable. Optical transceivers have the highest near-term deployment priority due to their higher dollar value, longer external lead times, and greater supply risk. Credo's AECs and ADCs are also a high priority but follow optics, as they are easier to replenish, have shorter lead times, and are more substitutable. DAC copper has the lowest near-term deployment priority. In practice, if a link requires both an optic and an AEC, they are deployed together. If optics for a cluster are constrained but AEC inventory is available, the AECs will be held until the matching optics are ready. If optics inventory is elevated, the priority will be to consume those optics first, which in turn pulls through the AECs as part of that deployment wave. The key principle is that optics are the pacing item, and the AEC inventory deployment schedule follows that of the optics.

### Q23: What is the deployment timeline and strategy for pluggables, NPO, and CPO technologies through 2028?

The near-term deployment priority is pluggables first, followed by NPO pilots, and CPO later. For 800G pluggables, 2026 is the production mainstream, 2027 will be high volume, and 2028 will see gradual maturation and cost reduction. For 1.6T pluggables, 2026 involves early production, 2027 will be the main AI ramp, and 2028 will be the mainstream for new AI clusters. NPO is in lab and limited pilot stages this year (2026), with the first meaningful pilots in 2027 and selective production in 2028. CPO is in evaluation only this year (2026), with limited switch fabric pilots in 2027 and early production in the highest-density AI fabrics in 2028. NPO is seen as a more practical intermediate step because its optical engines fit near the package while preserving more serviceability than full CPO. Broad deployment of CPO is not expected before late 2027-2028. In the first half of 2027, the focus will be on consuming the pluggable inventory. NPO pilots will occur in the second half of 2027, and CPO will start in 2028, but only for the densest AI fabrics, likely representing 5% to 10% of new high-end ports.

### Q24: What are the projected unit deployment volumes for NPO and CPO in 2027 and 2028, and what is the rationale behind their respective adoption rates?

For NPO, the projected deployment is several tens of thousands of units in 2027, increasing to a couple of hundred thousand units in 2028, marking its first meaningful scale in AI fabrics. For CPO, volumes are expected to be around ten thousand units in 2027, growing to several tens of thousands of units in 2028 for limited, high-density deployments only. To provide a central estimate, NPO volumes are around sixty thousand in 2027 and a quarter of a million in 2028, while CPO volumes are approximately ten thousand in 2027 and seventy thousand in 2028. In terms of the relative mix of these next-generation optics within new AI deployments, NPO is expected to command a vast majority share of around eighty-five to ninety percent in 2027, with CPO taking the remaining minority slice. In 2028, the mix is projected to shift slightly to around three-quarters for NPO and roughly a quarter for CPO. NPO is expected to ramp faster due to easier thermal integration and better field replaceability and serviceability. CPO will ramp slower because switch replacement becomes more difficult when the integrated optics fail.

## 相关股票

<!-- AUTO:相关股票 START -->
- [[000660 KS]]
- [[005930 KS]]
- [[AMD US]]
- [[AVGO US]]
- [[BC94 LN]]
- [[COHR US]]
- [[LITE US]]
- [[META US]]
- [[MRVL US]]
- [[MU US]]
- [[NVDA US]]
- [[RMBS US]]
- [[TXN US]]
<!-- AUTO:相关股票 END -->
