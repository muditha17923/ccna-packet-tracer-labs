### Objectives

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
