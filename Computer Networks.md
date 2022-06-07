# NETWORK
---
- group of computers connected
- NAT - used due to scarcity of ipv4 - no privacy
- MAC - Media Access Control

##### Types
- LAN - Local Area Network
- PAN - Personal Area Network
- MAN - Metropolitan Area Network
- WAN - Wide Area Network

- ISP to router - WAN cable
- router is connected to a switch
- devices are connected to a switch

#### IP Address
- every device connected to internet has an ip address
- 0.0.0.0 to 255.255.255.255
- port numbers are mapped to mac address
- some ip addresses are reserved

#### Protocols
- ICMP - Internet Control Message Protocol - ping
- ARP - Address Resolution Protocol - allows a device to associate a MAC address with its IP address on the network
- DHCP - Dynamic Host Configuration Protocol 
- DNS - Domain Name Service
- IPv4 - Internet Protocol - 32 bits
- IPv6 - Internet Protocol - 64 bits

#### Swtiches and Routers
- Switches are dedicated devices within a network that are designed to aggregate multiple other devices using ethernet 
- Switches can connect a large number of devices by having ports of 4, 8, 16, 24, 32, and 64 for devices to plug into

 - Routers connect networks and passes data between them
 - It involves creating a path between networks so that this data can be successfully delivered

# TOPOLOGIES
----
#### Star
- all devices are individually connected via a central networking device
- more expensive
- commonly found due to reliability and scalability

#### BUS
- single connection called backbone cable
- prone to becoming slowed and bottlenecked if the devices connected continuously send requests
- difficult to troubleshoot
- cost efficient

#### RING
- token topology
- devices are connected directly to each other to form a loop
- little cabling required and less dependence on dedicated hardware
- one direction of data traversal
- easy to troubleshoot, but not efficient 

# OSI Model
----
- Opem Systems Interconnect Model
- 7 layers -
					Application - to allow access to network resources
					Presentation - to translate, encrypt and compress data
					Session - to establish, manage and terminate sessions
					Transport - to provide reliable process to process message delivery and error delivery
					Network  - to move packets from source to destination
					Data Link - to organize bits into frames
					Physical - to transmit bits over a medium

- Each layer will have its own protocols

- Application layer - HTTP, HTTPS, FTP

- Transport layer - Heart of OSI
							 - Has two protocols
							 - UDP - User Datagram Protocol
										- non reliable, no return
										- used in streaming, games
										- if data is lost, it will not try to get it back
							 - TCP - Transmission Control Protocol
									    - reliable, returns a message
									    - used to download

- Network layer - OSPF - Open Shortest Path First
										- routing algorithm

- Routers manage software layer, switches manage hardware layer
- OSI model is no longer in use


- TCP - 3 way handshake 
	Initialize connection:
	1. Sender -> Receiver - SYN packet
	2. Receiver -> Sender - SYNACK packet
	3. Sender -> Receiver - ACK packet

	End connection:
	1. Sender -> Receiver - FIN packet
	2. Receiver -> Sender - ACK packet


# TCP/IP MODEL
---
- 4 layers - Application - 7th,6th,5th layers of OSI
				 - Transport - 4th layer of OSI
				 - Network - 3rd layer of OSI
				 - Network Interface - 2nd and 1st layer of OSI

# ATTACKS ON EACH LAYER
---
### DOS
- Denial of Service
- sending multiple syn packets without sending ack packets
- server waits for acknowledgement
- all connections are half open, others cannot send syn packet
- prevented by allowing only few connections per ip address

### DDOS
- Distributed Denial of Service
- DOS by a botnet
- multiple syn packets by multiple ip addresses
- attack on transport layer

### Man in the Middle
- spoofing an ip address where two systems have made a 3 way handshake