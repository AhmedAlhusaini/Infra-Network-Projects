# 🎉 Jubilee Financial Services Ltd (JFSL) 🎉

Jubilee Financial Services Ltd (JFSL) is a well-established finance service provider in Kenya, offering online finance solutions and services to its clients. The company operates in the country’s capital city, Nairobi, and is hosted within an eleven-story building. The company primarily operates from the seventh to the eighth floors, with at least two departments on each floor.

## 🏢 Departments and Devices

### Seventh Floor
- **Human Resource (HR)**
- **Customer Service (CS)**
- **Marketing (MK)**

Each department has:
- At least 40 user devices 💻
- 40 IP phones 📞
- One WIFI-AP 📶

### Eighth Floor
- **Legal Management (LM)**
- **Information Technology (IT)**

Each department has:
- At least 20 user devices 💻
- 20 IP phones 📞
- One WIFI-AP 📶

**Note**: Each user can have an associated VoIP phone (but not a must).

## 🌐 Network Infrastructure

The network infrastructure is currently managed by a third-party firm called Infinitive IT Systems Kenya. The senior management has decided to own its network infrastructure, including Local Area Network (LAN), Wide Area Network (WAN), and an external Server-Side location connected via appropriate WAN technology, prioritizing secure communication between the HQ network and the external site.

### 🖥️ Server-Side Site

The server-side site will host:
- DHCP
- DNS
- WEB
- EMAIL servers

### 📡 ISPs

The company intends to subscribe to two ISPs (Safaricom and JTL ISPs) to provide redundancy and load-balancing in terms of internet provisions.

### 🛠️ Network Equipment

The company has purchased:
- Two Cisco Catalyst 2911 routers (one for HQ and one for server-side)
- One gateway router Catalyst 2811 router (for HQ VoIP)
- Two multilayer switches (both for HQ)
- Six access switches for the departments

## 🔒 Network Design Requirements

Due to security requirements, all five departments will be on a separate network segment within the same local area network. None of the servers is located within the local area network but will be hosted from an external site accessible via a WAN connection. The network security policy will comprehensively dictate user access to the external site using Access Control LIST (ACL).

### 📐 Design and Implementation

You have been hired as a network security engineer to design the network for Jubilee Financial Services Ltd (JFSL) according to the requirements set by the senior management. You will consult an appropriate robust network design model to meet the design requirements. You will also implement Access Control Lists and Virtual Private Networks to enable secure communication considering security and network performance factors paramount to safeguard the Confidentiality, Integrity, and Availability of data and communication.

### Key Requirements

- **High Performance** 🚀
- **Redundancy** 🔄
- **Scalability** 📈
- **Availability** 🕒

### 🧩 IP Addressing

- **Data**: 192.168.20.0/24
- **Voice**: 10.10.10.0/24
- **Public Addresses**: 190.200.100.0

### 🛠️ Design Tool

- **Cisco Packet Tracer**: Use Cisco Packet Tracer to design and implement the network solution.

### 🏗️ Hierarchical Design

- Use a hierarchical model providing redundancy at every layer.

### 🌐 ISPs

- The network is expected to connect to at least two ISPs to provide redundancy, and each router is connected to the two ISPs.

### 📶 WIFI

- Each department is required to have a wireless network for the users.

### 📞 VoIP

- Each department should have IP phones, and users in the department should be able to call each other.

### 🖥️ VLAN

- Each department should be in a different VLAN and a different subnetwork. The voice VLAN ID number will remain at VID 120 for the entire network.

### 🧮 Subnetting

- Carry out subnetting to allocate the correct number of IP addresses to each department.

### 🔧 Basic Settings

- Configure basic device settings such as hostnames, console passwords, enable passwords, banner messages, encrypt all passwords, and disable IP domain lookup.

### 🔄 Inter-VLAN Routing

- Devices in all the departments are required to communicate with each other with the respective multilayer switch configured for inter-VLAN routing.

### 🏢 Core Switches

- The Multilayer switches are expected to carry out both routing and switching functionalities and thus will be assigned IP addresses.

### 🖥️ DHCP Server

- All devices in the network (except IP phones) are expected to obtain an IP address dynamically from the dedicated DHCP servers located at the server-side site.

### 📞 Cisco 2811 Router

- Ensure to have a router that can support telephony service i.e., Cisco Catalyst 2811 (the VoIP router should be connected to any of the L3-switches at HQ).

### 📝 Static Addressing

- Devices in the server room are to be allocated IP addresses statically.

### 📞 Telephony Service

- Configure VoIP on the voice gateway router and allocate dial numbers in format (4..).

### 📡 Routing Protocol

- Use OSPF as the routing protocol to advertise routes both on the routers and multilayer switches.

### 🔒 Switchport Security

- Configure port security for the server site department switch to allow only one device to connect to a switch port, and use the sticky method to obtain mac-address and violation mode shutdown.

### 🔐 SSH

- Configure SSH in all the routers and layer three switches for remote login.

### 🔒 Standard ACL for SSH

- Configure a simple standard ACL on the line VTY to allow only the ICT department to carry out all remote administrative tasks using SSH.

### 🔄 NAT + ACL

- Configure PAT to use the respective outbound router interface IPv4 address, and implement the necessary ACL rule.

### 🔒 IPsec VPN + ACL

- Configure site-to-site IPsec VPN between the HQ router and the Server-side router, and implement the necessary ACL rule.

### ✅ Final

- Test Communication, ensure everything configured is working as expected.

## 🛠️ Technologies Implemented

- Creating a network topology using Cisco Packet Tracer.
- Hierarchical Network Design.
- Connecting Networking devices with Correct cabling.
- Configuring Basic device settings.
- Creating VLANs and assigning ports VLAN numbers.
- Creating both data and voice VLANs and assigning ports VLAN numbers.
- Subnetting and IP Addressing.
- Configuring Inter-VLAN Routing both on the Switches (SVI) and Routers (router-on-a-stick).
- Configuring Dedicated DHCP Server device for Data to provide dynamic IP allocation.
- Configuring Routers as DHCP server for Voice to provide IP Phones dynamic IP allocation.
- Configuring SSH for secure Remote access.
- Configuring OSPF as the routing protocol.
- Configuring Standard ACL for VTY interfaces to restrict remote Access using SSH.
- Configuring Port Address Translations or PAT for NAT.
- Configuring Standard ACL for PAT.
- Configuring VoIP or Telephony service configuration in all routers.
- Configuring site-to-site IPsec VPN on the gateway routers.
- Configuring Standard ACL for site-to-site IPsec VPN.
- Host Device Configurations.
- Test and Verifying Network Communication.

