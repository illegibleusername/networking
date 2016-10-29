[IPv4 Packet Header](https://en.wikipedia.org/wiki/IPv4#Packet_structure) | 20-40 octets(128-256 bits) |   |   |   |
----------- | --- | --- | --- | --- |
Version | IHL | DSCP | ECN | Total length |
Identification | Flags | Fragment Offset | |
Time to Live | Protocol | Header Checksum | | |
Source Address | | | | |
Destination Address | | | | |
Options | | | | |

Field | Description
----- | -----------
Version | Always set to 0100 (4 bits)
Internet Header Length | Specifies the size of the header (4 bits)
DSCP | [DSCP](https://en.wikipedia.org/wiki/Differentiated_services) value for [QoS](https://en.wikipedia.org/wiki/Quality_of_service) (6 bits)
ECN | [Allows end-to-end notification of network congestion without dropping packets](https://en.wikipedia.org/wiki/Explicit_Congestion_Notification) (2 bits)
Total Length | Defines the entire packet size, including header and data, in bytes. The minimum-length packet is 20 bytes and the maximum is 65,535 bytes (16 bits)
Identification | Primarily used for uniquely identifying the group of fragments of a single [IP datagram](https://en.wikipedia.org/wiki/Datagram#Internet_Protocol) (16 bits)
Flags | Used to control or identify fragments: bit 0 - Reserved; must be zero; bit 1 - Don't Fragment (DF); bit 2 - More Fragments (MF) (3 bits)
Fragment Offset | Specifies the offset of a particular fragment relative to the beginning of the original unfragmented IP datagram (13 bits)
TTL | [Time-to-Live](https://en.wikipedia.org/wiki/Time_to_live) helps prevent datagrams from persisting on an internet (8 bits)
Protocol | Defines the [protocol](https://en.wikipedia.org/wiki/List_of_IP_protocol_numbers) used in the data portion (8 bits)
Header Checksum | Used for [error-checking](https://en.wikipedia.org/wiki/IPv4_header_checksum) of the header (16 bits)
Source Address | Source IPv4 address (32 bits)
Destination Address | Destination IP address (32 bits)
Options | Not often used



[IPv6 Packet Header](https://en.wikipedia.org/wiki/IPv6_packet) | 40 octets/320 bits | Payload < 64KB (jumbo < 4GB) |
----------- | --- | --- |
Version | Traffic Class | Flow Label |
Payload Length | Next Header | Hop Limit |
Source IP Address | | |
Destination IP Address | | |

Field | Description
----- | -----------
Version | Always set to 0110 (4 bits)
Traffic Class | [DSCP](https://en.wikipedia.org/wiki/Differentiated_services) value for [QoS](https://en.wikipedia.org/wiki/Quality_of_service) (8 bits)
Flow Label | Identifies unique flows (optional) (20 bits)
Payload Length | length of payload in bytes (16 bits)
Next Header | Header or [protocol](https://en.wikipedia.org/wiki/List_of_IP_protocol_numbers) contained in the packet (8 bits)
Hop Limit | [Time-to-Live](https://en.wikipedia.org/wiki/Time_to_live) helps prevent datagrams from persisting on an internet (8 bits)
Source Address | Source IPv6 address (128 bits)
Destination Address | Destination IPv6 address (128 bits)
