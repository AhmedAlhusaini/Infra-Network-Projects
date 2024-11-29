# 🌐 Melbourne Health Services Network Design and Implementation

## 📋 Project Overview

**Melbourne Health Services** is a leading health provider in Australia, operating across two locations in Melbourne. The institution aims to transition from third-party IT services to an in-house, secure, and cost-effective network infrastructure. This project involves designing and implementing a robust network infrastructure that adheres to the principles of **Confidentiality, Integrity, and Availability (CIA)**.

---

## 🏥 Locations and Departments

### **1. Headquarters (HQ)**  
Located 20 km from the branch, the HQ houses the following departments:
- 🩺 **Medical Lead Operation & Consultancy Services (MLOCS)**  
- 🚑 **Medical Emergency and Reporting (MER)**  
- 🗂 **Medical Records Management (MRM)**  
- 💻 **Information Technology (IT)**  
- ☎️ **Customer Service (CS)**  
- 🛋 **Guest/Waiting Area (GWA)**  

### **2. Branch Hospital**  
The branch complements the HQ and includes:  
- 👩‍⚕️ **Nurses & Surgery Operations (NSO)**  
- 🧪 **Hospital Labs (HL)**  
- 👔 **Human Resources (HR)**  
- 📈 **Marketing (MK)**  
- 💰 **Finance (FIN)**  
- 🛋 **Guest/Waiting Area (GWA)**  

---

## 🛠 Project Objectives

1. **Design and implement** a hierarchical network model with redundancy.
2. **Implement VLANs** to segment departments for security and efficiency.
3. Enable **secure communication** using Access Control Lists (ACLs) and a site-to-site **IPSec VPN**.
4. Configure **dynamic IP allocation** using dedicated DHCP servers.
5. **Ensure scalability, security, and cost-effectiveness** of the network.

---

## ⚙️ Technologies Implemented

- 🔧 **Cisco Packet Tracer** for simulation.
- 📶 **Wireless LAN** for each department.
- 🖧 **VLANs** for departmental segmentation.
- 🔒 **Access Control Lists (ACLs)** for traffic filtering.
- 🔄 **OSPF** as the routing protocol.
- 📤 **NAT Overload (PAT)** for outbound traffic.
- 🔑 **SSH** for secure device access.
- 🔑 **Port Security** to prevent unauthorized access.
- 🔗 **Site-to-Site VPN** for secure branch-HQ communication.
- 🖥 **Static and Dynamic IP Addressing**.

---

## 🗺 Network Design Requirements

### **1. Topology**
- A hierarchical model with core routers at HQ and the branch.
- Each router connected to two subscribed ISPs.
- Separate network segments for each department.

### **2. Server-Side Configuration**
- 🖥 **DHCP Server** for dynamic IP allocation.
- 🌐 **DNS, Web, and Email Servers** configured statically.

### **3. IP Addressing**
- Base Network: `192.168.100.0/24`
- Subnetting used to allocate IPs to departments based on user count:
  - HQ: 60 users per department.
  - Branch: 30 users per department.

### **4. Security Policies**
- Extended **ACLs** for user access control.
- **IPSec VPN** for encrypted communication between sites.
- **Port Security**: One device per port (sticky method).

### **5. Protocols and Features**
- **OSPF**: Dynamic routing.
- **PAT**: Use outbound router interface for public IP sharing.
- **Default Static Routing**: For unmatched traffic forwarding.

---

## 🛑 Configuration Steps

1. **Basic Device Setup**:
   - Hostnames, console passwords, and banners.
   - Disable IP domain lookup.
2. **VLAN Creation**:
   - Assign VLANs to departments and configure inter-VLAN routing.
3. **Subnetting**:
   - Allocate IPs to departments.
4. **Router Configuration**:
   - Configure OSPF, NAT, and static routes.
   - Secure communication with SSH and IPSec VPN.
5. **Switch Configuration**:
   - Enable port security and inter-VLAN routing.
6. **Server Configuration**:
   - Static IPs for servers and DHCP setup for devices.
7. **Testing and Validation**:
   - Verify connectivity and security policies.

---

## 🚀 Expected Outcomes

- ✅ Seamless communication between HQ and the branch.
- ✅ Secure data transmission with encryption.
- ✅ Efficient network performance and traffic management.
- ✅ Adherence to the **CIA security model**.

---

## 📂 Project Files

- **`Packet Tracer Topology File (.pkt)`**: Complete network design.
- **`Subnetting Plan (.xlsx)`**: Detailed IP allocation.
- **`Configuration Scripts (.txt)`**: Router and switch configurations.

---

## 📈 Future Enhancements

- Implementation of monitoring tools like SNMP.
- Integration with cloud services for disaster recovery.
- Advanced security measures (e.g., intrusion detection systems).

