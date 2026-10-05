### Objectives

*   Understand OSPF DR/BDR election on multi-access networks
    
*   Manipulate DR/BDR election using OSPF priority
    
*   Verify DR/BDR/DROTHER states on router interfaces
    

### 🖧 Topology

R1, R2, R3, R4 all connected to a central switch SW1 on subnet 10.0.0.0/24; R1 G0/0 (10.0.0.1), R2 G0/0 (10.0.0.2), R3 G0/0 (10.0.0.3), R4 G0/0 (10.0.0.4); Each router has a loopback: R1=1.1.1.1/32, R2=2.2.2.2/32, R3=3.3.3.3/32, R4=4.4.4.4/32

### 📝 Tasks

1.  Cable all four routers to SW1 and configure IP addressing including loopback interfaces
    
2.  Configure OSPF process 1 on all routers, advertising 10.0.0.0/24 and loopbacks into Area 0
    
3.  Set router-IDs using loopback addresses and verify default DR/BDR election
    
4.  Modify OSPF priority so R2 becomes DR (priority 255) and R3 becomes BDR (priority 200)
    
5.  Set R1 priority to 0 so it never becomes DR/BDR
    
6.  Clear OSPF process on all routers to force new election and verify results
    
7.  Document which router is DR, BDR, and DROTHER
