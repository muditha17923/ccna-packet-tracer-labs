### Objectives

*   Enable IPv6 routing and configure router interfaces with IPv6 addresses
    
*   Understand how SLAAC uses Router Advertisements to provide prefix information
    
*   Verify that end hosts automatically generate global unicast IPv6 addresses
    
*   Test IPv6 connectivity between auto-configured hosts
    

### 🖧 Topology

R1 -- SW1 -- PC1, PC2, PC3; R1 G0/0 connects to SW1 Fa0/1; PC1 on Fa0/2, PC2 on Fa0/3, PC3 on Fa0/4

### 📝 Tasks

1.  Enable IPv6 unicast routing on R1
    
2.  Configure R1 G0/0 with the IPv6 address 2001:DB8:ACAD:1::1/64 and enable the interface
    
3.  Verify that R1 is sending Router Advertisement messages on G0/0
    
4.  Configure all three PCs to obtain IPv6 addresses automatically (SLAAC/Auto Config)
    
5.  Wait for PCs to receive Router Advertisements and generate global unicast addresses
    
6.  Verify each PC has an address in the 2001:DB8:ACAD:1::/64 prefix
    
7.  Test IPv6 connectivity by pinging R1 and other PCs from PC1
