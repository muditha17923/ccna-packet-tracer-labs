### Objectives

*   Configure single-area OSPFv2 on multiple routers
    
*   Manually set OSPF router-IDs
    
*   Configure passive interfaces to prevent unnecessary OSPF traffic on LAN segments
    

### 🖧 Topology

R1 -- R2 -- R3 in a linear topology; R1 G0/0 (10.0.12.1/24) connects to R2 G0/0 (10.0.12.2/24); R2 G0/1 (10.0.23.2/24) connects to R3 G0/0 (10.0.23.3/24); R1 G0/1 (192.168.1.1/24) to SW1 with PC1; R3 G0/1 (192.168.3.1/24) to SW2 with PC2

### 📝 Tasks

1.  Cable the topology and assign IP addresses to all router interfaces as specified
    
2.  Enable OSPF process ID 1 on all three routers and advertise all connected networks into Area 0
    
3.  Configure a manual router-ID on each router: R1=1.1.1.1, R2=2.2.2.2, R3=3.3.3.3
    
4.  Configure passive interfaces on R1 G0/1 and R3 G0/1 to prevent OSPF hello packets on LAN segments
    
5.  Verify OSPF neighbor adjacencies form between R1-R2 and R2-R3
    
6.  Test end-to-end connectivity by pinging from PC1 to PC2
