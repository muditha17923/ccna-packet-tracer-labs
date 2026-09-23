### 🎯 Objectives

*   Configure 802.1Q trunk links between two switches
    
*   Understand how VLANs span across multiple switches via trunks
    
*   Configure and verify native VLAN settings on trunk ports
    

### 🖧 Topology

SW1 (Fa0/24) ----- trunk ----- (Fa0/24) SW2; SW1: PC1 on Fa0/1 (VLAN 10), PC2 on Fa0/2 (VLAN 20); SW2: PC3 on Fa0/1 (VLAN 10), PC4 on Fa0/2 (VLAN 20)

### 📝 Tasks

1.  Create VLAN 10 (Sales) and VLAN 20 (HR) on SW1
    
2.  Create VLAN 10 (Sales) and VLAN 20 (HR) on SW2
    
3.  Configure Fa0/1 as access port in VLAN 10 and Fa0/2 as access port in VLAN 20 on both switches
    
4.  Configure Fa0/24 on SW1 as an 802.1Q trunk port
    
5.  Configure Fa0/24 on SW2 as an 802.1Q trunk port
    
6.  Change the native VLAN to 99 on both trunk ports
    
7.  Assign IPs: PC1=10.10.10.1/24, PC3=10.10.10.3/24, PC2=10.10.20.2/24, PC4=10.10.20.4/24
