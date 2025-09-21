# incs615_term_project

## 1. Introduction (1.5页)

- **背景**
    
    - LEO 卫星网络的重要性（Starlink、OneWeb，6G 应用）。
        
    - QoS 与安全挑战：动态拓扑、频繁切换、DoS 风险。
        
- **现有研究**
    
    - QTER：提升 QoS，但集中化严重、边缘节点缺乏安全。
        
    - IMS：分层控制（CSCF）+ 边缘保护（SBC/BCF），但复杂、SBC 黑盒、BGF 不适合动态环境。
        
- **研究空白**
    
    - IMS 边缘设备最易受 DoS，需要 SBC/BCF 保护；同理，QTER 的低层卫星也不安全。
        
- **研究动机**
    
    - 借鉴 IMS 思想，在 QTER 边缘引入 **ECF (Edge Control Function)**，作为卫星版的 SBC/BCF。
        
- **贡献**
    
    1. 提出 IMS-Inspired 三层 MSN + ECF 架构；
        
    2. 强化边缘安全，解决 QTER 的不足；
        
    3. 设计仿真方案，比较性能与安全性。
        

---

## 2. Methods (2页)

- **三层 MSN 架构**
    
    - **P-MSN (低层)**：加入 ECF，执行认证、加密、QoS 检查、DoS 防御。
        
    - **M-MSN (中层)**：类似改进型 BGF，负责区域 QoS 和容灾。
        
    - **S-MSN (高层)**：全局调度和跨区域资源分配。
        
- **ECF 设计**
    
    - 借鉴 IMS 的 **SBC**：保护边缘、防止 DoS、拓扑隐藏。
        
    - 借鉴 IMS 的 **BGF**：策略执行、QoS 管控。
        
    - 在卫星边缘分布式部署，降低集中开销。
        
- **实验与评估方案**
    
    - 仿真环境：扩展 QTER/LEOCraft；
        
    - 对比方案：QTER、OBRA/H-AB、IMS-Inspired MSN；
        
    - 指标：时延、吞吐量、丢包率、QoS 满足率、安全防御能力。
        

---

## 3. Results (1.5)

- **性能改进**：IMS-Inspired MSN 在高负载下延迟更低，QoS 更稳定。
    
- **安全增强**：ECF 在边缘完成认证与加密，降低 DoS 风险。
    
- **可扩展性**：分布式 ECF 与区域级 BGF 改进，能适应上万颗卫星规模。
    
- 用表格/图示对比 QTER 与 IMS-Inspired MSN 的性能指标。
    

---

## 4. Discussion (0.5页)

- **优势**
    
    - 解决 QTER 的集中瓶颈；
        
    - 将 IMS 的 SBC/BCF 思路移植到卫星网络；
        
    - QoS 管理从单一可靠性扩展为多维度。
        
- **不足**
    
    - 边缘卫星算力有限，ECF 带来计算/能耗压力；
        
    - 三层架构增加通信协调成本；
        
    - IMS 的复杂性仍需简化。
        
- **未来工作**
    
    - 结合 SDN/NFV，进一步解耦功能；
        
    - 引入 AI/DRL 做智能路由；
        
    - 应用 IMS-HAG 威胁建模扩展到 LEO 安全分析。
        

---

## 5. Conclusion (0.5页)

- 提出 IMS-Inspired 三层 MSN + ECF，解决 QTER 集中化和边缘不安全问题；
    
- 借鉴 IMS 的 SBC/BCF 思想，提升 LEO 网络的安全性与 QoS；
    
- 为大规模卫星网络提供可扩展的安全架构。

---

## 6. References (1页)

