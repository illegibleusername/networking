IPv4 Packet |     |     |     |    |
----------- | --- | --- | --- | --- |
Version (4 bits) | IHL (4 bits) | DSCP (6 bits) | ECN (2 bits) | Total length (2 bytes) |
Identification (2 bytes) | Flags (3 bits) | Fragment Offset (13 bits) | |
Time to Live (1 byte) | Protocol (1 byte) | Header Checksum (2 bytes) | | |
Source IP Address (4 bytes) | | | | |
Destination IP Address (4 bytes) | | | | |
Options if IHL > 5 (0 - 16 bytes) | | | | |


IPv6 Packet |     |     |
----------- | --- | --- |
Version (4 bits) | Traffic Class (1 byte) | Flow Label (20 bits) |
Payload Length (2 bytes) | Next Header (1 byte) | Hop Limit (1 byte) |
Source IP Address (16 bytes) | | |
Destination IP Address (16 bytes) | | |
