###  Objectives

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
