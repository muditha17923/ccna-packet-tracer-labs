### Objectives

*   Understand the purpose of first-hop redundancy protocols
    
*   Configure basic HSRP between two routers
    
*   Verify HSRP active and standby router roles
    
*   Test gateway failover functionality
    

### 🖧 Topology

R1 and R2 both connect to SW1 (access switch); R1 G0/0 to SW1 F0/1, R2 G0/0 to SW1 F0/2; PC1 and PC2 connect to SW1 F0/10 and F0/11; R1 and R2 uplinks to ISP-Cloud via G0/1 interfaces; LAN subnet 192.168.10.0/24, Virtual IP 192.168.10.1

### 📝 Tasks

1.  Cable the topology and assign IP addresses: R1 G0/0 = 192.168.10.2/24, R2 G0/0 = 192.168.10.3/24
    
2.  Configure PC1 and PC2 with IP addresses in the 192.168.10.0/24 subnet using 192.168.10.1 as their default gateway
    
3.  Configure HSRP group 10 on R1 G0/0 with virtual IP 192.168.10.1 and priority 110
    
4.  Configure HSRP group 10 on R2 G0/0 with virtual IP 192.168.10.1 (default priority 100)
    
5.  Verify HSRP status and confirm R1 is the active router
    
6.  Test failover by shutting down R1 G0/0 and verify R2 becomes active
