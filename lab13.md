### Objectives

*   Configure a Cisco router as a DHCP server
    
*   Create DHCP pools with network options including default gateway and DNS
    
*   Exclude specific IP addresses from the DHCP pool
    
*   Verify DHCP operation using show commands
    

### 🖧 Topology

R1 (G0/0: 192.168.10.1/24) -- SW1 (Fa0/1) -- PC1 (Fa0/2), PC2 (Fa0/3), PC3 (Fa0/4); SW1 is a Layer 2 switch

### 📝 Tasks

1.  Configure R1's G0/0 interface with IP address 192.168.10.1/24 and enable it
    
2.  Exclude addresses 192.168.10.1 through 192.168.10.10 from DHCP allocation
    
3.  Create a DHCP pool named LAN\_POOL for network 192.168.10.0/24
    
4.  Configure the default gateway as 192.168.10.1 in the pool
    
5.  Configure DNS server as 8.8.8.8 and domain name as ccnalab.local
    
6.  Set the DHCP lease time to 2 days
    
7.  Configure all three PCs to obtain IP addresses automatically
    
8.  Verify DHCP bindings and test connectivity by pinging between PCs
