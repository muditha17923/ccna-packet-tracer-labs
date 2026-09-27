### Objectives

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
