# CISCO COMMANDS

CONFIGURE THE DEVICE | Switch
-------------------- | ------
_**Verify the default switch configuration**_ |
`Switch> enable` | Enables privileged EXEC mode
`Switch# show running-config` | Display current running configuration from RAM
`Switch# show startup-config` | Display current default configuration from NVRAM
`Switch# show interface vlan1` | Display configuration of SVI on VLAN 1
`Switch# show ip interface vlan1` | Display IP configuration of SVI VLAN 1
`Switch# show version` | Display IOS version information
`Switch# show interface f0/6` | Display configuration of interface _f0/6_
`Switch# show vlan` | Display VLAN configuration
`Switch# show flash` | Display contents of flash drectory
`Switch# dir flash:` | Display contents of flash drectory
|
_**Configure basic switch settings**_ |
`Switch# configure terminal` | Enables global config mode
`Switch(config)# hostname S1` | Assign hostname _S1_ to device
`S1(config)# service password-encryption` | Encrypt passwords in the config file
`S1(config)#security passwords min-length 5` | Ensure that all configured passwords are a minimum of a specified length (5)
`S1(config)# login block-for 120 attempts 3 within 60` | Block login attempts for 120 seconds if there are three failed login attempts within 60 seconds
`S1(config)# enable secret class` | Set the privileged EXEC mode secret to _class_
`S1(config)#no ip domain-lookup` | Disable automatic domain lookup
`S1(config)#banner motd #This is a MOTD banner#` | Configure a MOTD Banner
|
_**Configure lines**_ |
`S1(config)#line console 0` | Enable configuration mode for console line 0
`S1(config-line)#password cisco` | Set the console password to cisco
`S1(config-line)#login` | Configure the console line to require a password at user EXEC mode login
`S1(config-line)#logging synchronous` | Enable logging synchronous
`S1(config-line)#exec-timeout 10` | Automatically disconnect users on a line after they have been idle for the duration of the exec timeout value
`S1(config-line)#line vty 0 15` | Enable configuration mode for VTY line 0-15
`S1(config-line)#password cisco` | Set the VTY password to cisco
`S1(config-line)#login` | Configure the VTY line to require a password at Telnet/SSH login
`S1(config-line)#logging synchronous` | Enable logging synchronous
`S1(config-line)#exec-timeout 10` | Automatically disconnect users on a line after they have been idle for the duration of the exec timeout value
`S1(config-line)#exit` | Return to privileged EXEC mode
|
_**Configure SVI management interface on VLAN 99**_ |
`S1(config)# vlan 99` | Create VLAN 99
`S1(config-vlan)# name vlan_name` | Configure name for VLAN 99
` S1(config-vlan)# exit` | Return to global config mode
`S1(config)#interface vlan 99` | Enter the interface config mode for VLAN 99 
`S1(config-if)#ip address 192.168.1.1 255.255.255.240` | Configure management interface IP address
`S1(config-if)#no shutdown` | Enable management interface
`S1(config-if)# switchport access vlan 99` | 
`S1(config-if)#exit` | Return to global config mode
`S1(config)#ip default-gateway 192.168.0.1` | Configure a default gateway for the device
`S1(config)#interface range f0/1 – 24,g0/1 - 2` | Enter interface range configuration mode
`S1(config-if-range)#switchport access vlan 99` | 


CONFIGURE THE DEVICE | Router
-------------------- | ------
_**Initial configuration and security settings**_ |
`Router>enable` | Enables privileged EXEC mode
`Router#config terminal` | Enables global EXEC mode
`Router(config)#hostname R1` | Assign a hostname to a device, in this case R1
`R1(config)#banner motd #This is a MOTD banner#` | Configure a MOTD Banner
`S1(config)#service password-encryption` | Encrypt passwords in the config file
`R1(config)#security passwords min-length` | Ensure that all configured passwords are a minimum of a specified length
`R1(config)# login block-for 120 attempts 3 within 60` | Block login attempts for 120 seconds if there are three failed login attempts within 60 seconds
`R1(config)#enable secret class` | Set the privileged EXEC mode secret password to class
`R1(config)#line console 0` | Enable console line configuration mode
`R1(config-line)#password cisco` | Set the console password to cisco
`R1(config-line)#login` | Configure the console line to require a password at user EXEC mode login
`R1(config-line)#logging synchronous` | Enable logging synchronous
`R1(config-line)#exec-timeout 10` | Automatically disconnect users on a line after they have been idle for the duration of the exec timeout value
`R1(config-line)#line vty 0 4` | Enable VTY line configuration mode
`R1(config-line)#password cisco` | Set the VTY password to cisco
`R1(config-line)#login` | Configure the VTY line to require a password at Telnet/SSH login
`R1(config-line)#logging synchronous` | Enable logging synchronous
`R1(config-line)#exec-timeout 10` | Automatically disconnect users on a line after they have been idle for the duration of the exec timeout value
`R1(config-line)#exit` | Return to privileged EXEC mode
_**Configure Interfaces**_ |
`R1(config)#interface S 0/0/0` | Configure Serial interface
`R1(config-if)#description Serial interface for R1` | Describe the interface as 'Serial interface for R1'
`R1(config-if)#ip address 192.168.1.17 255.255.255.240` | Assign an IPv4 address and subnet mask to the interface
`R1(config-if)#ipv6 address 2001:DB8:ACAD::1/64` | Assign an IPv6 address and subnet mask to the interface
`R1(config-if)#no shutdown` | Set the interface administratively up
`R1(config-if)#exit` | Return to privileged EXEC mode
_**Enable SSH login**_ |
`R1(config)#ip domain-name example.com` | Configure the IP domain name of the network
`R1(config)#crypto key generate rsa general-keys modulus 1024` | Generate SSH secret key modulus 1024
`R1(config)#username Student privilege 15 secret cisco` | Create a local database username entry with root privilege
`R1(config)#line vty 0 4` | Enable VTY line configuration mode
`R1(config-line)#login local` | Enable password checking at login
`R1(config-line)#transport input ssh` | Disable non-SSH access to line vty
`R1(config-line)#exit` | Return to privileged EXEC mode


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
`Router1#ping 123.456.789.10` | Ping the desired IPv4 address
`Router1#show file systems` | Lists all of the available file systems
`Router1#show protocols` | Displays status and interfaces for desired protocol
`Router1#show version` | Displays system information
`Router1#show cdp neighbors (detail)` | Displays detailed information about neighboring devices discovered using Cisco Discovery Protocol (CDP)
`Router1#no cdp run` | Disable CDP globally
`Router1(config-if)#no cdp enable` | Disable CDP on an interface
`S1#show vlan brief` | Display information about all VLANs
