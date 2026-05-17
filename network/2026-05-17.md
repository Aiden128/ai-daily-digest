---
title: "Network Daily Digest - 2026-05-17"
date: 2026-05-17
permalink: /network/2026-05-17
---

# Network Daily Digest - 2026-05-17

## Headlines

- **OpenAI、Microsoft 與產業夥伴聯合發表 MRC 協定：讓 Ethernet 擴展到百萬節點等級**（May 12）— [The Next Platform](https://www.nextplatform.com/connect/2026/05/12/openai-microsoft-and-friends-build-a-better-more-scalable-ethernet/5239078) / [arXiv:2605.04333](https://arxiv.org/abs/2605.04333)
  - 這項名為 Multipath Reliable Connection（MRC）的新協定，由 OpenAI、Microsoft、Broadcom、AMD 與 NVIDIA 共同推動。核心思路並非繼續追求單一埠更高的頻寬，而是將同一顆交換器 ASIC 的總頻寬拆分成更多條較低速的連結，藉此打造「更高基數（higher radix）」且更扁平的網路拓撲。
  - 舉例來說，若將 51.2 Tb/sec 的交換器 ASIC 從 64 埠 800Gb/sec 改為 512 埠 100Gb/sec，並搭配八個獨立的 Clos 資料平面，就能在僅兩層網路中連接 131,072 個運算節點，且任何兩點之間最多只需三跳（three hops）。相較之下，傳統三層 RoCE 網路連接 65,536 個節點需要五到七跳。
  - MRC 採用靜態 IPv6 Segment Routing（SRv6）搭配自適應封包噴灑（adaptive packet spraying）與 ECN 擁塞控制，支援無序傳遞、選擇性重傳與封包修剪（packet trimming）。當八條連結中任一條故障時，網路可自動繞行修復，AI 訓練工作無需中斷。目前已在 Oracle Stargate 與 Microsoft Azure AI 資料中心實際部署。

- **Arista 預告 2027 年進軍 AI Scale-Up 網路市場：ESUN 與 1.6Tb/sec 交換器**（May 7）— [The Next Platform](https://www.nextplatform.com/connect/2026/05/07/arista-rides-ai-scale-out-networks-moves-into-scale-across-and-awaits-scale-up/5235293)
  - Arista 執行長 Jayshree Ullal 在財報會議中明確表示，公司正從「Scale-Out」橫向擴展網路延伸至「Scale-Across」跨資料中心網路，並預計 2027 年進入「Scale-Up」機架內高速互連市場。
  - Arista 預計 2026 全年營收達 115 億美元，其中 AI 相關網路營收從 32.5 億美元上調至 35 億美元。目前已有超過一百家客戶部署 800Gb/sec Ethernet，並預計 2027 年推出 1.6Tb/sec 產品。
  - 所謂 ESUN（Ethernet for Scale-Up Networking）規格，目標是透過共封裝銅纜（CPC）或共封裝光學（CPO）技術，在機架內提供極低延遲的運算與記憶體加速互連。

- **Google 揭露 TPU 8 世代與 Virgo Scale-Out Ethernet Fabric**（Apr 28）— [The Next Platform](https://www.nextplatform.com/connect/2026/04/28/new-google-networks-tuned-up-for-genai-inference-and-training/5218978)
  - Google 在 TPU 8 發表中同步揭露了兩項新網路技術：針對訓練的「Sunfish」3D Torus 拓撲（可擴展至 9,600 顆 TPU），以及針對推理的「Zebrafish」Boardfly 拓撲（可連接 1,152 顆 TPU 8i，延遲從 16 跳降至 7 跳）。
  - 同時亮相的 Virgo 是 Google 全新設計的資料中心級 Scale-Out Ethernet Fabric，用於連接包含 TPU Pod 在內的各類機架。Google 自 2016 年起即採用自研的 Snap NOS 與 Pony Express 資料平面引擎，後續又發展了 Aquila 低延遲協定與 Falcon 傳輸層（用於 Mount Evans DPU）。

## Vendor Updates

- **NVIDIA**：新聞室提及 Spectrum-X 為「開放式 AI-Native Ethernet Fabric」，並設定 Gigascale AI 標準。該平臺整合 NVIDIA BlueField-3 DPU 與 Spectrum-4 交換器，提供 RoCE 擴展與 AI 流量最佳化。（May 2026）— [NVIDIA Newsroom](https://nvidianews.nvidia.com/)

- **Cisco**：發布「5 signs your data center is holding your AI strategy back」，指出 AI 基礎設施最常見的瓶頸並非 GPU 本身，而是網路骨幹無法以 GPU 所需的速度搬運資料，導致昂貴的加速器閒置。文章強調「當安全內建於網路骨幹本身，就能在不減速的情況下保護 AI 工作負載」。（Apr 28）— [Cisco Blog](https://blogs.cisco.com/datacenter/5-signs-your-data-center-is-holding-your-ai-strategy-back)

- **Arista**：2026 Q1 產品營收達 23.1 億美元（年增 36.6%），服務營收 3.98 億美元（年增 27.3%）。AI 網路業務持續擴張，預期 Scale-Across 跨資料中心網路將佔 AI 營收的三分之一至三分之二。（May 7）— [The Next Platform](https://www.nextplatform.com/connect/2026/05/07/arista-rides-ai-scale-out-networks-moves-into-scale-across-and-awaits-scale-up/5235293)

- **AMD**：Pensando 產品頁面目前顯示 404，無法取得最新 DPU 產品線資訊。該來源當前無法連線。

- **Intel**：Intel IPU（Infrastructure Processing Unit）產品線頁面正常運作，強調從邊緣到雲端的網路連接能力，但近期未見重大產品更新公告。（May 2026）— [Intel Network](https://www.intel.com/content/www/us/en/products/network-io.html)

## SmartNIC & DPU Focus

- **MRC 協定已實作於多款 SmartNIC/DPU**：根據 The Next Platform 報導，MRC 目前已部署於 NVIDIA ConnectX-8 SmartNIC、AMD "Pollara" 與 "Vulcano" DPU，以及 Broadcom Thor Ultra SmartNIC。SRv6 靜態路由則運行於 NVIDIA Spectrum 4/5（搭配 Cumulus Linux 或 SONiC）以及 Arista EOS（基於 Broadcom Tomahawk 5 ASIC）之上。（May 12）

- **Communication Offloading on SmartNIC DPUs: A Quantitative Approach**（arXiv:2605.04842, May 6）：這篇論文以量化方法評估 SmartNIC DPU 在支援非同步通訊卸載上的可行性。研究顯示，將通訊任務卸載至可程式化核心可節省高端 CPU 資源，但效能增益高度依賴封包大小與卸載策略的選擇。

- **Blink: CPU-Free LLM Inference by Delegating the Serving Stack to GPU and SmartNIC**（arXiv:2604.07609, Apr 8）：提出將 LLM 推理的服務堆疊（orchestration 與 token-level 控制）完全卸載至 GPU 與 SmartNIC，讓主機 CPU 退出關鍵路徑。實驗顯示此架構可顯著降低端到端延遲並提升吞吐量。

- **SCENIC: Stream Computation-Enhanced SmartNIC**（arXiv:2604.15128, Apr 16）：現有商業 SmartNIC 雖提供高頻寬與易用的軟體整合，但可程式化能力有限。SCENIC 提出一種串流計算增強型 SmartNIC 架構，試圖在效能與彈性之間取得更好平衡。

## Ultra Ethernet Consortium & Standards

- **UEC 規格 1.0.2 已開放下載**：Ultra Ethernet Consortium 目前提供 1.0.2 版規格書與發布說明（PDF），並附有 1.0 規格白皮書與解說影片。UEC 的目標是讓 Ethernet 達到超級電腦互連的效能，同時維持 Ethernet 的普遍性與成本效益。（Jan 2026）— [UEC 官網](https://ultraethernet.org/)

- **MRC 與 UEC 的關係**：MRC 被定位為 UEC 規格精神的「務實延伸」，而非從白紙開始的全新協定。MRC 直接建構在現有 RoCE 之上，加入多路徑、自適應負載平衡、封包修剪等機制，並使用標準 Ethernet 交換器 ASIC 即可實作，無需等待全新硬體世代。

- **UEC 成員動態**：Broadcom 於 2025 年 10 月發表 Thor Ultra 800G AI Ethernet NIC，並宣稱完全符合 UEC 規格。UEC 持續推動合規性與互通性計畫，但目前尚未公布新的 plugfest 時程。

## Conference & Research Papers

以下為近兩週內與高效能網路、RDMA、SmartNIC 及資料中心網路相關的研究論文，依發表日期排序：

1. **Avoiding Cross-Datacenter Collective Congestion via Disaggregated Buffering**（arXiv:2605.11852, May 12）
   - **白話摘要**：當 LLM 訓練擴展到數萬顆 GPU 並橫跨多個資料中心時，跨資料中心的集合通訊（collectives）會與資料中心內流量產生碰撞，造成嚴重擁塞。
   - **核心價值**：提出「解耦式緩衝（disaggregated buffering）」架構，將緩衝區從交換器晶片移至獨立的記憶體節點，讓擁塞控制能跨資料中心統一調度。
   - **實務價值**：對於正在建設「地理分散式 AI 叢集」的雲端業者，這提供了一個減少尾部延遲（tail latency）的新方向。

2. **On the Verification Problem of Remote Direct Memory Access programs**（arXiv:2605.10631, May 11）
   - **白話摘要**：RDMA 程式允許繞過作業系統直接存取遠端記憶體，但這也帶來了驗證上的挑戰——傳統的網路協定驗證工具難以處理 RDMA 的非同步語意。
   - **核心價值**：提出一套針對 RDMA 程式的形式化驗證框架，能自動偵測記憶體一致性與死鎖問題。
   - **實務價值**：對於使用 RDMA 建構分散式系統的工程師，這意味著未來可能有工具能在部署前自動抓出難以重現的並行臭蟲。

3. **From Detection to Recovery: Operational Analysis on LLM Pre-training with 504 GPUs**（arXiv:2605.09370, May 10）
   - **白話摘要**：大型 AI 訓練本質上已是分散式系統問題，硬體故障已成為「日常運作條件」而非罕見例外。本文基於 504 GPU 的真實叢集運營資料進行分析。
   - **核心價值**：系統性地量化故障從偵測到恢復的時間線，發現網路連結故障佔整體訓練中斷的顯著比例。
   - **實務價值**：強化了「網路必須具備自愈能力」的論點，與 MRC 的多路徑故障修復設計不謀而合。

4. **Resilient AI Supercomputer Networking using MRC and SRv6**（arXiv:2605.04333, May 5）
   - **白話摘要**：在超大規模同步預訓練中，尾部延遲主導整體效能。本文提出三管齊下的方法：新的 RDMA 傳輸協定 MRC、IPv6 Segment Routing 靜態路由、以及積極的負載平衡。
   - **核心價值**：MRC 透過「噴灑」流量至多條路徑並主動負載平衡，結合封包修剪與選擇性重傳，大幅降低擁塞造成的延遲飆升。
   - **實務價值**：這篇論文已轉化為 OCP 規格與多家廠商的硬體實作，是近期從學術研究走向產業標準最快的網路技術之一。

5. **A Protocol-Independent Transport Architecture**（arXiv:2605.02210, May 4）
   - **白話摘要**：現代網路傳輸層越來越常實作於 NIC 硬體中，但這也使得部署新傳輸協定變得困難。
   - **核心價值**：提出一個與協定無關的傳輸架構，讓同一個 NIC 硬體能夠靈活支援多種傳輸協定（包括未來的新協定），而無需更換硬體。
   - **實務價值**：對於資料中心營運商而言，這意味著硬體投資可以更具前瞻性，降低被單一協定綁定的風險。

6. **Eliminating Hidden Serialization in Multi-Node Megakernel Communication**（arXiv:2605.00686, May 1）
   - **白話摘要**：MoE 推理的「Megakernel」設計將專家計算與細粒度 GPU 發起通訊融合為單一常駐核心，但在多節點擴展時暗藏序列化瓶頸。
   - **核心價值**：發現並消除了跨節點通訊中隱藏的序列化點，讓多節點 MoE 推理能真正達到單節點般的重疊計算與通訊效率。
   - **實務價值**：對於部署大型 MoE 模型（如 GPT-4、DeepSeek-V3 等級）的推理服務商，這直接關係到叢集擴展時的線性加速比。

## Hot GitHub Projects

- **linux-rdma/rdma-core v63.0**（May 6）：RDMA 核心用戶空間函式庫的最新穩定版本，包含多項 bug 修復與新硬體支援。對於使用 RoCEv2 或 InfiniBand 的系統管理員，這是維持驅動程式與核心版本相容性的關鍵元件。[GitHub](https://github.com/linux-rdma/rdma-core/releases/tag/v63.0)

- **openucx/ucx v1.20.1**（May 7）：UCX 是高效能通訊框架，廣泛用於 HPC 與 AI 叢集（如 OpenMPI、NCCL 的底層傳輸）。此修補版本修正了多個與記憶體註冊和 RDMA 連線管理相關的穩定性問題。[GitHub](https://github.com/openucx/ucx/releases/tag/v1.20.1)

- **p4lang/p4c v1.2.5.13**（May 7）：P4 編譯器的最新版本。P4 是可程式化交換器與 SmartNIC 的關鍵語言，此更新持續擴展對 Tofino、Tofino2 與 eBPF 後端的支援。[GitHub](https://github.com/p4lang/p4c/releases/tag/v1.2.5.13)

- **fpgasystems/SCENIC**（近期熱門）：SCENIC（Stream Computation-Enhanced SmartNIC）的開源實作，嘗試在 FPGA-based SmartNIC 上實現高效能串流計算。雖然目前僅 10 顆星，但它是少數同時發表頂會論文並開源硬體程式碼的 SmartNIC 研究專案。[GitHub](https://github.com/fpgasystems/SCENIC)

## Community Discussions

- **Hacker News**：近期未見高熱度的資料中心網路專題討論。最相關的話題多集中在 AI 模型與開發工具，網路基礎設施並非本週 HN 的焦點。

- **Reddit r/networking**：近期討論以企業無線存取點選型與 Cisco VXLAN Fabric 的 IPv6 Prefix Delegation 設定為主，未見大規模資料中心網路或 RDMA 相關的深層技術討論。

- **Reddit r/sysadmin**：Windows Server 2016 Storage Spaces Direct（S2D）的降級與修復問題獲得少量關注，但與高效能網路無直接關聯。

## Deep Analysis

本週網路產業最重大的事件，無疑是 OpenAI、Microsoft 與一線晶片廠聯手推出的 MRC（Multipath Reliable Connection）協定。這不僅是一篇學術論文，更是一套已經在 Oracle Stargate 與 Microsoft Azure AI 資料中心實際運作的生產系統。MRC 的設計哲學值得深入探討：它並未試圖發明全新的 Ethernet，而是「重新配置」現有的 51.2 Tb/sec 交換器 ASIC，將其頻寬從「少數高速埠」轉化為「大量中速連結」，進而實現更扁平、更具韌性的拓撲。

這種設計反映出 AI 叢集網路面臨的兩難：一方面，單埠頻寬從 100G 推進到 800G 甚至 1.6T，但交換器數量與跳數（hop count）卻讓尾部延遲成為瓶頸；另一方面，增加連結數量會提高故障機率，但 MRC 證明了「只要有足夠多的路徑與正確的協定，網路就能繞過故障連結自愈」。這與傳統電信網路的「冗餘設計」概念相通，但 MRC 將其帶入 RDMA/Ethernet 的語境，並與封包修剪、選擇性重傳等機制結合。

與此同時，Arista 的財報透露了另一個產業趨勢：「Scale-Up」機架內互連將在 2027 年成為新的戰場。過去 Arista 專注於 Scale-Out（機架間的 leaf/spine 網路），但隨著 ESUN（Ethernet for Scale-Up Networking）規格的浮現，Ethernet 正試圖入侵過去由 NVLink 與 InfiniBand 主導的機架內高速互連領域。若 ESUN 成功，意味著資料中心將能用單一 Ethernet 技術棧同時服務機架內（Scale-Up）、機架間（Scale-Out）與跨資料中心（Scale-Across）三種場景，這對簡化營運與降低成本具有重大意義。

Google 的 TPU 8 與 Virgo Fabric 則展示了第三條路徑：完全客製化。Google 同時擁有 Aquila（InfiniBand 等級低延遲）、Falcon（DPU 傳輸層）、Snap（自研 NOS）與現在的 Virgo（Scale-Out Ethernet），並根據訓練（Torus）與推理（Boardfly/Dragonfly）的不同需求選擇最適合的拓撲。這種「為工作負載量身打造網路」的能力，是超大規模業者相對於一般企業的結構性優勢。

綜觀三者，2026 年的資料中心網路正處於「收斂與分化並存」的關鍵時刻：MRC 與 UEC 推動開放標準的收斂，讓 Ethernet 有機會統一 AI 叢集的網路層；但 Google 的客製化路線又證明了，在極致效能的競賽中，專用設計仍有其不可替代的地位。對於多數企業與雲端業者而言，MRC 與 ESUN 所代表的「開放、可擴展、可自愈」的 Ethernet 生態，將是未來三到五年最具實務價值的投資方向。
