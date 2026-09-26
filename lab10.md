### 🎯 Objectives

*   Implement Rapid PVST+ for sub-second convergence across VLANs
    
*   Design hierarchical STP topology with deterministic root placement
    
*   Deploy EtherChannel for increased bandwidth and redundancy between distribution switches
    
*   Secure the STP domain using PortFast, BPDU Guard, and Root Guard
    

### 🖧 Topology

Core/Dist Layer: SW1 (primary core), SW2 (secondary core); Access: SW3, SW4; SW1 g0/1-2 to SW2 g0/1-2 (LACP Po1); SW1 g0/3 to SW3 f0/1; SW2 g0/3 to SW3 f0/2; SW1 g0/4 to SW4 f0/1; SW2 g0/4 to SW4 f0/2; PC1 on SW3 f0/10; PC2 on SW4 f0/10; VLANs 10, 20, 99

### 📝 Tasks

1.  Create VLANs 10 (Users), 20 (Servers), 99 (Mgmt) on all four switches
    
2.  Enable Rapid PVST+ mode on all switches for faster convergence
    
3.  Configure LACP EtherChannel Po1 between SW1-SW2 using active mode on both sides
    
4.  Configure all inter-switch links as trunks allowing only VLANs 10, 20, 99 with native VLAN 99
    
5.  Set SW1 as root primary for VLANs 10, 20, 99 and SW2 as secondary root for all VLANs
    
6.  Configure Root Guard on SW3 and SW4 uplink ports facing SW1 and SW2
    
7.  Configure access ports f0/10 on SW3 and SW4 in VLAN 10 with PortFast and BPDU Guard
    
8.  Test failover by shutting down SW1 and verify SW2 becomes root
