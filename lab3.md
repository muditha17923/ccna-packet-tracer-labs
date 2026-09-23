### 🎯 Objectives

*   Configure router subinterfaces for inter-VLAN routing
    
*   Apply 802.1Q encapsulation on router subinterfaces
    
*   Configure a trunk link between switch and router
    
*   Enable communication between hosts in different VLANs
    

### 🖧 Topology

R1 (G0/0) ----- trunk ----- (Fa0/1) SW1; SW1: PC1 on Fa0/10 (VLAN 10), PC2 on Fa0/20 (VLAN 20), PC3 on Fa0/30 (VLAN 30)

### 📝 Tasks

1.  Create VLAN 10 (Sales), VLAN 20 (Engineering), and VLAN 30 (Management) on SW1
    
2.  Configure Fa0/10 as access port for VLAN 10, Fa0/20 for VLAN 20, Fa0/30 for VLAN 30
    
3.  Configure Fa0/1 on SW1 as a trunk port to connect to the router
    
4.  On R1, enable interface G0/0 and create subinterface G0/0.10 with 802.1Q encapsulation for VLAN 10
    
5.  Create subinterfaces G0/0.20 and G0/0.30 with appropriate encapsulation for VLANs 20 and 30
    
6.  Assign IPs: G0/0.10=192.168.10.1/24, G0/0.20=192.168.20.1/24, G0/0.30=192.168.30.1/24
    
7.  Configure PCs with IPs in their respective subnets and set default gateways to the router subinterfaces
    
8.  Test inter-VLAN routing by pinging between all PCs
