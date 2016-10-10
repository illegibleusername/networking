# CISCO COMMANDS

CONFIGURE THE DEVICE | Switch
-------------------- | ------
`Switch>enable` | Enables privileged EXEC mode
`Switch#config terminal` | Enables global EXEC mode
`Switch(config)#hostname S1` | Assign a hostname to a device, in this case S1
`S1(config)#banner motd #This is a MOTD banner#` | Configure a MOTD Banner
`S1(config)#no ip domain-lookup` | Disable automatic domain lookup
`S1(config)#service password-encryption` | Encrypt passwords in the config file
`S1(config)#security passwords min-length` | Ensure that all configured passwords are a minimum of a specified length
`S1(config)# login block-for 120 attempts 3 within 60` | Block login attempts for 120 seconds if there are three failed login attempts within 60 seconds
`S1(config)#enable secret class` | Set the privileged EXEC mode secret password to class
`S1(config)#line console 0` | Enable console line configuration mode
`S1(config-line)#password cisco` | Set the console password to cisco
`S1(config-line)#login` | Configure the console line to require a password at user EXEC mode login
`S1(config-line)#logging synchronous` | Enable logging synchronous
`S1(config-line)#line vty 0 15` | Enable VTY line configuration mode
`S1(config-line)#password cisco` | Set the VTY password to cisco
`S1(config-line)#login` | Configure the VTY line to require a password at Telnet/SSH login
`S1(config-line)#exit` | Return to privileged EXEC mode
`S1(config)#interface vlan 1` | Enter the interface configuration mode for VLAN 1 SVI management interface
`S1(config-if)#ip address dotted-decimal subnet-mask` | Set the IP address, subnet mask for the SVI management interface
`S1(config-if)#no shutdown` | Set the interface administratively up
`S1(config)#default-gateway` | Configure a default gateway

CONFIGURE THE DEVICE | Router
-------------------- | ------
`Router>enable` | Enables privileged EXEC mode
`Router#config terminal` | Enables global EXEC mode
`Router(config)#hostname R1` | Assign a hostname to a device, in this case R1`S1(config)#service password-encryption` | Encrypt passwords in the config file
`R1(config)#security passwords min-length` | Ensure that all configured passwords are a minimum of a specified length
`R1(config)# login block-for 120 attempts 3 within 60` | Block login attempts for 120 seconds if there are three failed login attempts within 60 seconds
`R1(config)#enable secret class` | Set the privileged EXEC mode secret password to class
`R1(config)#line console 0` | Enable console line configuration mode
`R1(config-line)#password cisco` | Set the console password to cisco
`R1(config-line)#login` | Configure the console line to require a password at user EXEC mode login
`R1(config-line)#logging synchronous` | Enable logging synchronous
`R1(config-line)#line vty 0 15` | Enable VTY line configuration mode
`R1(config-line)#password cisco` | Set the VTY password to cisco
`R1(config-line)#login` | Configure the VTY line to require a password at Telnet/SSH login
`R1(config-line)#exit` | Return to privileged EXEC mode
`R1(config)#banner motd #This is a MOTD banner#` | Configure a MOTD Banner
`R1(config)#interface type-and-number` | Configure desired interface (FE, GE, S, etc)
`R1(config-if)#description description-text` | Describe the interface
`R1(config-if)#ip address ipv4-address subnet-mask` | Assign an IPv4 address and subnet mask to the interface
`R1(config-if)#no shutdown` | Set the interface administratively up

messing with config files |
-------------------------------------- | --- |
`S1#show running-configuration` | Display current running configuration in RAM
`S1#copy running-config startup-config` | Copy running configuration to NVRAM to remain in place on reload


VERIFY THE CONFIGURATION OF THE DEVICE | Assorted
-------------------------------------- | -------- |
`Router1#show ip route` | Displays the contents of the IPv4 routing table stored in RAM
`Router1#show arp` | Shows ARP table
`Router1#show mac address-table` | shows MAC table
`Router1#show ip interface` | Displays the IPv4 statistics for all interfaces on a router
`Router1#show ip interface brief` | Displays all interfaces, their IPv4 address, and their current status
`Router1#show interfaces` | Displays statistics for all interfaces on the device
`Router1#ping ipv4-address` | Ping the desired IPv4 address
