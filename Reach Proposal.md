# 基于IMS架构优化的三层MSN卫星网络研究方案

## 摘要

低轨卫星网络（LEO）正逐渐成为全球通信的重要组成部分。然而，现有的路由与管理框架仍存在集中化严重、边缘节点缺乏智能、安全性不足等问题。典型方案如 QTER (QoS-Aware 3-D Efficient and Reliable Routing) 在提升 QoS 的同时仍依赖高层卫星集中调度，导致可扩展性与安全性受限。本文提出一种 **借鉴IMS架构的三层MSN（Management Satellite Node）模型**，在低层引入 **边缘控制功能（Edge Control Function, ECF）**，中层负责区域调度，高层进行全局资源管理。该方案旨在实现分层QoS保障、边缘智能化与安全增强，从而突破现有框架的瓶颈。

## 研究背景

随着 Starlink、OneWeb 等大规模星座的部署，LEO 卫星网络的动态拓扑、频繁链路切换以及多业务需求对 QoS 和安全提出了新挑战[3]。现有的 QTER 框架通过高层 MSN 集中调度实现高可靠路由，但存在以下不足：

1. **集中管理瓶颈**：所有管理依赖高层 MSN，容易造成过载[1]；
    
2. **低层节点智能缺失**：低层仅作为转发节点，缺乏 QoS、认证与安全功能；
    
3. **QoS 单一化**：指标主要集中在可靠性，缺乏对带宽、公平性等维度的支持；
    
4. **容灾不足**：过度依赖高层 MSN 进行恢复，区域级自治能力有限。
    

与此同时，IMS (IP Multimedia Subsystem) 在地面核心网中已证明其分层控制与会话安全的有效性[4, 5] 。其核心思想是通过 **CSCF、SBC 等分层组件**，实现分布式控制、边缘接入安全与多维 QoS 保证。这为 LEO 卫星网络的优化提供了启发。

## 相关工作

- **QTER**：提出三维路由方法，增强可靠性，但集中化和边缘节点功能不足仍是瓶颈[1]。
    
- **优化路由模型**：如 OBRA/H-AB 算法，关注多约束优化与实时计算，但缺乏 IMS 风格的分层 QoS 与安全机制[3]。
    
- **LEOCraft 框架**：提供大规模星座设计与优化工具，强调拓扑与轨道优化，但未涉及安全与分层控制[2]。
    
- **IMS 安全与 SBC**：IMS 通过安全关联 (Security Associations) 和 SBC 防护，实现跨域安全、边缘认证与 QoS enforcement[4, 5, 6]。

## 研究方法

本文提出一种 **IMS-Inspired 三层 MSN 架构**：

1. **低层 P-MSN + ECF**：在边缘层实现用户认证、加密解密、QoS 检查、数据压缩和负载上报，相当于卫星网络的“智能边缘网关”；
    
2. **中层 M-MSN**：负责区域级 QoS 调度与局部容灾，减轻高层负担；
    
3. **高层 S-MSN**：进行跨区域全局调度与资源分配，保证系统弹性。
    

研究计划包括：

- **仿真对比**：基于 QTER 仿真平台扩展三层 MSN 架构，与原始 QTER 进行对比；
    
- **性能评估**：测试时延、吞吐量、丢包率、容灾恢复时间；
    
- **安全性验证**：借助 IMS 威胁建模方法（如 IMS-HAG）评估新架构的防御能力[6]。


## 预期贡献

1. **分层化的 MSN 管理模型**，有效缓解集中化瓶颈；
    
2. **低层边缘智能化（ECF）**，实现 QoS enforcement 与安全增强；
    
3. **多维度 QoS 保障**，覆盖接入、区域与全局；
    
4. **更高弹性与可扩展性**，适应大规模星座与多业务场景。


## 参考文献

[1] Y. Wu, et al., “QTER: QoS-Aware 3-D Efficient and Reliable Routing for LEO Satellite Networks,” _IEEE Trans. Commun._, 2023.
  
[2] S. Basak, A. Pal, and D. Bhattacherjee, “LEOCraft: Towards Designing Performant LEO Networks,” _USENIX ATC_, 2025.
  
[3] F. Y. S. Lin, S.-Y. Zhang, and C.-H. Hsiao, “Efficient Optimization-based Routing Strategies for Large-Scale Multi-Layer LEO Satellite Networks,” _IEEE ICCCN_, 2025.
  
[4] Alcatel-Lucent, “IMS Interconnect: Peering, Roaming and Security – Part Two,” White Paper, 2011.
  
[5] Metaswitch, “Session Border Control in IMS Networks,” White Paper, 2011.
  
[6] A. E. Shaikh and S. Y. Enoch, “Threat Specific Risk Assessment for IMS Based on Hierarchical Models,” _Whitecliffe College_, 2025.




