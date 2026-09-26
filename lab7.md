###  Objectives

*   Configure PortFast to bypass STP listening/learning states on access ports
    
*   Implement BPDU Guard to protect against rogue switch connections
    
*   Recover a port from err-disabled state caused by BPDU Guard
    

### 🖧 Topology

SW1 with PC1 on f0/1, PC2 on f0/2, f0/3 reserved for rogue switch test; SW2 (rogue) to connect to SW1 f0/3 for BPDU Guard testing

### 📝 Tasks

1.  Configure f0/1 and f0/2 as access ports in VLAN 10
    
2.  Enable PortFast on f0/1 and f0/2 using interface-level commands
    
3.  Enable PortFast globally as default for all access ports
    
4.  Configure BPDU Guard on interface f0/3 and set it as access port in VLAN 10
    
5.  Connect PCs to f0/1 and f0/2 and observe immediate forwarding state
    
6.  Connect SW2 to f0/3 and observe BPDU Guard trigger err-disabled state
    
7.  Manually recover f0/3 from err-disabled state
