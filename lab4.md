### 🎯 Objectives

*   Enable Layer 3 routing on a multilayer switch
    
*   Configure SVIs (Switched Virtual Interfaces) for inter-VLAN routing
    
*   Understand the performance benefits of SVI routing over router-on-a-stick
    

### 🖧 Topology

MLS1 (3560 Layer 3 Switch): PC1 on Fa0/1 (VLAN 10), PC2 on Fa0/2 (VLAN 20), PC3 on Fa0/3 (VLAN 30), Server1 on Fa0/10 (VLAN 100)

### 📝 Tasks

1.  Create VLANs on MLS1: VLAN 10 (Accounting), VLAN 20 (IT), VLAN 30 (HR), VLAN 100 (Servers)
    
2.  Configure Fa0/1 as access port for VLAN 10, Fa0/2 for VLAN 20, Fa0/3 for VLAN 30, Fa0/10 for VLAN 100
    
3.  Enable IP routing on the Layer 3 switch using the 'ip routing' command
    
4.  Create and configure SVI for VLAN 10 with IP 10.10.10.1/24
    
5.  Create SVIs for VLANs 20, 30, and 100 with IPs 10.10.20.1/24, 10.10.30.1/24, and 10.10.100.1/24
    
6.  Ensure all SVIs are administratively enabled
    
7.  Configure all PCs and Server1 with appropriate IPs and default gateways pointing to their SVI
