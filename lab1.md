🎯 Objectives

Create VLANs and assign meaningful names on a switch
Configure switch ports as access ports and assign them to specific VLANs
Verify VLAN configuration and understand Layer 2 segmentation

🖧 Topology
SW1 connected to: PC1 (Fa0/1), PC2 (Fa0/2), PC3 (Fa0/11), PC4 (Fa0/12). All devices connected to a single 2960 switch.

📝 Tasks

Create VLAN 10 and name it 'Sales' on SW1
Create VLAN 20 and name it 'Engineering' on SW1
Configure interfaces Fa0/1 and Fa0/2 as access ports assigned to VLAN 10
Configure interfaces Fa0/11 and Fa0/12 as access ports assigned to VLAN 20
Assign static IPs to PCs: PC1=192.168.10.1/24, PC2=192.168.10.2/24, PC3=192.168.20.1/24, PC4=192.168.20.2/24
Test connectivity between PCs in the same VLAN and between different VLANs
