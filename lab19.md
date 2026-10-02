###  Objectives

*   Understand the EUI-64 process of deriving interface ID from MAC address
    
*   Configure IPv6 addresses using the EUI-64 option on router interfaces
    
*   Manually verify EUI-64 address calculation (insert FFFE, flip 7th bit)
    
*   Establish IPv6 routing between multiple segments using EUI-64 addresses
    

### 🖧 Topology

R1 -- R2 -- R3 (linear); R1 G0/0 -- SW1 -- PC1; R2 connects R1 and R3; R3 G0/0 -- SW2 -- PC2; R1 G0/1 to R2 G0/0; R2 G0/1 to R3 G0/1

### 📝 Tasks

1.  Enable IPv6 unicast routing on R1, R2, and R3
    
2.  On R1 G0/0, configure IPv6 using prefix 2001:DB8:A:1::/64 with EUI-64
    
3.  On R1 G0/1, configure IPv6 using prefix 2001:DB8:A:12::/64 with EUI-64
    
4.  On R2 G0/0 and G0/1, configure IPv6 using prefixes 2001:DB8:A:12::/64 and 2001:DB8:A:23::/64 with EUI-64
    
5.  On R3 G0/1, configure 2001:DB8:A:23::/64 with EUI-64; on G0/0 configure 2001:DB8:A:3::/64 with EUI-64
    
6.  Use 'show ipv6 interface brief' to document the actual EUI-64 generated addresses
    
7.  Configure IPv6 static routes on all routers to enable end-to-end reachability
    
8.  Verify connectivity by pinging from PC1 to PC2 using IPv6
