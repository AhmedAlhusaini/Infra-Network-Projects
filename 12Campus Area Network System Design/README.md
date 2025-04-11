# 🛡️ Martin Luther King University Network Infrastructure Project

## 📚 Project Overview

Martin Luther King University (MLKU) is a distinguished educational institution comprising **two campuses** situated **100 miles apart** within the United States. The university hosts **30,000 users** and is expected to **double** its size by 2025, necessitating a **robust, scalable, and secure network infrastructure**.

## ⚠️ Project Disclaimer

This case study includes a specialized architecture for **ArcGIS Enterprise workload separation**:

- **HQ** serves as the **Production environment** with full redundancy
- **BR** serves as the **Staging environment** for testing and development
- Environments are physically and logically separated while maintaining:
  - Secure data synchronization channels
  - Isolated storage and processing resources
  - Independent VLANs and subnets
  - Controlled access policies

_This documentation represents a theoretical case study for educational purposes. All configurations were simulated using Cisco Packet Tracer. ArcGIS Enterprise workload separation is a conceptual design demonstrating environment isolation best practices._

_Documentation assistance provided by DeepSeek Chat AI._

## 👨‍💻 Engineer

- **Role:** Senior Network Security Engineer
- **Tools Used:** Cisco Packet Tracer
- **Status:** ✅ Completed and tested
- **Platform:** Hybrid (On-prem + Google Cloud)

---

## 🎯 Objectives

- Design a **hierarchical, scalable**, and **redundant network infrastructure**.
- Establish **secure communications** between campuses via **IPsec VPN**.
- Implement **VLAN segmentation**, **inter-VLAN routing**, and **DHCP**.
- Utilize **Cisco ASA Firewalls**, **HSRP**, and **ACLs** for security.
- Support **VoIP**, **WLAN**, and **Cloud services** via Google Cloud.
- Facilitate **remote management** via SSH restricted to specific admins.
- Ensure full **redundancy, load balancing**, and **failover capabilities**.

---

## 🧱 Network Architecture

### 🏛️ Campuses

- **Main Campus**: Core IT and server infrastructure (HQ - Production)
- **Branch Campus**: Connected via secure VPN tunnel (BR - Staging)

### 🎓 Faculties (Each Campus)

- Health and Sciences
- Business
- Engineering and Computing
- Art and Design

---

## 🧩 Technologies Implemented

| Component                | Description                                                            |
| ------------------------ | ---------------------------------------------------------------------- |
| 🔐 **Security**          | Cisco ASA 5500-X Firewalls, BPDU Guard, PortFast, Standard ACLs        |
| 🌐 **Routing**           | OSPF for dynamic routing across firewall, routers, and switches        |
| 🔄 **Redundancy**        | HSRP on core switches, dual DHCP servers, LACP (EtherChannel)          |
| 🛰️ **Remote Access**     | IPsec VPN between campuses                                             |
| 🧭 **VLANs**             | Segmentation for Management (10), LAN (20), WLAN (50), Blackhole (199) |
| 📞 **VoIP**              | IP Phones in every department                                          |
| 📡 **Wi-Fi**             | Centralized via Wireless LAN Controller (WLC) and LAPs                 |
| 📦 **Virtualization**    | Two physical servers running VMs (DNS, DHCP, WEB, FTP, SMTP, Email)    |
| 🧠 **Core Switches**     | Multilayer switching with inter-VLAN routing                           |
| 🖥️ **Cloud Integration** | Google Cloud Platform for remote access to university services         |
| 🌍 **ArcGIS Enterprise** | Separate environments for HQ (Production) and BR (Staging)             |

---

## 🗺️ IP Addressing Scheme

| Segment    | Main Campus (HQ) | Branch Campus (BR) |
| ---------- | ---------------- | ------------------ |
| LAN        | 10.10.0.0/16     | 10.11.0.0/16       |
| WLAN       | 192.168.10.0/24  | Shared             |
| Voice      | 172.16.0.0/16    | 172.17.0.0/16      |
| DMZ        | 10.20.20.0/27    | Centralized        |
| Public IPs | 105.100.50.0/30  | 205.200.100.0/30   |
| ArcGIS HQ  | 10.10.100.0/24   | -                  |
| ArcGIS BR  | -                | 10.11.100.0/24     |

---

## 🧰 Hardware & Tools

| Component                        | Quantity (Per Campus) |
| -------------------------------- | --------------------- |
| Cisco Catalyst 3850 48-Port SW   | 2                     |
| Cisco Catalyst 2960 SWs          | 1 per faculty         |
| Cisco ASA 5500-X Firewall        | 1                     |
| Cisco Wireless LAN Controller    | 1                     |
| Lightweight Access Points (LAPs) | Multiple              |
| Physical Servers                 | 2 (Virtualized)       |
| IP Phones                        | Per department        |
| Airtel ISP Router                | 1                     |
| ArcGIS Enterprise Servers        | HQ: 3, BR: 2          |

---

## ⚙️ Configuration Summary

### 🔑 Basic Device Settings

- Hostname
- Banner MOTD
- Console & Enable passwords
- Password encryption
- Disable IP domain lookup

### 🧭 VLANs

- VLAN 10: Management
- VLAN 20: LAN
- VLAN 50: WLAN
- VLAN 199: Blackhole
- VLAN 100: ArcGIS HQ Production
- VLAN 101: ArcGIS BR Staging

### 🔄 Inter-VLAN Routing

- Enabled on Layer 3 Core Switch

### 🔗 EtherChannel

- Configured using **LACP** on uplinks

### 🌐 OSPF Routing

- Advertised on all Layer 3 devices and firewalls

### 🚨 ACLs & SSH

- Standard ACL on **VTY lines**
- SSH restricted to the **Senior Network Engineer's PC**

### 🌉 IPsec VPN

- Site-to-site VPN between Cisco ASA Firewalls

### 🏗️ ArcGIS Workload Separation

- Dedicated VLANs and subnets for Production (HQ) and Staging (BR)
- Isolated storage and processing resources
- Synchronization via secured replication channels

### 🧪 Final Testing

- Ping tests across VLANs
- VPN tunnel verification
- DHCP assignment
- Access to DMZ services (WEB, DNS, FTP)
- Failover and load balancing tested via HSRP
- ArcGIS environment isolation verification

---

## 📝 Additional Notes (from Engineer)

- **Subnetting** carefully applied to match department size projections.
- **Redundancy** achieved via HSRP for DHCP and gateway availability.
- **Blackhole VLAN** used to secure unused ports.
- VLAN-to-interface mappings ensure **clear broadcast domains** and segmentation.
- ASA Firewalls are the central **policy enforcers** across WAN and DMZ.
- **Cloud linkage** ensures external users can access university services globally.
- **ArcGIS separation** maintains complete isolation between Production and Staging environments while allowing controlled data synchronization.

---

## 🚀 Outcomes & Benefits

- ✅ **Secure & scalable architecture** ready for 2025 projections
- ✅ **Centralized management** of WiFi, servers, and security policies
- ✅ **Resilient infrastructure** with redundancy at key points
- ✅ **Cost-effective** use of virtualization and VLANs
- ✅ **Efficient traffic control** through OSPF and ACLs
- ✅ **Prepared for digital learning expansion** via Cloud connectivity
- ✅ **Proper workload separation** for ArcGIS Enterprise environments

---

---

## 📁 Files & Documentation

- `0 Studying Case Study.txt` – Original case study
- `0.1 Requirements, Notes & Config Steps.txt` – Engineer's personal analysis and configuration steps
- `README.md` – You're reading it!

---

## 🧠 Suggested Improvements (Future Work)

- Introduce **Network Monitoring Tools** (e.g., SNMP, NetFlow, Syslog)
- Evaluate **SD-WAN** for better WAN management
- Implement **Multi-site Telephony** service between HQ & BR
- Add **BGP Routing with Firewall IPsec Tunnel** for advanced routing scenarios
- Enhance **ArcGIS synchronization** with automated replication workflows
- Implement **GIS-specific security policies** for enhanced spatial data protection

---

# Project Analysis

## 1. Requirements Extraction

### Business Requirements

- Support 30,000+ users (scaling to 60,000 by 2025)
- Centralized IT management from the main campus
- Secure access to DMZ servers (DHCP, DNS, FTP) for branch campus users
- Global resource delivery via Google Cloud integration

### Technical Requirements

**Hardware:**

- 2x Cisco ASA 5500-X firewalls (one per campus)
- Core: 2x Catalyst 3850 48-port switches per campus
- Access: Catalyst 2960 48-port switches per faculty
- Wireless: Cisco WLC + Lightweight APs (LAPs)
- Servers: 2x physical servers for virtualization

**Software:**

- Hypervisor for VMs (unspecified type)
- Google Cloud for external services

**Protocols:**

- VLANs:
  - 10 (Management)
  - 20 (LAN)
  - 50 (WLAN)
  - 199 (Blackhole)
  - Use subnetting to allocate IPs for WLAN, LAN, Voice, Management and DMZ segments
  - Configure inter-VLAN routing using multilayer switches for communication
  - Establish high availability and failover with HSRP
- Routing: OSPF on ASAs and multilayer switches
  - Integrate Cisco ASA Firewall for enhanced security with inspection policies
- Redundancy: HSRP, EtherChannel (LACP)
- Security: IPsec VPN, ACLs, BPDUguard

**User Demands:**

- VoIP for all departments (IP phones)
  - Ensure VoIP telephony services using the Cisco WAN Router
- WiFi coverage per faculty (centrally managed)

---

## 2. Implementation Notes & Constraints

### General Notes

- For WLC, instead of connecting to any of MLS that will limit redundancy, we will connect WLC to Switch and this switch will be connected to both HSRB
- For MLS, sometimes is missing FastEthernet Ports, you must add manually
- Will implementing this topology be smart and prepare a chunk of some combined devices and then copy paste to another and also config this end devices (printer, pc, etc.) to use DHCP and power on and other primitive settings
- Also while working on this topology, use fixing ports for specific tasks, this will also make the config easier:
  - Port 1-2 → For MLS
  - Port 3-12 → LAN / Wired Devices
  - Port 12-14 → Management VLAN (In one Switch, otherwise from 3-14 for LAN)
  - Port 15-18 → ArcGIS Enterprise VLANs (App, webserver, data, database & serverside)
  - Port 18-20 → For VoIP
  - Port 21-24 → Access Points / WLAN
  - Ports gig or any unused ports → blackhole VLAN

### Constraints

- Distance: 100-mile separation between campuses → Reliance on IPsec VPN (potential latency)
- ISP Dependency: Single ISP (Airtel) per campus → No WAN redundancy
- DMZ Security: Main campus hosts DMZ; branch accesses it via VPN (exposure risk)

### Key Considerations

**Redundancy:**

- Dual DHCP servers (Active Directory)
- HSRP for default gateway failover

**Segmentation:**

- Strict VLAN separation (LAN/WLAN/VoIP)
- Blackhole VLAN (199) for unused ports

**Scalability:**

- /16 subnets for LAN/Voice allow growth
- Recommend SD-WAN for future VPN optimization
- Each department requires sufficient bandwidth, especially for guest WLAN traffic
- Secure access to Google cloud services for developers and applications
- Compliance with standards for data security and privacy

---

## 3. Step-by-Step Configuration Guide

1. **Topology & Beautify**
2. **Basic Config**
3. **VLAN Setup**
4. **Subnetting**
   - WLAN: 10.10.0.0/16
   - LAN: 192.168.0.0/20
   - Voice: 172.16.0.0/20
   - DMZ: 10.20.20.0/26
5. **Inter-VLAN Routing** (OSPF, Virtual Interfaces & Assign Static IPs For Server Rooms)
6. **Wireless Configuration**
7. **ASA Firewall & Security Policies**
8. **HSRP for Default Gateway Redundancy**
9. **IPsec VPN (Site-to-Site)**
10. **Security Hardening**

---

## 4. Observations and Recommendations During Implementation

- Regularly test backup systems and failover mechanisms to minimize downtime risks
- Monitor bandwidth usage on WLAN to prevent congestion due to guest or corporate user activity
- Document all configurations, especially OSPF and firewall policies, for reference during troubleshooting
- Consider future integration of AI-driven network monitoring for proactive issue detection

### Adjustments Made

- Used firewalls as routers (no dedicated routers)
- Allocated /16 subnets despite initial over-provisioning

### Best Practices

- Standardization: Consistent VLAN IDs across campuses
- Security: Disabled unused ports (Blackhole VLAN), encrypted passwords

### Future Enhancements

**Immediate:**

- Implement QoS for VoIP traffic
- Enable NetFlow/sFlow for traffic monitoring

**Long-Term:**

- Migrate to SD-WAN for better VPN performance
- Deploy IDS/IPS for DMZ traffic inspection

### Documentation

- Tools: NetBox for IPAM, Lucidchart for topology diagrams
- Process: Document all ACLs, VLANs, and IP schemes in a central wiki

---

## 5. Validation Testing Plan

| Test Case                | Procedure                                            | Expected Result                    |
| ------------------------ | ---------------------------------------------------- | ---------------------------------- |
| Inter-VLAN Communication | Ping from Health Sciences (VLAN 20) to Art (VLAN 20) | Success (10.10.x.x → 10.10.y.y)    |
| VPN Connectivity         | Transfer 1GB file between campuses via SMB           | No packet loss, throughput >50Mbps |
| DHCP Functionality       | Connect laptop, verify IP from 10.10.1.10/16         | Correct IP, DNS, gateway           |
| HSRP Failover            | Disable primary Core Switch                          | Backup takes over (<1s outage)     |
| SSH Access Control       | Attempt SSH from unauthorized IP (192.168.10.101)    | Connection refused                 |
