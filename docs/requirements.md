# Project Requirements - SD-WAN Multi-Branch Enterprise Simulation

**Project Goal**  
Build a realistic multi-branch SD-WAN network in Cisco Packet Tracer that demonstrates hybrid WAN (MPLS + Broadband), application-aware routing, QoS for VoIP, DIA breakout, and fast failover — directly mapped to CompTIA Network+ (N10-009) objectives.

**Company Context (Simulated)**  
- Company Name: GLOBE-NET Enterprises  
- HQ: Raipur (Chhattisgarh) — 100 users  
- Branch 1: Mumbai — 50 users  
- Branch 2: Delhi — 50 users  
- Business Type: Mid-size enterprise with VoIP calling, cloud apps (Office 365 / Google Workspace), ERP, and general internet usage  
- Challenge: High MPLS costs, latency-sensitive VoIP calls, increasing cloud usage, need for cost optimization without losing reliability

## N10-009 Objectives Mapping

| Objective | Description | How this project addresses it |
|----------|-------------|-------------------------------|
| 2.3      | WAN implementations and technologies | Hybrid underlay (MPLS + broadband), SD-WAN concepts (transport agnostic, application aware routing) |
| 3.4      | QoS concepts and operations | Traffic marking, classification, prioritization (VoIP in LLQ), congestion management |
| 1.5      | Routing protocols | Overlay routing simulation (BGP / EIGRP over tunnels), route preference & failover |
| 1.8      | Modern network environments | SD-WAN principles (central policy, application-aware, zero-touch concepts) |

## Business Requirements

- **Cost Optimization**  
  - Reduce dependency on expensive MPLS circuits  
  - Use hybrid model: MPLS for critical traffic + broadband/Internet for general & cloud traffic (DIA — Direct Internet Access)  
  - Target: 30–50% WAN cost reduction (real-world SD-WAN benchmarks show 30–84% savings vs full MPLS)

- **Application Performance**  
  - Prioritize VoIP traffic (target MOS score > 4.0)  
  - Low latency & jitter for voice (<150 ms latency, <30 ms jitter, <1% loss)  
  - Fast access to cloud applications (Office 365, Zoom, etc.) via local breakout (DIA)

- **High Availability & Failover**  
  - Automatic failover between MPLS and broadband  
  - Target convergence time: <5 seconds (realistic in PT: 5–10 seconds with IP SLA + tracking)

- **Data Sovereignty / Compliance (Simulated)**  
  - Allow local Internet breakout at branches for non-sensitive traffic  
  - Keep critical/internal traffic (ERP, file servers) going through HQ

- **User Scale**  
  - HQ: ~100 concurrent users  
  - Each branch: ~50 concurrent users  
  - Support VoIP phones, PCs, printers, and basic servers

## Technical Constraints (Packet Tracer Limitations)

- No native Cisco Catalyst SD-WAN (vEdge, vSmart, vBond, OMP) available  
- Simulate SD-WAN using:  
  - ISR routers (4331 / 2911 / 1941)  
  - IPsec/GRE tunnels for overlay  
  - BGP or EIGRP for routing  
  - Policy-Based Routing (PBR) for DIA breakout  
  - Modular QoS CLI (MQC) for VoIP prioritization  
  - IP SLA + tracking for failover

- Maximum realistic scale: 3 sites (HQ + 2 branches)  
- No real-time vManage — document policies manually via configs

## Success Criteria (Validation Goals)

- Branch users can reach HQ servers via primary (MPLS) path  
- VoIP traffic gets priority during congestion (test with iperf or multiple flows)  
- Internet traffic (YouTube / cloud) breaks out locally at branch (DIA simulation)  
- When MPLS link fails → traffic automatically shifts to broadband  
- Ping/trace shows failover <10 seconds (target <5 sec)  
- Basic security (ACLs + IPsec) blocks unauthorized access

## Next Phases Preview

- Phase 2 → Network diagrams (topology, logical, data flow, QoS marking)  
- Phase 3 → Packet Tracer build + configs  
- Phase 4 → Testing & failover demo  
- Phase 5 → Video + documentation for portfolio

**Prepared by:** Kamlesh  
**Date:** February 2026  
**Status:** Phase 1 Complete