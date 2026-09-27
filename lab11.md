### 🎯 Objectives

*   Understand the purpose and function of a default route (quad-zero route)
    
*   Configure a default static route pointing to an upstream ISP router
    
*   Verify the gateway of last resort is properly set
    

### 🖧 Topology

LAN\_PC -- SW1 -- R1 (G0/1: 192.168.10.1/24) -- (G0/0: 203.0.113.2/30) R1 -- (G0/0: 203.0.113.1/30) ISP -- (G0/1: 8.8.8.1/24) ISP -- Internet\_Server (8.8.8.8)

### 📝 Tasks

1.  Build the topology connecting R1 to ISP\_Router via their G0/0 interfaces
    
2.  Configure IP addressing on R1's G0/0 (WAN) and G0/1 (LAN) interfaces
    
3.  Configure IP addressing on ISP router's G0/0 and G0/1 interfaces
    
4.  Configure LAN\_PC with IP 192.168.10.100/24 and default gateway 192.168.10.1
    
5.  Configure Internet\_Server with IP 8.8.8.8/24 and gateway 8.8.8.1
    
6.  On ISP\_Router, configure a static route back to the 192.168.10.0/24 network
    
7.  On R1, configure a default static route (0.0.0.0/0) pointing to ISP's next-hop address
    
8.  Verify the gateway of last resort and test connectivity to Internet\_Server
