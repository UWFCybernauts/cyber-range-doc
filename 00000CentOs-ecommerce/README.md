## Documentation for the 00000CentOs box

This system is *_NOT_* live

### Role:
* ECommerce using a webserver.  
* in DMZ.  
* Paired with a Debian based DNS server (also in DMZ).  

### System Details:
* Kernel Version: 3.10.0
* Firewalld Version: 0.4.4.4
* EXT4 FS
* 1GB Swap
* 1 CPU core

### Firewalld rules 
* In default public zone
* Allowing ssh https http dhcpv6-client

### Notable installed tools:
* None

### Services:
##### ACTIVE:
* LAMP stack
    * Linux -> 3.10.0
    * Apache -> 2.4.6
    * MariaDB -> 15.1
    * PHP -> 5.4.16
* Firewalld -> 0.4.4.4
* Ethernet connects on boot
##### INACTIVE:
* Software Policy / User Policy -> disabled by default.
* Connection rate limiter. -> disabled by default.

### Changes from default setup:
* MariaDB
    * Root password assigned for DB admin. Same as the root user on the system.
    * Generic remote user creation disabled 
    * Simple ecom database with one table called Passwords :)

### Users (username / password):
##### Privelaged Users:
* root
    * toor
##### Unprivelaged users:
* user
    * resu

