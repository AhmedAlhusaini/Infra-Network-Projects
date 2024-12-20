# Turtle Consultancy Limited Network Project 🐢🌐

Welcome to the Turtle Consultancy Limited Network Project repository! This project showcases the design and implementation of a VoIP network for a newly acquired branch of Turtle Consultancy Limited, a company specialized in delivering IT infrastructure solutions to medium-sized organizations worldwide.

## Project Overview 📋

With the expansion of the company, a newly acquired branch needs a network. As a recently hired Network Engineer, you are tasked with designing and implementing a VoIP network based on the requirements and specifications outlined by your manager. The network consists of four servers (DHCP, EMAIL, DNS, HTTP) located at the server-side site and is fully configured for operations. All desktops have an associated telephone set, with each PC connecting directly to a phone.

## Network Requirements and Specifications 🛠️

### IP Addressing
- **Data:** 192.168.100.0/24
- **Voice:** 172.16.100.0/24
- **Between Routers:** 10.10.10.0/24

### Devices and Connections
- **Routers:** Each department has a VoIP-enabled router (Cisco 2811) with server-side LAN attached to the ICT department router.
- **Switches:** Each department has an access layer switch (Cisco 2960).
- **Connections:** Serial connections between routers, straight-through cables between router to switch, switch to hosts, and phones to PCs.

### Subnets and VLANs
- **Subnets:** Each department accesses two subnetworks (data and voice).
- **VLANs:** Each department will be in two VLANs (data and voice). All IP phones in the network should be in VLAN 100.

### Basic Settings
- Configure hostnames, console passwords, enable passwords, banner messages, encrypt all passwords, and disable IP domain lookup.

### DHCP Server
- **Voice (VoIP):** Use the respective router as the DHCP server.
- **Data:** Use the DHCP server device at the server-side site.

### Inter-VLAN Routing
- Use router-on-a-stick to enable inter-VLAN routing on the network. Create subinterfaces for both data and voice VLANs.

### IP Addressing
- All devices in the network are expected to obtain an IP address dynamically from the respective DHCP servers. Devices in the server room are to be allocated IP addresses statically.

### Routing Protocol
- Use OSPF as the routing protocol to advertise routes on the routers.

### Remote Access
- Configure SSH on all routers for remote login.

### Telephony Service
- Configure VoIP on the routers and allocate dial numbers in this format for the departments: Finance (1..), HR (2..), Sales (3..), and ICT (4..), where 1.. can be 101 to 199, and so on.
- Configure dial-peering on the routers to allow IP phones from different routers to communicate.

### Finalize
- Test communication and ensure everything configured is working as expected.

## Technologies Implemented 💡
- Creating a network topology using Cisco Packet Tracer.
- Hierarchical Network Design.
- Connecting networking devices with correct cabling.
- Configuring basic device settings.
- Creating VLANs and assigning ports VLAN numbers.
- Creating both data and voice VLANs and assigning ports VLAN numbers.
- Subnetting and IP Addressing.
- Configuring Inter-VLAN Routing on the Routers (router-on-a-stick).
- Configuring a dedicated DHCP Server device for Data to provide dynamic IP allocation.
- Configuring Routers as DHCP server for Voice to provide IP Phones dynamic IP allocation.
- Configuring SSH for secure remote access.
- Configuring OSPF as the routing protocol.
- Configuring VoIP or Telephony service configuration in all routers.
- Configuring Routing for VoIP or Dial peering configuration in all routers.
- Host Device Configurations.
- Testing and verifying network communication.

## Conclusion 🎯
This project demonstrates the comprehensive design and implementation of a scalable and available network infrastructure for Turtle Consultancy Limited. By following the outlined specifications and utilizing the mentioned technologies, the network is designed to meet the demands of the business and technology challenges.

Feel free to explore the repository and reach out if you have any questions or suggestions. Happy networking! 🚀
