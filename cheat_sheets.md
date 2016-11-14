### Routing Table (R 172.16.4.0/28 \[120/2\] via 209.165.200.226, 00:00:12, Serial0/0/0)
R | 172.16.4.0/28 | \[120 | /2\] | via 209.165.200.226, | 00:00:12, | Serial0/0/0
:---: | :---: | :---: | :---: | :---: | :---: | :---:
Route Source | Destination Network | Administrative Distance | Metric | Next-hop | Route Timestamp | Outgoing Interface
Identifies how the route was learned (C = connected, L = local, S = static, D = EIGRP, O = OSPF) | Identifies the address of the remote network | Identifies the trustworthiness of the route source | Identifies the value assigned to reach the remote network. Lower values indicate preferred routes | Identifies the IPv4 address of the next router to forward the packet to | Identifies from when the route was last heard | Identifies the exit interface to use to forward a packet toward the final destination


### Switch Boot Sequence
1. POST tests the CPU, DRAM, and the flash file system
2. Loads the boot loader from ROM
3. Boot loader initializes CPU registers
4. Boot loader initializes the flash file system
5. Boot loader loads an IOS image into RAM
6.  IOS initializes interfaces using the IOS commands found in startup-config in NVRAM


### Router Memory ###
Memory | Volatility | Stores
--- | --- | ---
RAM | Volatile | Running IOS, config, IP routing/ARP tables, packet buffer
ROM | Non-volatile | Bootup instructions, basic diagnostic software, limited IOS
NVRAM | Non-volatile | Startup-config
Flash | Non-volatile | IOS, system files
