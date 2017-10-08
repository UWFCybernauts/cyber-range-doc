## Documentation for the 00000CentOs box

This system is *_NOT_* live

### Role:
ECommerce using a webserver.  
in DMZ.  
Paired with a Debian based DNS server (also in DMZ).  

### System Details:
* Kernel Version: (TODO)
* Firewalld Version: (TODO)
* EXT4 FS
* 1GB Swap
* 1 CPU core: (TODO)

### Firewalld rules (IN:OUT) 
##### OVERALL POLICY ALLOW:ALLOW
* localhost on loopback
    * ALLOW:ALLOW
* LAN to localhost
    * ALLOW:ALLOW
* WAN to localhost
    * ALLOW:ALLOW

### Notable installed tools:
* None

### Services:
##### ACTIVE:
* LAMP stack
    * Linux -> (TODO)
    * Apache -> (TODO)
    * MariaDB -> (TODO)
    * PHP -> (TODO)
* Firewalld -> (TODO)
##### INACTIVE:
* Networking is still pretty iffy. THANKS @CentOS
* Software Policy / User Policy -> disabled by default.
* Connection rate limiter. -> disabled by default.

### Changes from default setup:
* MariaDB
    * Root password assigned for DB admin. Same as the root user on the system.
    * Generic remote user creation disabled 

### Users (username / password):
##### Privelaged Users:
* root
    * toor
##### Unprivelaged users:
* user
    * resu

