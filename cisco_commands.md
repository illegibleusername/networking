# CISCO COMMANDS

CONFIGURE THE DEVICE | Switch
--- | ---
_**Verify the default switch configuration**_ | _**XXX**_ is a variable
`Switch> enable` | Enters privileged EXEC mode
`Switch# show running-config` | Display current running configuration from RAM
`Switch# show startup-config` | Display current default configuration from NVRAM
`Switch# show version` | Display IOS version information
`Switch# show vlan` | Display VLAN configuration
`Switch# show flash` | Display contents of flash directory
`Switch# dir flash:` | Display contents of flash directory
|
_**Configure basic switch settings**_ |
`Switch# configure terminal` | Enters global config mode
`Switch(config)# hostname S1` | Assign hostname _**S1**_ to device
`S1(config)# no ip domain-lookup` | Disable automatic domain lookup
`S1(config)# service password-encryption` | Encrypt passwords in the config file
`S1(config)# security passwords min-length 5` | Ensure that all configured passwords are a minimum of a specified length of _**5**_
`S1(config)# login block-for 120 attempts 3 within 60` | Block login attempts for _**120**_ seconds if there are _**3**_ failed login attempts within _**60**_ seconds
`S1(config)# enable secret class` | Set the privileged EXEC mode secret to _**class**_
`S1(config)# ip default-gateway 192.168.1.1` | Set default gateway for the switch to _**192.168.1.1**_
`S1(config)# banner motd #This is a MOTD banner#` | Set MOTD Banner to _**This is a MOTD banner**_
`S1(config)# no ip http server` | Disable HTTP server
|
_**Configure management VLAN for remote access**_ |
`S1(config)# vlan 666` | Create VLAN _**666**_
`S1(config-vlan)# name Management` | Name VLAN 666 _**Management**_
`S1(config-vlan)# exit` |
`S1(config)# interface vlan 666` | Enter configuration mode for VLAN 666
`S1(config-if)# ip address 192.168.1.2 255.255.255.0` | Set IPv4 address _**192.168.1.2/24**_ on the internal virtual interface
`S1(config-if)# no shutdown` | Set interface administratively up
`S1(config-if)# exit` |
`S1(config)# interface range f0/1 – 24,g0/1 - 2` | Enter config mode for interface range _**f0/1 – 24,g0/1 - 2**_
`S1(config-if-range)# switchport access vlan 666` | Assign all user ports to VLAN 666
`S1(config-if-range)# exit` |
`S1(config)# do show vlan brief` | Verify all user ports are in VLAN 666
|
_**Configure lines**_ |
`S1(config)# line console 0` | Enter configuration mode for console line 0
`S1(config-line)# password cisco` | Set the console password to _**cisco**_
`S1(config-line)# login` | Configure the console line to require a password at user EXEC mode login
`S1(config-line)# logging synchronous` | Enable synchronous logging
`S1(config-line)# exec-timeout 10` | Automatically disconnect users after idle for _**10**_ minutes
`S1(config-line)# exit` |
`S1(config)# line vty 0 15` | Enter configuration mode for VTY lines 0 - 15
`S1(config-line)# password cisco` | Set the VTY password to _**cisco**_
`S1(config-line)# login` | Configure the VTY lines to require a password at Telnet/SSH login
`S1(config-line)# logging synchronous` | Enable synchronous logging
`S1(config-line)# exec-timeout 10` | Automatically disconnect users after idle for _**10**_ minutes
`S1(config-line)# exit` | Return to privileged EXEC mode
|
_**Configure SSH access on switch**_ |
`S1(config)# ip domain-name CCNA-Lab.com` | Create domain name _**ccna-lab.com**_
`S1(config)# username admin privilege 15 secret sshadmin` | Create a local user database entry of _**admin**_ with level _**15**_ (admin) privilege and secret _**sshadmin**_
`S1(config)# line vty 0 15` |
`S1(config-line)# transport input ssh` | Configure transport input for VTY lines to allow SSH connections only
`S1(config-line)# login local` | Use local user database for authentication
`S1(config-line)# exit` |
`S1(config)# crypto key generate rsa modulus 1024` | Generate _**RSA**_ key using mod _**1024**_
`S1(config)# ip ssh time-out 75` | Set idle time-out to _**75**_ seconds
`S1(config)# ip ssh authentication-retries 2` | Sets number of retries to _**2**_
|
_**Configure port security settings**_ |
`S1(config)# interface f0/5` |
`S1(config-if)# shutdown` |
`S1(config-if)# switchport port-security` | Enable port security on _**f0/5**_
`S1(config-if)# switchport port-security mac-address aaaa.bbbb.cccc` | Assign static entry for MAC address of _**aaaa.bbbb.cccc**_
`S1(config-if)# switchport port-security mac-address sticky` | Add learned MAC addresses to running-config
`S1(config-if)# no shutdown` |
|
_**Verify and save configuration**_ |
`S1# show run` | display entire running configuration
`Switch# show interface f0/6` | Display configuration of interface _**f0/6**_
`Switch# show interface vlan 666` | Display configuration of SVI on _**VLAN 666**_
`Switch# show ip interface vlan 666` | Display IP configuration of _**VLAN 666**_
`S1# show ip ssh` | Display SSH configuration
`S1# copy running-config startup-config` | save running-config in RAM to startup-config in NVRAM

Messing with MAC tables |
--- | --- |
`S1# show mac address-table ?` | Display currently known MAC addresses
`S1# clear mac address-table ?` | Remove existing MAC addresses
`S1(config)# mac address-table static 0050.56BE.6C89 vlan 666 interface f0/6` | Create static mapping of MAC address _**0050.56BE.6C89**_ to _**VLAN 666**_ on _**f0/6**_



CONFIGURE THE DEVICE | Router
--- | ---
_**Configure basic router settings**_ |
`Router> enable` | Enters privileged EXEC mode
`Router# config terminal` | Enters global config mode
`Router(config)# hostname R1` | Assign hostname _**R1**_ to device
`R1(config)# no ip domain-lookup` | Disable automatic domain lookup
`R1(config)# service password-encryption` | Encrypt passwords in the config file
`R1(config)# security passwords min-length 5` | Ensure that all configured passwords are a minimum of a specified length of _**5**_
`R1(config)# login block-for 120 attempts 3 within 60` | Block login attempts for _**120**_ seconds if there are _**3**_ failed login attempts within _**60**_ seconds
`R1(config)# enable secret class` | Set the privileged EXEC mode secret to _**class**_
`R1(config)# banner motd #This is a MOTD banner#` | Set MOTD Banner to _**This is a MOTD banner**_`
|
_**Configure lines**_ |
`R1(config)# line console 0` | Enter configuration mode for console line 0
`R1(config-line)# password cisco` | Set the console password to _**cisco**_
`R1(config-line)# login` | Configure the console line to require a password at user EXEC mode login
`R1(config-line)# logging synchronous` | Enable synchronous logging
`R1(config-line)# exec-timeout 10` | Automatically disconnect users after idle for _**10**_ minutes
`R1(config-line)# exit` |
`R1(config)# line vty 0 4` | Enter configuration mode for VTY lines 0 - 4
`R1(config-line)# password cisco` | Set the VTY password to _**cisco**_
`R1(config-line)# login` | Configure the VTY lines to require a password at Telnet/SSH login
`R1(config-line)# logging synchronous` | Enable synchronous logging
`R1(config-line)# exec-timeout 10` | Automatically disconnect users after idle for _**10**_ minutes
`R1(config-line)# exit` |
|
_**Configure Interfaces**_ |
`R1(config)# interface g0/1` | Enter config mode for interface _**g0/1**_
`R1(config-if)# description interface to S1` | Describe the interface as _**interface to S1**_
`R1(config-if)# ip address 192.168.1.1 255.255.255.0` | Assign IPv4 address _**192.168.1.1/24**_ to the interface
`R1(config-if)# ipv6 address 2001:DB8:ACAD::1/64` | Assign IPv6 address _**2001:DB8:ACAD::1/64**_ to the interface
`R1(config-if)# no shutdown` | Set interface administratively up
`R1(config-if)# exit` |
|
_**Configure RIP**_ |
`R1(config)# router rip `| Enable RIP protocol on the router
`R1(config)# no router rip` | Disable the RIP protocol on the router
`R1(config-router)# network 123.456.12.456` | Enable RIP for the specified network 123.456.123.456
`R1(config-router)# version 2`| Enable RIP version 2
`R1(config-router)# no auto-summary` | Disable autosummary
`R1(config-router)# passive-interface g0/0`| Configure interface g0/0 to stop routing updates from transmitting updates, but still be included in them
`R1(config-router)# default-information originate` | Configure R1 to originate default information to share with other routers using RIP
|
_**Configure RIPng**_
`R1(config)# ipv6 unicast-routing` |
`R1(config)# int g0/0`|
`R1(config-if)# ipv6 rip RIP-AS enable`| Configure interface g0/0 for RIPng
|
_**Enable SSH login**_ |
`R1(config)#ip domain-name example.com` | Configure the IP domain name of the network
`R1(config)#crypto key generate rsa general-keys modulus 1024` | Generate SSH secret key modulus 1024
`R1(config)#username Student privilege 15 secret cisco` | Create a local database username entry with root privilege
`R1(config)#line vty 0 4` | Enable VTY line configuration mode
`R1(config-line)#login local` | Enable password checking at login
`R1(config-line)#transport input ssh` | Disable non-SSH access to line vty
`R1(config-line)#exit` | Return to privileged EXEC mode





VERIFY THE CONFIGURATION OF THE DEVICE | Assorted
--- | ---
`Router1#show ip route` | Displays the contents of the IPv4 routing table stored in RAM
`Router1#show arp` | Shows ARP table
`Router1#show mac address-table` | shows MAC table
`Router1#show ip interface` | Displays the IPv4 statistics for all interfaces on a router
`Router1#show ip interface brief` | Displays all interfaces, their IPv4 address, and their current status
`Router1#show interfaces` | Displays statistics for all interfaces on the device
`Router1#ping 123.456.789.10` | Ping the desired IPv4 address
`Router1#show file systems` | Lists all of the available file systems
`Router1#show protocols` | Displays status and interfaces for desired protocol
`Router1#show version` | Displays system information
`Router1#show ip protocols` | Displays current IP protocols
`Router1#show cdp neighbors (detail)` | Displays detailed information about neighboring devices discovered using Cisco Discovery Protocol (CDP)
`Router1#no cdp run` | Disable CDP globally
`Router1(config-if)#no cdp enable` | Disable CDP on an interface
