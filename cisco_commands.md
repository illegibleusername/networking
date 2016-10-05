# CISCO COMMANDS

Configure the device | Switch
------------------ | --------------
`Switch>enable` | enables privileged EXEC mode
`Switch#config terminal` | enables global EXEC mode
`Switch(config)#hostname S1` | assign a hostname to a device
`S1(config)#banner motd #This is a MOTD banner#` | Configure a MOTD Banner
`S1(config)#no ip domain-lookup` | Disable automatic domain lookup
`S1(config)#enable secret class` | Set the privileged EXEC mode secret password to class
`S1(config)#line console 0` | enable console line configuration mode
`S1(config-line)#password cisco` | Set the console password to cisco
`S1(config-line)#login` | Configure the console line to require a password at login
`S1(config-line)#logging synchronous` | Configure logging synchronous
`S1(config-line)#line vty 0 15` | enable VTY line configuration mode
`S1(config-line)#password cisco` | Set the VTY password to cisco
`S1(config-line)#login` | Configure the VTY line to require a password at login
`S1(config-line)#end` | Return to privileged EXEC mode
`S1#conf t` | enables global EXEC mode
`S1(config)#interface vlan 1` | Enter the interface configuration mode for VLAN 1
`S1(config-if)#ip address dotted-decimal subnet-mask` | Set the IP address, subnet mask for the SVI management interface
`S1(config-if)#ip default-gateway dotted-decimal` | Assign default gateway for SVI management interface
`S1(config-if)#exit` | Return to privileged EXEC mode

VERIFY THE CONFIGURATION OF THE SWITCH | |
-------------------------------------- | ------ |
`S1#show running-configuration` | Display current running configuration in RAM
`S1#copy running-config startup-config` | Copy running configuration to NVRAM to remain in place on reload


PRIVILEGED EXEC COMMANDS |  Assorted
------------------------ | ---------- 
`Router1#show ip route` | shows IP routing table
`Router1#show arp` | shows arp table
`Router1#show mac address-table` | shows MAC table
`Router1#show ip interface (brief)` | shows all IP interfaces and statistics
`Router1#show interface type-and-number` | shows status of specific interface
