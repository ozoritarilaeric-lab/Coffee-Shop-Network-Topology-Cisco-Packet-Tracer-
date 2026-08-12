This project presents a small business network designed in Cisco Packet Tracer to simulate a realistic coffee shop environment. The network topology includes wired office devices, a Point of Sale (POS) system, office and receipt printers, and a guest Wi Fi network, all connected through a central switch and a router that provides Internet access via an ISP cloud. The project demonstrates basic routing, switching, wireless networking, and small-business network design concepts in a practical simulation environment.

# Objectives
The goal of this project was to design and simulate a small coffee shop network that provides:

-Reliable Internet connectivity

-Secure communication for business devices

-Wireless Internet access for guests

-Centralized network management through a switch and router

In this project, I built the complete network topology in Cisco Packet Tracer using the following steps:

# Network Design

-Added an ISP Cloud to represent Internet connectivity.

-Configured a Cisco 2911 router as the gateway between the local network and the ISP.

-Added a Cisco 2960-24TT switch as the central switching device.

# Wired Devices

-Manager PC

-POS Terminal

-Office Printer

-Receipt Printer

# Wireless Network

-Added an Access Point for guest Wi-Fi.

-Connected two guest laptops wirelessly to the access point.

# Connectivity Verification

-Ensured all interfaces were active (green status indicators).

-Verified that wired and wireless devices were connected through the switch and router.

-Simulated Internet access through the ISP cloud.

# Outcome

-The final network topology successfully achieved the project objectives.

# Device Configuration

# Router Configuration (Cisco 2911)

enable

configure terminal

hostname CoffeeShop-RTR

interface gigabitEthernet0/0

ip address dhcp 

no shutdown

interface gigabitEthernet0/1 

ip address 192.168.10.1 255.255.255.0 

no shutdown

ip dhcp pool STAFF 

network 192.168.10.0 255.255.255.0 

default-router 192.168.10.1

dns-server 8.8.8.8

end 

write memory

# Switch Configuration (Cisco 2960)

enable 

configure terminal

hostname Main-Switch 

interface range fa0/2 - 7

switchport mode access 

spanning-tree portfast

interface fa0/11 

switchport mode access 

spanning-tree portfast

interface gigabitEthernet0/1

switchport mode access

end 

write memory

# Successful Results

-All wired devices were connected to the switch.

-Guest laptops connected successfully to the wireless access point.

-The router provided a path to the ISP for Internet access.

-The topology demonstrated both wired and wireless communication within a single network.

-The design is scalable and can be extended with VLANs, DHCP, NAT, and security policies.

# Skills Gained

-Basic network design

-Router and switch interconnection

-Wireless network deployment

-Small-business network architecture

-Packet Tracer topology creation and troubleshooting

# Devices Used                                                                             

-Cloud-PT	                                                                               

-Cisco 2911 Router	                                                                      

-Cisco 2960-24TT            

-AccessPoint-PT	           

-Manager PC	               

-POS Terminal	             

-Office Printer	           

-Receipt Printer	          

-Guest Laptops

# Network Connections

-Router Gig0/0 → ISP Cloud

-Router Gig0/1 → Switch

-Switch Fa0/2 → Office Printer

-Switch Fa0/3 → Manager PC

-Switch Fa0/6 → POS Terminal

-Switch Fa0/7 → Receipt Printer

-Switch Fa0/11 → Guest Wi-Fi Access Point

Guest laptops connect wirelessly to the access point.

# Suggested IP Addressing
Network	  →  → → Subnet       →  →  →  →       Gateway    

Staff LAN   →  192.168.10.0/24	→ 192.168.10.1

Guest Wi-Fi	→ 192.168.20.0/24	→ 192.168.20.1

# Example VLAN Design

VLAN   →  → Purpose

VLAN 10 →	Staff devices

VLAN 20 →	POS devices

VLAN 30 →	Guest Wi‑Fi

This improves security by isolating guest users from business systems.

# Features Demonstrated
-Router-to-switch topology

-Wired LAN connectivity

-Wireless guest network

-Internet access simulation

-POS device integration

-Printer connectivity

-Basic network segmentation concepts

# Security Recommendations

-Use WPA2/WPA3 on the guest Wi‑Fi.

-Apply ACLs to prevent guest access to internal VLANs.

-Disable unused switch ports.

-Enable port security on access ports.

-Use strong router administrative passwords.

-Configure DHCP separately for staff and guest networks.

# What This Topology Demonstrates

This Packet Tracer project demonstrates several networking concepts:

-Small-business network design

-Router-to-switch architecture

-Wired and wireless integration

-Internet edge connectivity

-POS and printer connectivity

-Guest network deployment

-Basic network segmentation

# Conclusion
This project successfully designed and simulated a small business coffee shop network using Cisco Packet Tracer. The topology integrated a Cisco router, a switch, wired office devices, a POS terminal, printers, and a guest Wi-Fi network connected to an ISP. The simulation demonstrated how routing, switching, and wireless networking work together in a realistic small-business environment.
The project achieved its main objective of providing connectivity for both business operations and guest users while maintaining a simple and scalable network structure. Through this implementation, practical skills in network design, device interconnection, IP addressing, wireless configuration, and connectivity verification were developed.
Overall, the project provides a solid foundation for understanding small-business network infrastructure and can be further enhanced with VLANs, DHCP, NAT, ACLs, and additional security features for more advanced networking practice.


# License
This project is intended for educational and learning purposes only.
				
	
