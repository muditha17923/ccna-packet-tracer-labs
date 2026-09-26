### 🎯 Objectives

*   Observe the default STP root bridge election process based on bridge ID
    
*   Identify root bridge, root ports, and designated ports
    
*   Understand STP port states and their role in loop prevention
    

### 🖧 Topology

Three switches in triangle: SW1 f0/1 -- SW2 f0/1; SW2 f0/2 -- SW3 f0/1; SW3 f0/2 -- SW1 f0/2. No end devices required.

### 📝 Tasks

1.  Cable three switches in a triangle topology using the specified interfaces
    
2.  Enable all inter-switch interfaces using no shutdown command
    
3.  Wait 30-50 seconds for STP to converge completely
    
4.  Use show spanning-tree on each switch to identify the root bridge
    
5.  Document the bridge ID (priority + MAC) for all three switches
    
6.  Identify and record the root port on each non-root switch
    
7.  Identify which port is in blocking state to prevent the loop
