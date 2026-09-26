### 🎯 Objectives

*   Configure Layer 2 EtherChannel using LACP protocol
    
*   Configure Layer 2 EtherChannel using PAgP protocol
    
*   Verify EtherChannel operation and understand load-balancing methods
    

### 🖧 Topology

SW1 -- SW2 connected via f0/1-f0/2 (LACP EtherChannel); SW2 -- SW3 connected via f0/3-f0/4 (PAgP EtherChannel); Linear topology for simplicity

### 📝 Tasks

1.  Connect SW1 to SW2 using two cables: f0/1-f0/1 and f0/2-f0/2
    
2.  Connect SW2 to SW3 using two cables: f0/3-f0/3 and f0/4-f0/4
    
3.  Configure Port-Channel 1 between SW1-SW2 using LACP (SW1 active, SW2 passive)
    
4.  Configure Port-Channel 2 between SW2-SW3 using PAgP (SW2 desirable, SW3 auto)
    
5.  Configure both Port-Channels as trunk links allowing all VLANs
    
6.  Set the EtherChannel load-balancing method to src-dst-ip on all switches
    
7.  Verify EtherChannel formation, protocol negotiation, and member port status
    

**💡 Show Solution & Verification**

Lab 10: Enterprise Network STP Optimization with RSTP, EtherChannel, and Security Features
------------------------------------------------------------------------------------------

**Advanced**📚 Spanning Tree Protocol (STP/RSTP), PortFast, BPDU Guard, root bridge election, EtherChannel (LACP/PAgP)

### 🎯 Objectives

*   Implement Rapid PVST+ for sub-second convergence across VLANs
    
*   Design hierarchical STP topology with deterministic root placement
    
*   Deploy EtherChannel for increased bandwidth and redundancy between distribution switches
    
*   Secure the STP domain using PortFast, BPDU Guard, and Root Guard
    

### 🖧 Topology

Core/Dist Layer: SW1 (primary core), SW2 (secondary core); Access: SW3, SW4; SW1 g0/1-2 to SW2 g0/1-2 (LACP Po1); SW1 g0/3 to SW3 f0/1; SW2 g0/3 to SW3 f0/2; SW1 g0/4 to SW4 f0/1; SW2 g0/4 to SW4 f0/2; PC1 on SW3 f0/10; PC2 on SW4 f0/10; VLANs 10, 20, 99

### 📝 Tasks

1.  Create VLANs 10 (Users), 20 (Servers), 99 (Mgmt) on all four switches
    
2.  Enable Rapid PVST+ mode on all switches for faster convergence
    
3.  Configure LACP EtherChannel Po1 between SW1-SW2 using active mode on both sides
    
4.  Configure all inter-switch links as trunks allowing only VLANs 10, 20, 99 with native VLAN 99
    
5.  Set SW1 as root primary for VLANs 10, 20, 99 and SW2 as secondary root for all VLANs
    
6.  Configure Root Guard on SW3 and SW4 uplink ports facing SW1 and SW2
    
7.  Configure access ports f0/10 on SW3 and SW4 in VLAN 10 with PortFast and BPDU Guard
    
8.  Test failover by shutting down SW1 and verify SW2 becomes root
    

**💡 Show Solution & Verification**

Lab 11: Basic IPv4 Addressing and Subnet Implementation
-------------------------------------------------------

**Beginner**📚 IP addressing & subnetting: VLSM design, IPv4 addressing plans, IPv6 addressing (SLAAC, EUI-64)

### 🎯 Objectives

*   Configure IPv4 addresses on router interfaces
    
*   Assign IP addresses to end devices in different subnets
    
*   Verify layer 3 connectivity between devices using ping and show commands
    

### 🖧 Topology

R1 -- SW1 -- PC1, PC2; R1 -- SW2 -- PC3, PC4; R1 G0/0 connects to SW1 Fa0/1; R1 G0/1 connects to SW2 Fa0/1

### 📝 Tasks

1.  Given the network 192.168.10.0/24, divide it into two equal /25 subnets
    
2.  Configure R1 G0/0 with the first usable IP of subnet 1 (192.168.10.0/25)
    
3.  Configure R1 G0/1 with the first usable IP of subnet 2 (192.168.10.128/25)
    
4.  Assign PC1 and PC2 valid IP addresses in subnet 1 with the correct default gateway
    
5.  Assign PC3 and PC4 valid IP addresses in subnet 2 with the correct default gateway
    
6.  Verify connectivity by pinging from PC1 to PC4 across subnets
    

**💡 Show Solution & Verification**

Lab 12: VLSM Network Design for Multi-Department Organization
-------------------------------------------------------------

**Intermediate**📚 IP addressing & subnetting: VLSM design, IPv4 addressing plans, IPv6 addressing (SLAAC, EUI-64)

### 🎯 Objectives

*   Design an efficient VLSM addressing scheme based on varying host requirements
    
*   Allocate subnets of different sizes to minimize IP address waste
    
*   Implement the VLSM design on a multi-router topology
    
*   Configure static routing for full network reachability
    

### 🖧 Topology

R1 -- R2 (serial WAN link); R1 G0/0 -- SW1 -- Sales Dept (50 hosts); R1 G0/1 -- SW2 -- IT Dept (25 hosts); R2 G0/0 -- SW3 -- HR Dept (10 hosts); R2 G0/1 -- SW4 -- Mgmt (5 hosts); R1 S0/0/0 to R2 S0/0/0

### 📝 Tasks

1.  Using network 172.16.0.0/24, design a VLSM scheme: Sales=50 hosts, IT=25 hosts, HR=10 hosts, Management=5 hosts, WAN=2 hosts
    
2.  Document your VLSM allocation starting with the largest subnet requirement first
    
3.  Configure R1 G0/0 and G0/1 with the first usable IPs of the Sales and IT subnets
    
4.  Configure the serial WAN link between R1 S0/0/0 and R2 S0/0/0 with the point-to-point subnet
    
5.  Configure R2 G0/0 and G0/1 with the first usable IPs of the HR and Management subnets
    
6.  Configure static routes on R1 to reach HR and Management networks via R2
    
7.  Configure static routes on R2 to reach Sales and IT networks via R1
    
8.  Test end-to-end connectivity by pinging from a Sales PC to an HR PC
    

**💡 Show Solution & Verification**

Lab 13: IPv6 SLAAC Configuration and Automatic Address Assignment
-----------------------------------------------------------------

**Intermediate**📚 IP addressing & subnetting: VLSM design, IPv4 addressing plans, IPv6 addressing (SLAAC, EUI-64)

### 🎯 Objectives

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
    

**💡 Show Solution & Verification**

Lab 14: IPv6 EUI-64 Address Configuration on Router Interfaces
--------------------------------------------------------------

**Advanced**📚 IP addressing & subnetting: VLSM design, IPv4 addressing plans, IPv6 addressing (SLAAC, EUI-64)

### 🎯 Objectives

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
    

**💡 Show Solution & Verification**

Lab 15: Enterprise Dual-Stack Network with VLSM and IPv6 SLAAC
--------------------------------------------------------------

**Advanced**📚 IP addressing & subnetting: VLSM design, IPv4 addressing plans, IPv6 addressing (SLAAC, EUI-64)

### 🎯 Objectives

*   Design a complete VLSM IPv4 addressing scheme for an enterprise with multiple VLANs
    
*   Implement dual-stack (IPv4 and IPv6) addressing on all router interfaces
    
*   Configure router-on-a-stick for inter-VLAN routing with both protocols
    
*   Enable SLAAC for IPv6 client addressing while using static IPv4 assignments
    

### 🖧 Topology

HQ\_R1 -- WAN -- Branch\_R2; HQ\_R1 G0/0 -- SW1 (trunk) -- VLAN10:Engineering(100 hosts), VLAN20:Sales(50 hosts); Branch\_R2 G0/0 -- SW2 -- VLAN30:Remote(25 hosts); HQ\_R1 S0/0/0 -- Branch\_R2 S0/0/0 (WAN)

### 📝 Tasks

1.  Design VLSM plan using 10.0.0.0/23: Engineering=100 hosts, Sales=50 hosts, Remote=25 hosts, WAN=2 hosts
    
2.  Create VLANs 10, 20 on SW1 and configure trunk port to HQ\_R1 G0/0
    
3.  Configure HQ\_R1 G0/0.10 and G0/0.20 subinterfaces with 802.1Q encapsulation and IPv4/IPv6 addresses
    
4.  Assign IPv6 prefixes: VLAN10=2001:DB8:CAFE:10::/64, VLAN20=2001:DB8:CAFE:20::/64, VLAN30=2001:DB8:CAFE:30::/64, WAN=2001:DB8:CAFE:FF::/64
    
5.  Configure the serial WAN link between HQ\_R1 and Branch\_R2 with both IPv4 and IPv6 addresses
    
6.  Configure Branch\_R2 G0/0 for the Remote subnet with both IPv4 and IPv6
    
7.  Configure IPv4 and IPv6 static routes on both routers for full reachability
    
8.  Verify dual-stack connectivity from Engineering VLAN to Remote VLAN using both ping and ping ipv6
    

**💡 Show Solution & Verification**

Lab 16: Basic IPv4 Static Route Configuration
---------------------------------------------

**Beginner**📚 Static routing & default routes (IPv4 and IPv6), floating static routes

### 🎯 Objectives

*   Configure IPv4 addresses on router interfaces
    
*   Implement static routes to enable inter-network communication
    
*   Verify routing table entries and end-to-end connectivity
    

### 🖧 Topology

PC1 -- R1 (G0/1) -- (G0/0) R1 -- (G0/0) R2 (G0/1) -- PC2; R1 G0/0: 10.0.0.1/30, R2 G0/0: 10.0.0.2/30; R1 G0/1: 192.168.1.1/24 (to PC1); R2 G0/1: 192.168.2.1/24 (to PC2)

### 📝 Tasks

1.  Cable the topology as shown and power on all devices
    
2.  Configure hostnames on R1 and R2
    
3.  Configure IP addresses on all router interfaces and enable them with no shutdown
    
4.  Configure PC1 with IP 192.168.1.10/24 and default gateway 192.168.1.1
    
5.  Configure PC2 with IP 192.168.2.10/24 and default gateway 192.168.2.1
    
6.  On R1, configure a static route to reach the 192.168.2.0/24 network via R2's next-hop address
    
7.  On R2, configure a static route to reach the 192.168.1.0/24 network via R1's next-hop address
    
8.  Verify connectivity by pinging from PC1 to PC2
    

**💡 Show Solution & Verification**

Lab 17: IPv4 Default Route to ISP Gateway
-----------------------------------------

**Beginner**📚 Static routing & default routes (IPv4 and IPv6), floating static routes

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
    

**💡 Show Solution & Verification**

Lab 18: IPv6 Static Routing with Link-Local Next-Hop
----------------------------------------------------

**Intermediate**📚 Static routing & default routes (IPv4 and IPv6), floating static routes

### 🎯 Objectives

*   Configure IPv6 global unicast addresses on router interfaces
    
*   Implement IPv6 static routes using link-local addresses as next-hop
    
*   Understand the requirement to specify exit interface when using link-local next-hop
    
*   Configure and verify an IPv6 default route
    

### 🖧 Topology

PC1 -- R1 (G0/1: 2001:DB8:ACAD:10::1/64) -- (G0/0: 2001:DB8:ACAD:1::1/64) R1 -- (G0/0: 2001:DB8:ACAD:1::2/64) R2 -- (G0/1: 2001:DB8:ACAD:20::1/64) R2 -- PC2

### 📝 Tasks

1.  Cable the topology and configure hostnames on both routers
    
2.  Enable IPv6 unicast routing on both R1 and R2
    
3.  Configure IPv6 global unicast addresses on all router interfaces per the topology
    
4.  Manually configure link-local addresses: R1 G0/0 as FE80::1, R2 G0/0 as FE80::2
    
5.  Configure PC1 with 2001:DB8:ACAD:10::100/64 and default gateway 2001:DB8:ACAD:10::1
    
6.  Configure PC2 with 2001:DB8:ACAD:20::100/64 and default gateway 2001:DB8:ACAD:20::1
    
7.  On R1, configure an IPv6 static route to 2001:DB8:ACAD:20::/64 using exit-interface and link-local next-hop FE80::2
    
8.  On R2, configure an IPv6 static route to 2001:DB8:ACAD:10::/64 using exit-interface and link-local next-hop FE80::1
    

**💡 Show Solution & Verification**

Lab 19: Floating Static Routes for WAN Redundancy
-------------------------------------------------

**Intermediate**📚 Static routing & default routes (IPv4 and IPv6), floating static routes

### 🎯 Objectives

*   Understand administrative distance and its role in route preference
    
*   Configure floating static routes as backup paths with higher AD
    
*   Test and verify automatic failover when the primary link fails
    

### 🖧 Topology

HQ\_PC -- R1 (G0/2: 192.168.1.1/24) -- Primary Link (G0/0: 10.0.0.1/30) -- (G0/0: 10.0.0.2/30) R2; R1 (G0/1: 10.0.1.1/30) -- Backup Link -- (G0/1: 10.0.1.2/30) R2; R2 (G0/2: 192.168.2.1/24) -- Branch\_PC

### 📝 Tasks

1.  Build the dual-link topology between R1 and R2
    
2.  Configure all IP addresses on both routers including LAN and both WAN links
    
3.  Configure HQ\_PC with 192.168.1.10/24 gateway 192.168.1.1 and Branch\_PC with 192.168.2.10/24 gateway 192.168.2.1
    
4.  On R1, configure a primary static route to 192.168.2.0/24 via 10.0.0.2 (default AD of 1)
    
5.  On R1, configure a floating static route to 192.168.2.0/24 via 10.0.1.2 with AD of 10
    
6.  On R2, configure matching primary and floating static routes to reach 192.168.1.0/24
    
7.  Verify that only the primary route (via G0/0) appears in the routing table
    
8.  Shutdown the primary link on R1 (G0/0) and verify the floating route activates
    

**💡 Show Solution & Verification**

Lab 20: Dual-Stack Static Routing with IPv4/IPv6 Floating Routes
----------------------------------------------------------------

**Advanced**📚 Static routing & default routes (IPv4 and IPv6), floating static routes

### 🎯 Objectives

*   Implement a complete dual-stack network with both IPv4 and IPv6 static routing
    
*   Configure default routes for both protocol families toward an upstream router
    
*   Implement floating static routes for redundancy in both IPv4 and IPv6
    
*   Verify failover behavior for both protocol stacks simultaneously
    

### 🖧 Topology

LAN\_Server -- CORE (G0/2) -- (G0/0) CORE -- (G0/1) EDGE1 -- (G0/0) EDGE1 -- ISP; CORE (G0/1) -- (G0/1) EDGE2 -- (G0/0) EDGE2 -- ISP; IPv4: CORE-EDGE1 10.1.1.0/30, CORE-EDGE2 10.2.2.0/30, EDGE1-ISP 203.0.113.0/30, EDGE2-ISP 203.0.113.4/30, LAN 172.16.50.0/24; IPv6: CORE-EDGE1 2001:DB8:1::/64, CORE-EDGE2 2001:DB8:2::/64, EDGE1-ISP 2001:DB8:A::/64, EDGE2-ISP 2001:DB8:B::/64, LAN 2001:DB8:50::/64

### 📝 Tasks

1.  Build the topology with CORE router connected to two EDGE routers, both connecting to ISP
    
2.  Configure all IPv4 and IPv6 addresses on CORE, EDGE1, EDGE2, and ISP routers per topology
    
3.  Enable IPv6 unicast-routing on all routers
    
4.  On CORE, configure primary IPv4 default route via EDGE1 (10.1.1.1) and floating backup via EDGE2 (10.2.2.1) with AD 25
    
5.  On CORE, configure primary IPv6 default route via EDGE1 (2001:DB8:1::1) and floating backup via EDGE2 with AD 25
    
6.  On EDGE1 and EDGE2, configure default routes toward ISP and static routes back to LAN 172.16.50.0/24 and 2001:DB8:50::/64
    
7.  On ISP, configure static routes to reach the LAN network via EDGE1 (primary) with floating routes via EDGE2
    
8.  Test failover by shutting down CORE's G0/0 interface and verifying both IPv4 and IPv6 switch to backup path
    

**💡 Show Solution & Verification**

Lab 21: Basic Single-Area OSPF with Router-ID and Passive Interfaces
--------------------------------------------------------------------

**Beginner**📚 OSPFv2 single-area and multi-area: adjacencies, router-id, cost, passive interfaces, DR/BDR

### 🎯 Objectives

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
    

**💡 Show Solution & Verification**

Lab 22: OSPF DR/BDR Election and Priority Manipulation
------------------------------------------------------

**Intermediate**📚 OSPFv2 single-area and multi-area: adjacencies, router-id, cost, passive interfaces, DR/BDR

### 🎯 Objectives

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
    

**💡 Show Solution & Verification**

Lab 23: OSPF Cost Manipulation for Path Selection
-------------------------------------------------

**Intermediate**📚 OSPFv2 single-area and multi-area: adjacencies, router-id, cost, passive interfaces, DR/BDR

### 🎯 Objectives

*   Understand how OSPF calculates interface cost based on bandwidth
    
*   Modify OSPF cost to influence routing decisions
    
*   Use reference bandwidth to accommodate high-speed links
    

### 🖧 Topology

Triangle topology: R1 connects to R2 via G0/0-G0/0 (10.0.12.0/24); R2 connects to R3 via G0/1-G0/0 (10.0.23.0/24); R1 connects to R3 via G0/1-G0/1 (10.0.13.0/24); R3 has LAN 192.168.100.0/24 on G0/2

### 📝 Tasks

1.  Build the triangle topology and assign IP addresses to all interfaces
    
2.  Enable OSPF area 0 on all routers advertising all connected networks
    
3.  Verify default path from R1 to 192.168.100.0/24 (should be direct via R3)
    
4.  Change reference bandwidth to 10000 Mbps on ALL routers for consistency
    
5.  Increase the OSPF cost on R1 G0/1 to 1000 to force traffic through R2
    
6.  Verify the routing table now shows path to 192.168.100.0/24 via R2
    
7.  Use traceroute from R1 to confirm traffic flows R1->R2->R3
    

**💡 Show Solution & Verification**

Lab 24: Multi-Area OSPF with ABR Configuration
----------------------------------------------

**Intermediate**📚 OSPFv2 single-area and multi-area: adjacencies, router-id, cost, passive interfaces, DR/BDR

### 🎯 Objectives

*   Configure multi-area OSPF with backbone Area 0 and standard areas
    
*   Understand the role of Area Border Routers (ABRs)
    
*   Verify inter-area routes (O IA) in the routing table
    

### 🖧 Topology

R1 in Area 1 connects to R2 (ABR) via S0/0/0-S0/0/0 (10.0.12.0/30); R2 connects to R3 (ABR) via G0/0-G0/0 in Area 0 (10.0.23.0/24); R3 connects to R4 in Area 2 via S0/0/0-S0/0/0 (10.0.34.0/30); R1 LAN: 172.16.1.0/24 on G0/0; R4 LAN: 172.16.4.0/24 on G0/0

### 📝 Tasks

1.  Configure IP addressing on all interfaces including serial links (clock rate 128000 on DCE)
    
2.  Configure R1 with OSPF: advertise 172.16.1.0/24 and 10.0.12.0/30 into Area 1
    
3.  Configure R2 as ABR: 10.0.12.0/30 in Area 1, 10.0.23.0/24 in Area 0
    
4.  Configure R3 as ABR: 10.0.23.0/24 in Area 0, 10.0.34.0/30 in Area 2
    
5.  Configure R4 with OSPF: advertise 172.16.4.0/24 and 10.0.34.0/30 into Area 2
    
6.  Set appropriate router-IDs on all routers
    
7.  Verify ABR status and inter-area route propagation
    

**💡 Show Solution & Verification**

Lab 25: Comprehensive Multi-Area OSPF with DR/BDR, Cost, and Passive Interfaces
-------------------------------------------------------------------------------

**Advanced**📚 OSPFv2 single-area and multi-area: adjacencies, router-id, cost, passive interfaces, DR/BDR

### 🎯 Objectives

*   Design and implement a multi-area OSPF network with all key features
    
*   Configure DR/BDR election, cost manipulation, and passive interfaces together
    
*   Troubleshoot and verify complex OSPF adjacencies across areas
    
*   Optimize OSPF behavior using multiple configuration techniques
    

### 🖧 Topology

Area 0 (Backbone): R1, R2, R3 connected via SW1 (10.0.0.0/24) - multi-access segment; R1 G0/0=10.0.0.1, R2 G0/0=10.0.0.2, R3 G0/0=10.0.0.3; Area 10: R1 G0/1 (10.1.14.1/24) to R4 G0/0 (10.1.14.4/24); Area 20: R3 G0/1 (10.2.35.3/24) to R5 G0/0 (10.2.35.5/24); R4 LAN: 192.168.10.0/24 on G0/1; R5 LAN: 192.168.20.0/24 on G0/1

### 📝 Tasks

1.  Build the complete topology and configure all IP addressing
    
2.  Configure OSPF on backbone routers R1, R2, R3 with Area 0 on the shared segment
    
3.  Force R2 to be DR (priority 255) and R1 to be BDR (priority 100) on the backbone segment; R3 priority 0
    
4.  Configure R1 as ABR between Area 0 and Area 10; R3 as ABR between Area 0 and Area 20
    
5.  Configure R4 and R5 with OSPF in their respective areas with passive interfaces on LAN segments
    
6.  Set reference-bandwidth to 100000 on ALL routers; manually set cost of 500 on R3 G0/0
    
7.  Configure unique router-IDs: R1=1.1.1.1 through R5=5.5.5.5
    
8.  Verify full connectivity between all LANs and document the path from 192.168.10.0 to 192.168.20.0
    

**💡 Show Solution & Verification**

Lab 26: Basic DHCP Server Configuration on a Router
---------------------------------------------------

**Beginner**📚 Network services: DHCP server/relay, NAT/PAT, NTP, DNS, CDP/LLDP

### 🎯 Objectives

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
    

**💡 Show Solution & Verification**

Lab 27: DHCP Relay Agent for Multi-Subnet Environment
-----------------------------------------------------

**Intermediate**📚 Network services: DHCP server/relay, NAT/PAT, NTP, DNS, CDP/LLDP

### 🎯 Objectives

*   Configure a centralized DHCP server serving multiple remote subnets
    
*   Implement DHCP relay using ip helper-address on router subinterfaces
    
*   Understand how DHCP relay converts broadcasts to unicasts
    
*   Verify proper address assignment across VLANs
    

### 🖧 Topology

DHCP-Server (10.0.0.10/24) -- R1 (G0/0: 10.0.0.1/24) -- (G0/1 trunk) -- SW1; VLAN10 subnet: 192.168.10.0/24; VLAN20 subnet: 192.168.20.0/24; PC1 in VLAN10, PC2 in VLAN20

### 📝 Tasks

1.  Configure R1 G0/0 with IP 10.0.0.1/24 connecting to the DHCP server network
    
2.  Configure R1 G0/1 as a trunk with subinterfaces for VLAN10 and VLAN20
    
3.  Configure G0/1.10 with IP 192.168.10.1/24 (VLAN 10) and G0/1.20 with IP 192.168.20.1/24 (VLAN 20)
    
4.  On the DHCP server router, create pools for both 192.168.10.0/24 and 192.168.20.0/24
    
5.  Configure ip helper-address 10.0.0.10 on both subinterfaces of R1
    
6.  Configure SW1 with VLANs 10 and 20, trunk to R1, and access ports for PCs
    
7.  Test DHCP by requesting addresses from PC1 and PC2
    

**💡 Show Solution & Verification**

Lab 28: Static NAT and PAT Configuration for Internet Connectivity
------------------------------------------------------------------

**Intermediate**📚 Network services: DHCP server/relay, NAT/PAT, NTP, DNS, CDP/LLDP

### 🎯 Objectives

*   Configure static NAT to expose an internal server with a public IP
    
*   Implement PAT (overload) for internal hosts to share a single public IP
    
*   Correctly designate NAT inside and outside interfaces
    
*   Verify and troubleshoot NAT translations
    

### 🖧 Topology

ISP-Cloud (209.165.200.226) -- R1 (G0/0: 209.165.200.225/30 outside, G0/1: 192.168.1.1/24 inside) -- SW1 -- Web-Server (192.168.1.100), PC1 (DHCP), PC2 (DHCP)

### 📝 Tasks

1.  Configure R1 G0/0 with public IP 209.165.200.225/30 and mark as NAT outside
    
2.  Configure R1 G0/1 with private IP 192.168.1.1/24 and mark as NAT inside
    
3.  Configure static NAT mapping internal Web-Server 192.168.1.100 to public 209.165.200.230
    
4.  Create standard ACL 1 permitting the 192.168.1.0/24 network
    
5.  Configure PAT using ACL 1 overloading on interface G0/0
    
6.  Add a default route pointing to ISP next-hop 209.165.200.226
    
7.  From PC1 and PC2, generate traffic to external destinations
    
8.  Verify both static and dynamic NAT translations are created
    

**💡 Show Solution & Verification**

Lab 29: NTP Time Synchronization Hierarchy with Authentication
--------------------------------------------------------------

**Intermediate**📚 Network services: DHCP server/relay, NAT/PAT, NTP, DNS, CDP/LLDP

### 🎯 Objectives

*   Configure an NTP master as the authoritative time source
    
*   Establish NTP client-server relationships creating a stratum hierarchy
    
*   Implement NTP authentication for security
    
*   Verify synchronization status and stratum levels
    

### 🖧 Topology

R1 (NTP Master, 10.1.1.1/24) -- SW1 -- R2 (10.1.1.2/24) -- SW2 -- R3 (10.1.2.1/24, also 10.1.1.3/24 for NTP); R2 syncs to R1; R3 syncs to R2

### 📝 Tasks

1.  Configure IP addressing: R1 G0/0=10.1.1.1/24, R2 G0/0=10.1.1.2/24 and G0/1=10.1.2.1/24, R3 G0/0=10.1.2.2/24
    
2.  Configure R1 as NTP master at stratum 2
    
3.  Set timezone to UTC on all routers
    
4.  Configure NTP authentication key 1 with password 'Cisco123' on all routers
    
5.  Enable NTP authentication and mark key 1 as trusted on all routers
    
6.  Configure R2 to sync with R1 using authenticated NTP
    
7.  Configure R3 to sync with R2 using authenticated NTP
    
8.  Verify the NTP hierarchy and stratum levels on each device
    

**💡 Show Solution & Verification**

Lab 30: Comprehensive Network Services with CDP/LLDP Discovery
--------------------------------------------------------------

**Advanced**📚 Network services: DHCP server/relay, NAT/PAT, NTP, DNS, CDP/LLDP

### 🎯 Objectives

*   Use CDP and LLDP to discover and document network topology
    
*   Implement security best practices by disabling discovery on edge interfaces
    
*   Integrate DHCP, NAT, NTP, and DNS services in an enterprise scenario
    
*   Configure DNS name resolution on network devices
    

### 🖧 Topology

ISP (203.0.113.2) -- R1-Edge (G0/0: 203.0.113.1/30 outside, G0/1: 10.0.0.1/24) -- SW-Core (VLAN1: 10.0.0.2) -- SW-Access1, SW-Access2; DNS-Server: 10.0.0.53; NTP via R1; Internal LAN: 10.0.0.0/24

### 📝 Tasks

1.  Configure R1 interfaces: G0/0=203.0.113.1/30 (ISP), G0/1=10.0.0.1/24 (internal)
    
2.  Enable CDP globally on R1 and all switches; disable CDP on R1's G0/0 (external-facing)
    
3.  Enable LLDP globally on all switches for multi-vendor support
    
4.  Configure R1 as NTP master stratum 3; configure switches as NTP clients to R1
    
5.  Configure DNS lookup on R1 with name-server 10.0.0.53 and domain ccna-lab.com
    
6.  Configure R1 as DHCP server for 10.0.0.0/24 excluding .1-.20, including DNS option
    
7.  Configure PAT on R1 for internal network using G0/0 for overload
    
8.  Document the topology using CDP neighbor discovery commands
    

**💡 Show Solution & Verification**

Lab 31: Standard Numbered ACL - Block Specific Host Traffic
-----------------------------------------------------------

**Beginner**📚 ACLs: standard & extended numbered/named ACLs, applying to interfaces and VTY lines

### 🎯 Objectives

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
    

**💡 Show Solution & Verification**

Lab 32: Standard Named ACL - Securing VTY Lines for Remote Access
-----------------------------------------------------------------

**Beginner**📚 ACLs: standard & extended numbered/named ACLs, applying to interfaces and VTY lines

### 🎯 Objectives

*   Create a standard named access control list
    
*   Apply an ACL to VTY lines using the access-class command
    
*   Restrict Telnet/SSH management access to authorized hosts only
    

### 🖧 Topology

R1 -- SW1 -- Admin-PC (192.168.1.50), User-PC (192.168.1.100), Attacker-PC (192.168.1.200); R1 G0/0 (192.168.1.1/24) connected to SW1 Fa0/1

### 📝 Tasks

1.  Configure R1 G0/0 with IP 192.168.1.1/24 and enable the interface
    
2.  Configure Admin-PC (192.168.1.50/24), User-PC (192.168.1.100/24), and Attacker-PC (192.168.1.200/24) with gateway 192.168.1.1
    
3.  Enable Telnet access on R1 VTY lines 0-4 with password 'ccna2024' and enable login
    
4.  Verify all three PCs can currently Telnet to R1 (before ACL)
    
5.  Create a standard named ACL called 'ADMIN-ONLY' that permits only the Admin-PC IP address
    
6.  Apply the 'ADMIN-ONLY' ACL to VTY lines 0-4 using the access-class command inbound
    
7.  Test: Admin-PC Telnet should succeed; User-PC and Attacker-PC Telnet attempts should be refused
    

**💡 Show Solution & Verification**

Lab 33: Extended Numbered ACL - Protocol and Port-Based Filtering
-----------------------------------------------------------------

**Intermediate**📚 ACLs: standard & extended numbered/named ACLs, applying to interfaces and VTY lines

### 🎯 Objectives

*   Understand extended ACL syntax including protocol, source, destination, and ports
    
*   Create an extended numbered ACL (100-199 range)
    
*   Filter traffic based on TCP/UDP port numbers for specific services
    
*   Apply extended ACLs close to the traffic source
    

### 🖧 Topology

PC1 (192.168.10.10) -- SW1 -- R1 G0/0 (192.168.10.1); R1 G0/1 (10.10.10.1) -- SW2 -- WebServer (10.10.10.100 HTTP/HTTPS), FileServer (10.10.10.200 FTP)

### 📝 Tasks

1.  Configure R1 G0/0 (192.168.10.1/24) and G0/1 (10.10.10.1/24), enable both interfaces
    
2.  Configure PC1 with 192.168.10.10/24 and gateway 192.168.10.1
    
3.  Configure WebServer with 10.10.10.100/24, enable HTTP service
    
4.  Configure FileServer with 10.10.10.200/24, enable FTP service
    
5.  Verify PC1 can ping both servers, access web pages, and connect via FTP
    
6.  Create extended ACL 110: permit HTTP (TCP 80) and HTTPS (TCP 443) to WebServer, deny FTP (TCP 20-21) to FileServer, permit ICMP to any server, deny all other traffic to server network
    
7.  Apply ACL 110 inbound on R1 G0/0
    
8.  Test: Web access works, FTP is blocked, ping works to both servers
    

**💡 Show Solution & Verification**

Lab 34: Extended Named ACL - DMZ Traffic Policy Implementation
--------------------------------------------------------------

**Intermediate**📚 ACLs: standard & extended numbered/named ACLs, applying to interfaces and VTY lines

### 🎯 Objectives

*   Design and implement an extended named ACL with multiple rules
    
*   Apply proper rule ordering with most specific entries first
    
*   Use established keyword for return traffic optimization
    
*   Implement logging on denied traffic for security monitoring
    

### 🖧 Topology

Internet-Cloud -- R1 G0/0 (203.0.113.1/24); R1 G0/1 (172.16.50.1/24) -- DMZ-SW -- WebServer (172.16.50.10), MailServer (172.16.50.20), DNSServer (172.16.50.30); External-PC (203.0.113.100) simulates internet host

### 📝 Tasks

1.  Configure R1 G0/0 (203.0.113.1/24) facing external network and G0/1 (172.16.50.1/24) facing DMZ
    
2.  Configure WebServer (172.16.50.10/24) with HTTP/HTTPS services enabled
    
3.  Configure MailServer (172.16.50.20/24) with SMTP (25) service enabled
    
4.  Configure DNSServer (172.16.50.30/24) with DNS (53) service enabled
    
5.  Configure External-PC (203.0.113.100/24) with gateway 203.0.113.1
    
6.  Create extended named ACL 'INBOUND-DMZ-POLICY' with rules: permit HTTP/HTTPS to WebServer, permit SMTP to MailServer, permit DNS (UDP) to DNSServer, deny and log all other traffic to DMZ
    
7.  Apply 'INBOUND-DMZ-POLICY' inbound on R1 G0/0
    
8.  Verify permitted services work and denied traffic generates log messages
    

**💡 Show Solution & Verification**

Lab 35: Comprehensive ACL Deployment - Multi-Site Enterprise Security
---------------------------------------------------------------------

**Advanced**📚 ACLs: standard & extended numbered/named ACLs, applying to interfaces and VTY lines

### 🎯 Objectives

*   Implement multiple ACL types (standard and extended, numbered and named) across a network
    
*   Apply ACLs to both data interfaces and VTY management lines
    
*   Follow best practices: standard ACLs near destination, extended ACLs near source
    
*   Troubleshoot and verify complex multi-ACL configurations
    

### 🖧 Topology

HQ-Site: HQ-R1 G0/0 (10.1.10.1/24) -- Admin-SW -- Admin-PC (10.1.10.50); HQ-R1 G0/1 (10.1.20.1/24) -- User-SW -- User-PC (10.1.20.100); HQ-R1 S0/0/0 (172.16.0.1/30) -- WAN -- Branch-R2 S0/0/0 (172.16.0.2/30); Branch-R2 G0/0 (192.168.100.1/24) -- Server-SW -- FileServer (192.168.100.10), WebServer (192.168.100.20)

### 📝 Tasks

1.  Configure all IP addressing as per topology on HQ-R1 and Branch-R2
    
2.  Configure OSPF process 1 area 0 on both routers advertising all connected networks
    
3.  Verify full IP reachability between all devices before applying ACLs
    
4.  On HQ-R1: Create extended named ACL 'USER-POLICY' - permit User-PC subnet to WebServer HTTP/HTTPS only, deny User-PC subnet to FileServer completely, permit all other traffic
    
5.  Apply 'USER-POLICY' inbound on HQ-R1 G0/1 (near source - Users)
    
6.  On Branch-R2: Create standard numbered ACL 15 - permit only Admin subnet (10.1.10.0/24) access toward FileServer
    
7.  Apply ACL 15 outbound on Branch-R2 G0/0 (near destination - Servers)
    
8.  On BOTH routers: Create standard named ACL 'VTY-SECURE' permitting only Admin subnet, apply to VTY 0-4 with SSH transport input
    

**💡 Show Solution & Verification**

Lab 36: Basic Password Security and Login Banners
-------------------------------------------------

**Beginner**📚 Device security & management: SSH, port security, passwords, banners, local users, AAA basics

### 🎯 Objectives

*   Configure enable secret and console passwords on a Cisco router
    
*   Enable password encryption service to protect plaintext passwords
    
*   Create MOTD and login banners for legal notification
    

### 🖧 Topology

R1 -- SW1 -- PC1; PC1 connected to SW1 Fa0/1; R1 G0/0 connected to SW1 Fa0/24; Console access from PC1 to R1

### 📝 Tasks

1.  Access R1 via console and enter global configuration mode
    
2.  Set the hostname to R1 and configure an enable secret password of 'Cisco123'
    
3.  Configure the console line with password 'ConPass99' and require login
    
4.  Enable the service to encrypt all plaintext passwords in the configuration
    
5.  Create a Message of the Day banner warning unauthorized users
    
6.  Create a login banner that displays before the username prompt
    
7.  Save the configuration and test by exiting and reconnecting
    

**💡 Show Solution & Verification**

Lab 37: Configuring Secure SSH Remote Access
--------------------------------------------

**Intermediate**📚 Device security & management: SSH, port security, passwords, banners, local users, AAA basics

### 🎯 Objectives

*   Configure SSH version 2 on a Cisco router for secure remote management
    
*   Create local user accounts for SSH authentication
    
*   Disable insecure Telnet access on VTY lines
    
*   Test SSH connectivity from a remote host
    

### 🖧 Topology

R1 (G0/0: 192.168.1.1/24) -- SW1 -- PC1 (192.168.1.10/24); PC1 Fa0 to SW1 Fa0/1; R1 G0/0 to SW1 Fa0/24

### 📝 Tasks

1.  Configure R1 with hostname and IP domain name 'ccnalab.local'
    
2.  Generate a 2048-bit RSA key pair for SSH encryption
    
3.  Create a local user 'admin' with secret password 'SSHpass123' and privilege level 15
    
4.  Configure VTY lines 0-4 to use local authentication and allow only SSH
    
5.  Set SSH version 2 and configure a timeout of 60 seconds with 2 authentication retries
    
6.  Configure the G0/0 interface with IP address 192.168.1.1/24
    
7.  From PC1, test SSH connectivity to R1 using the admin credentials
    

**💡 Show Solution & Verification**

Lab 38: Switch Port Security with Sticky MAC Addresses
------------------------------------------------------

**Intermediate**📚 Device security & management: SSH, port security, passwords, banners, local users, AAA basics

### 🎯 Objectives

*   Configure port security on switch access ports to limit MAC addresses
    
*   Implement sticky MAC address learning for automatic secure MAC configuration
    
*   Configure different violation modes and understand their behavior
    
*   Verify and troubleshoot port security status
    

### 🖧 Topology

SW1 -- PC1 (Fa0/1), PC2 (Fa0/2), PC3 (Fa0/3), Server1 (Fa0/10); All devices in VLAN 1 with 192.168.1.0/24 network

### 📝 Tasks

1.  Configure Fa0/1 with port security allowing only 1 MAC address using sticky learning and shutdown violation mode
    
2.  Configure Fa0/2 with port security allowing maximum 2 MAC addresses with restrict violation mode
    
3.  Configure Fa0/3 with port security using a static MAC address aa11.bb22.cc33 and protect violation mode
    
4.  Configure Fa0/10 for the server with maximum 1 MAC address and shutdown violation mode
    
5.  Enable all configured interfaces and generate traffic from each PC
    
6.  Simulate a violation on Fa0/1 by connecting a different device and observe the result
    
7.  Recover the err-disabled port and verify all port security configurations
    

**💡 Show Solution & Verification**

Lab 39: Multi-User Local Authentication with Privilege Levels
-------------------------------------------------------------

**Intermediate**📚 Device security & management: SSH, port security, passwords, banners, local users, AAA basics

### 🎯 Objectives

*   Create multiple local user accounts with different privilege levels
    
*   Configure custom privilege levels with specific command access
    
*   Implement login local authentication on console and VTY lines
    
*   Test user access restrictions based on privilege levels
    

### 🖧 Topology

R1 (G0/0: 10.0.0.1/24) -- SW1 -- AdminPC (10.0.0.10/24), HelpdeskPC (10.0.0.20/24); Console access available to R1

### 📝 Tasks

1.  Create user 'netadmin' with privilege level 15 and secret 'Admin@123'
    
2.  Create user 'helpdesk' with privilege level 5 and secret 'Help@456'
    
3.  Create user 'monitor' with privilege level 1 and secret 'View@789'
    
4.  Configure privilege level 5 to allow show commands: show ip interface brief, show interfaces, show running-config
    
5.  Configure console line to use local authentication with a 10-minute timeout
    
6.  Configure VTY lines 0-4 for local authentication with SSH only
    
7.  Test each user account and verify their command access restrictions
    

**💡 Show Solution & Verification**

Lab 40: AAA Configuration with Local and Fallback Authentication
----------------------------------------------------------------

**Advanced**📚 Device security & management: SSH, port security, passwords, banners, local users, AAA basics

### 🎯 Objectives

*   Enable and configure the AAA framework on a Cisco router
    
*   Create named authentication method lists for different access methods
    
*   Implement local database authentication with enable fallback
    
*   Configure AAA authorization and basic accounting
    

### 🖧 Topology

R1 (G0/0: 172.16.1.1/24) -- SW1 -- AdminPC (172.16.1.100/24), TestPC (172.16.1.101/24); R1 also connected to simulated TACACS+ server at 172.16.1.200 (for future use)

### 📝 Tasks

1.  Create local users: 'aaaadmin' (priv 15, secret 'AAAadm1n'), 'aaauser' (priv 1, secret 'AAAus3r')
    
2.  Enable the AAA new-model on the router
    
3.  Create a default authentication method list using local database with enable password as fallback
    
4.  Create a named method list 'CONSOLE-AUTH' for console using local-case (case-sensitive)
    
5.  Create a named method list 'VTY-AUTH' for VTY using local authentication
    
6.  Apply the appropriate method lists to console and VTY lines
    
7.  Configure AAA authorization for exec sessions using local database
    
8.  Configure basic AAA accounting to log start-stop records for exec sessions
    

**💡 Show Solution & Verification**

Lab 41: Basic HSRP Gateway Redundancy Configuration
---------------------------------------------------

**Beginner**📚 Wireless & WLAN config concepts (WLC/AP), plus first-hop redundancy (HSRP)

### 🎯 Objectives

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
    

**💡 Show Solution & Verification**

Lab 42: Wireless LAN Controller Basic WLAN Deployment
-----------------------------------------------------

**Beginner**📚 Wireless & WLAN config concepts (WLC/AP), plus first-hop redundancy (HSRP)

### 🎯 Objectives

*   Understand the split-MAC architecture of lightweight APs and WLCs
    
*   Configure a basic WLAN on a Cisco Wireless LAN Controller
    
*   Associate a lightweight access point with the WLC
    
*   Connect wireless clients to the newly created WLAN
    

### 🖧 Topology

WLC-1 connects to SW1 G0/1 (trunk port); LAP-1 (Lightweight AP) connects to SW1 F0/1 (access port VLAN 100); SW1 F0/24 connects to R1 G0/0 (default gateway); Management VLAN 100 subnet 192.168.100.0/24; Wireless clients VLAN 110 subnet 192.168.110.0/24; Laptop-1 and Smartphone-1 as wireless clients

### 📝 Tasks

1.  Configure SW1 with VLANs 100 (Management) and 110 (Wireless-Users) and appropriate trunk/access ports
    
2.  Configure R1 as the default gateway with subinterfaces for both VLANs and enable DHCP pools
    
3.  Access the WLC web interface and complete initial setup wizard with management IP 192.168.100.10/24
    
4.  Create a new WLAN named 'Corporate-WiFi' with SSID 'CorpNet' mapped to VLAN 110
    
5.  Configure WPA2-PSK security on the WLAN with passphrase 'Cisco12345'
    
6.  Verify the lightweight AP has joined the WLC and is broadcasting the SSID
    
7.  Connect Laptop-1 wirelessly to 'CorpNet' and verify IP assignment from VLAN 110 pool
    

**💡 Show Solution & Verification**

Lab 43: HSRP with Interface Tracking and Preemption
---------------------------------------------------

**Intermediate**📚 Wireless & WLAN config concepts (WLC/AP), plus first-hop redundancy (HSRP)

### 🎯 Objectives

*   Configure HSRP interface tracking to monitor upstream link status
    
*   Implement HSRP preemption for automatic failback
    
*   Tune HSRP timers for faster convergence
    
*   Verify tracking behavior during link failures
    

### 🖧 Topology

R1 G0/0 and R2 G0/0 connect to SW1 (LAN side); R1 G0/1 connects to ISP1; R2 G0/1 connects to ISP2; PC1/PC2 on SW1; LAN: 10.1.1.0/24, Virtual IP: 10.1.1.1; R1 G0/1: 203.0.113.1/30 to ISP1; R2 G0/1: 198.51.100.1/30 to ISP2

### 📝 Tasks

1.  Configure basic IP addressing on all router interfaces as per topology
    
2.  Configure HSRP group 1 on both routers with virtual IP 10.1.1.1
    
3.  Set R1 as primary with priority 120 and R2 with default priority 100
    
4.  Enable preemption on both routers with a 30-second delay
    
5.  Configure R1 to track interface G0/1 and decrement priority by 30 if the link goes down
    
6.  Adjust HSRP hello timer to 1 second and hold timer to 3 seconds on both routers
    
7.  Test by shutting down R1 G0/1 and verify R2 becomes active
    
8.  Restore R1 G0/1 and verify R1 preempts back to active after delay
    

**💡 Show Solution & Verification**

Lab 44: Multi-VLAN Wireless Deployment with WLC
-----------------------------------------------

**Intermediate**📚 Wireless & WLAN config concepts (WLC/AP), plus first-hop redundancy (HSRP)

### 🎯 Objectives

*   Configure multiple WLANs for different user groups on a single WLC
    
*   Map WLANs to separate VLANs using dynamic interfaces
    
*   Implement different security policies per WLAN
    
*   Verify wireless client VLAN assignment and isolation
    

### 🖧 Topology

WLC-1 connects to DSW1 (distribution switch) via trunk; Two LAPs connect to ASW1 (access switch); DSW1 interconnects to R1 for inter-VLAN routing; VLAN 10: Management (192.168.10.0/24); VLAN 20: Employee-WLAN (192.168.20.0/24); VLAN 30: Guest-WLAN (192.168.30.0/24); VLAN 40: IoT-WLAN (192.168.40.0/24)

### 📝 Tasks

1.  Configure VLANs 10, 20, 30, and 40 on DSW1 and ASW1 with appropriate trunk links
    
2.  Configure R1 with router-on-a-stick for inter-VLAN routing and DHCP pools for each VLAN
    
3.  On WLC, create dynamic interfaces for Employee (VLAN 20), Guest (VLAN 30), and IoT (VLAN 40)
    
4.  Create WLAN 'Employee-Secure' with WPA2-PSK mapped to Employee interface
    
5.  Create WLAN 'Guest-Open' with open authentication mapped to Guest interface
    
6.  Create WLAN 'IoT-Devices' with WPA2-PSK and a different passphrase mapped to IoT interface
    
7.  Connect test clients to each WLAN and verify correct VLAN/IP assignment
    

**💡 Show Solution & Verification**

Lab 45: Enterprise Campus with HSRP and Centralized Wireless
------------------------------------------------------------

**Advanced**📚 Wireless & WLAN config concepts (WLC/AP), plus first-hop redundancy (HSRP)

### 🎯 Objectives

*   Design and implement a redundant gateway infrastructure using HSRP
    
*   Deploy a centralized wireless solution with WLC high availability considerations
    
*   Integrate wired and wireless VLANs with proper Layer 2/Layer 3 design
    
*   Implement HSRP for both data VLANs and wireless management traffic
    

### 🖧 Topology

Core: R1 and R2 (multilayer switches acting as gateways) with HSRP; Distribution: DSW1 trunk to both R1/R2; Access: ASW1 and ASW2 connecting end devices and LAPs; WLC-1 dual-homed to DSW1; VLANs: 10-Mgmt(10.10.10.0/24), 20-Wired-Users(10.10.20.0/24), 30-Wireless-Users(10.10.30.0/24), 40-Voice(10.10.40.0/24); HSRP Virtual IPs: VLAN20=10.10.20.1, VLAN30=10.10.30.1

### 📝 Tasks

1.  Configure VLANs 10, 20, 30, 40 and VTP domain 'CAMPUS' on all switches with DSW1 as VTP server
    
2.  Configure trunk links between all switches allowing all VLANs
    
3.  On R1, create SVIs for VLANs 20, 30, 40 and configure HSRP group 20 for VLAN 20 (priority 110, active)
    
4.  On R2, create SVIs and configure HSRP group 20 for VLAN 20 (priority 90, standby)
    
5.  Configure HSRP group 30 on both routers for VLAN 30 with R2 as active (priority 110) for load balancing
    
6.  Enable HSRP preemption and interface tracking on both routers tracking their uplink interfaces
    
7.  Configure WLC with management interface in VLAN 10 and create WLAN 'Campus-Wireless' on VLAN 30
    
8.  Verify end-to-end connectivity: wired PC gets gateway 10.10.20.1, wireless client gets gateway 10.10.30.1
    

**💡 Show Solution & Verification**

Lab 46: Basic Connectivity Troubleshooting: Layer 1-3 Issues
------------------------------------------------------------

**Beginner**📚 Troubleshooting & automation: connectivity troubleshooting labs, syslog, and intro REST/JSON concepts

### 🎯 Objectives

*   Identify and resolve common Layer 1 issues (interface shutdown, cable problems)
    
*   Diagnose and fix Layer 2 issues (duplex mismatch, VLAN assignment)
    
*   Troubleshoot Layer 3 issues (incorrect IP addressing, missing default gateway)
    

### 🖧 Topology

R1 (g0/0) -- (f0/1) SW1 (f0/2) -- PC1; SW1 (f0/3) -- PC2; R1 acts as default gateway 192.168.1.1/24; PC1 should be 192.168.1.10/24; PC2 should be 192.168.1.20/24

### 📝 Tasks

1.  Power on all devices and attempt to ping from PC1 to PC2 - document the failure
    
2.  Use 'show ip interface brief' on R1 and 'show interfaces status' on SW1 to identify interface states
    
3.  Check if R1 g0/0 interface is administratively down and bring it up if needed
    
4.  Verify PC1 and PC2 IP configurations using 'ipconfig' and fix any addressing errors
    
5.  Confirm SW1 interfaces are in the correct VLAN using 'show vlan brief'
    
6.  Use 'show interfaces f0/2' to check for duplex/speed mismatches and correct them
    
7.  Test end-to-end connectivity with ping from PC1 to R1 and PC1 to PC2
    
8.  Document the issues found and their resolutions
    

**💡 Show Solution & Verification**

Lab 47: Configuring Syslog for Centralized Network Monitoring
-------------------------------------------------------------

**Intermediate**📚 Troubleshooting & automation: connectivity troubleshooting labs, syslog, and intro REST/JSON concepts

### 🎯 Objectives

*   Configure routers and switches to send syslog messages to a central syslog server
    
*   Understand and configure syslog severity levels (0-7)
    
*   Analyze syslog output to identify network events and issues
    

### 🖧 Topology

R1 (g0/0) -- (f0/1) SW1 (f0/24) -- Syslog-Server (192.168.1.100); R1 g0/0: 192.168.1.1/24; SW1 VLAN1: 192.168.1.2/24; Management network on 192.168.1.0/24

### 📝 Tasks

1.  Configure IP addressing on R1 (g0/0: 192.168.1.1/24) and SW1 (VLAN1: 192.168.1.2/24)
    
2.  Verify connectivity to the syslog server at 192.168.1.100 using ping
    
3.  Configure R1 to send syslog messages to 192.168.1.100 with severity level 'debugging' (level 7)
    
4.  Configure SW1 to send syslog messages to the same server with severity level 'informational' (level 6)
    
5.  Set the logging source interface to the management interface on both devices
    
6.  Configure timestamps for syslog messages using datetime format with milliseconds
    
7.  Generate test events by shutting/no shutting interfaces and observe logs on the syslog server
    
8.  Adjust logging trap level to 'warnings' and verify reduced log volume
    

**💡 Show Solution & Verification**

Lab 48: Troubleshooting Inter-VLAN Routing and Default Gateway Issues
---------------------------------------------------------------------

**Intermediate**📚 Troubleshooting & automation: connectivity troubleshooting labs, syslog, and intro REST/JSON concepts

### 🎯 Objectives

*   Diagnose and resolve router-on-a-stick configuration issues
    
*   Troubleshoot trunk port misconfigurations between switch and router
    
*   Identify and fix subinterface encapsulation and IP addressing problems
    

### 🖧 Topology

R1 (g0/0.10, g0/0.20) -- trunk -- (f0/1) SW1; SW1 (f0/2) -- PC1-VLAN10 (192.168.10.10/24); SW1 (f0/3) -- PC2-VLAN20 (192.168.20.10/24); R1 subinterfaces are gateways: .1 for each subnet

### 📝 Tasks

1.  Attempt to ping from PC1 (VLAN10) to PC2 (VLAN20) and document the failure
    
2.  Verify VLAN configuration on SW1 using 'show vlan brief' - ensure VLANs 10 and 20 exist
    
3.  Check trunk status on SW1 f0/1 using 'show interfaces trunk' and fix if not trunking
    
4.  Verify R1 physical interface g0/0 is enabled and subinterfaces exist using 'show ip interface brief'
    
5.  Check subinterface encapsulation with 'show interfaces g0/0.10' - verify 802.1Q and correct VLAN tag
    
6.  Confirm subinterface IP addresses match the default gateway configured on each PC
    
7.  Fix any misconfigurations found on trunk port or subinterfaces
    
8.  Test inter-VLAN connectivity by pinging between VLANs and to the gateway addresses
    

**💡 Show Solution & Verification**

Lab 49: Introduction to REST APIs and JSON: Network Automation Concepts
-----------------------------------------------------------------------

**Intermediate**📚 Troubleshooting & automation: connectivity troubleshooting labs, syslog, and intro REST/JSON concepts

### 🎯 Objectives

*   Understand REST API fundamentals including HTTP methods (GET, POST, PUT, DELETE)
    
*   Interpret and construct JSON data structures for network configuration
    
*   Use Packet Tracer's IoT or simulation features to interact with REST-like APIs
    

### 🖧 Topology

PC1 (with web browser/API tool) -- SW1 -- (simulated API endpoint); In Packet Tracer: use IoE Server or Home Gateway with REST API capability; Network: 192.168.1.0/24

### 📝 Tasks

1.  Set up PC1 with IP 192.168.1.10/24 and connect to SW1 - verify basic connectivity
    
2.  On PC1, open the web browser or Desktop > Command Prompt and explore available API tools
    
3.  Study the provided JSON example for a VLAN configuration: {"vlan\_id": 100, "name": "Sales", "status": "active"}
    
4.  Identify the JSON data types used: strings, integers, booleans, arrays, and objects in sample configurations
    
5.  Construct a JSON object to represent an interface configuration with keys: interface\_name, ip\_address, subnet\_mask, enabled
    
6.  Write a sample REST API URL structure for retrieving device information: https://\[device-ip\]/restconf/data/interfaces
    
7.  Document the expected HTTP response codes: 200 (OK), 201 (Created), 400 (Bad Request), 401 (Unauthorized), 404 (Not Found)
    
8.  Create a JSON array containing three VLAN objects with different IDs and names
    

**💡 Show Solution & Verification**

Lab 50: Advanced Troubleshooting: Multi-Layer Issues with Syslog Analysis
-------------------------------------------------------------------------

**Advanced**📚 Troubleshooting & automation: connectivity troubleshooting labs, syslog, and intro REST/JSON concepts

### 🎯 Objectives

*   Systematically troubleshoot complex network issues spanning multiple OSI layers
    
*   Use syslog messages and debug output to identify root causes
    
*   Resolve issues involving STP, DHCP, routing, and ACLs simultaneously
    
*   Document troubleshooting methodology and findings
    

### 🖧 Topology

R1 (g0/0) -- (f0/1) SW1 (f0/24) -- (f0/24) SW2 (f0/2) -- PC1; R1 (g0/1) -- Server1 (DHCP/Syslog: 10.0.0.100); R1 is DHCP relay; PC1 should get IP via DHCP from 192.168.1.0/24 pool and reach Server1

### 📝 Tasks

1.  Verify PC1 is not receiving DHCP address - document the symptom
    
2.  Configure syslog on R1 and SW1 to send messages to Server1 (10.0.0.100) at debug level
    
3.  Check SW1-SW2 link status and STP state using 'show spanning-tree' - identify if ports are blocking unexpectedly
    
4.  Verify trunk configuration between SW1 and SW2 allows the required VLANs
    
5.  On R1, verify DHCP relay (ip helper-address) is configured on the interface facing the client network
    
6.  Check for any ACLs blocking DHCP (UDP 67/68) or ICMP traffic using 'show access-lists' and 'show ip interface'
    
7.  Review syslog messages on Server1 to identify any logged errors during troubleshooting
    
8.  After fixes, release/renew DHCP on PC1 and verify full connectivity to Server1 with ping and traceroute
    

**💡 Show Solution & Verification**
