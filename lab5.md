### 🎯 Objectives

*   Design and implement a hierarchical multi-switch VLAN topology
    
*   Configure trunk links with allowed VLAN restrictions for traffic optimization
    
*   Implement inter-VLAN routing using SVIs on a distribution layer switch
    
*   Troubleshoot and verify complex VLAN and trunking configurations
    

### 🖧 Topology

DSW1 (L3 Distribution Switch) connects to: ASW1 via Gi0/1-Fa0/24 trunk, ASW2 via Gi0/2-Fa0/24 trunk; ASW1 (Access Switch): PC1 on Fa0/1 (VLAN 10), PC2 on Fa0/2 (VLAN 20); ASW2 (Access Switch): PC3 on Fa0/1 (VLAN 20), PC4 on Fa0/2 (VLAN 30); All trunk native VLAN = 999

### 📝 Tasks

1.  Create VLANs 10 (Finance), 20 (Marketing), 30 (Operations), and 999 (Native) on all three switches
    
2.  On ASW1, configure Fa0/1 as access VLAN 10 and Fa0/2 as access VLAN 20
    
3.  On ASW2, configure Fa0/1 as access VLAN 20 and Fa0/2 as access VLAN 30
    
4.  Configure trunk on ASW1 Fa0/24 allowing only VLANs 10, 20, and 999 with native VLAN 999
    
5.  Configure trunk on ASW2 Fa0/24 allowing only VLANs 20, 30, and 999 with native VLAN 999
    
6.  On DSW1, configure Gi0/1 and Gi0/2 as trunks with matching VLAN restrictions and native VLAN 999
    
7.  Enable IP routing on DSW1 and create SVIs: VLAN10=172.16.10.1/24, VLAN20=172.16.20.1/24, VLAN30=172.16.30.1/24
    
8.  Assign IPs to PCs in their respective subnets with DSW1 SVIs as gateways and verify full connectivity
