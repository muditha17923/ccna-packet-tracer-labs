### Objectives

*   Understand standard ACL syntax and wildcard masks
    
*   Create a standard numbered ACL (1-99 range)
    
*   Apply a standard ACL to a router interface in the correct direction
    
*   Verify ACL operation using show commands and connectivity tests
    

### 🖧 Topology

R1 -- SW1 -- PC1 (192.168.1.10), PC2 (192.168.1.20); R1 G0/0 (192.168.1.1) to SW1 Fa0/1; R1 G0/1 (10.0.0.1) to Server1 (10.0.0.100)

### 📝 Tasks

1.  Configure IP addressing on R1 G0/0 (192.168.1.1/24) and G0/1 (10.0.0.1/24), enable both interfaces
    
2.  Configure PC1 with IP 192.168.1.10/24 and default gateway 192.168.1.1
    
3.  Configure PC2 with IP 192.168.1.20/24 and default gateway 192.168.1.1
    
4.  Configure Server1 with IP 10.0.0.100/24 and default gateway 10.0.0.1
    
5.  Verify baseline connectivity: both PCs should successfully ping Server1
    
6.  Create standard ACL 10 to deny traffic from PC1 (192.168.1.10) and permit all other traffic
    
7.  Apply ACL 10 inbound on R1 G0/0 interface
    
8.  Test and document: PC1 pings to Server1 should fail; PC2 pings should succeed
