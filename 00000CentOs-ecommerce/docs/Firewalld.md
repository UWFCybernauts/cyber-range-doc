### This file contains useful information concerning firewalld in relation to the CentOS box.
*_This is also mainly notes I found useful wile setting up the firewall_*

Firewalld manages groups of rules using entities called "zones". Zones are sets of rules dictating  
what traffic should be allowed depending on the level of trust you have in the networks  
the computer is connected to. Network interfaces are assigned a zone to dictate the behavior  
that the firewall should allow.

*Zones are not particulary useful for a server.*

##### There are pre-defined zones for firewalld. They are:
* drop: lowest level of trust. all requests are dropped immediatly
* block: All requests are rejected with icmp-host-prohibited or icmp6-adm-prohibited
* public: allows selected incoming connections on a case-by-case basis.
* external: Used to represent the WAN side of a gateway. It is pre-configured for NAT
* internal: The other side of the external zone. Represents the network behind a gateway.
* DMZ: Represents isolated computers that do not have access to the rest of the network.
* work: Trust most computers on the network.
* home: Trust more of the computers on the network.
* trusted: Trust all of the machines in the network.

### Commands guide

#### Tips:
* $ZONE is a zone parameter from above
* $SERVICE is a service E.X. `http`
* $PORT is a portnumber E.X. `80`
* $PROTOCOL is either `tcp` or `udp`
* $INTERFACE is an interface such as `eth0` or `ens33`
* if you want a change you make to be permanent, pass the `--permanent` flag otherwise the change will be lost at firewall restart

##### Get the current state
```
# firewall-cmd --state
```

##### Change the zone for the interface
```
# firewall-cmd --zone=$ZONE --change-interface=$INTERFACE
```

##### List the active zones on *what* interfaces
```
# firewall-cmd --get-active-zones
```

##### List all the services firewalld can currently support
```
# firewall-cmd --get-services
```

##### List all the services for a specifc zone
```
# firewall-cmd --zone=$ZONE --list-services
```

##### Add a service to a zone
```
# firewall-cmd --zone=$ZONE --add-service=$SERVICE
```

##### Remove a service from a zone
```
# firewall-cmd --zone=$ZONE --remove-service=$SERVICE
```

##### Add a specific port to the firewall rules
```
# firewall-cmd --zone=$ZONE --add-port=$PORT/$PROTOCOL
```

##### Add a specific port range to the firewall rules
```
# firewall-cmd --zone=$ZONE --add-port=$PORT-$PORT/$PROTOCOL
```

##### List ports from a zone
```
# firewall-cmd --zone=$ZONE --list-ports
```

##### Adding your own custom service
**Take a look at /usr/lib/firwalld/services/http.xml for an example**
Once you've created your .xml service file;
* move/copy it to /etc/firewalld/services/
* restart the firewall
* you will find the service listed using the get services command




