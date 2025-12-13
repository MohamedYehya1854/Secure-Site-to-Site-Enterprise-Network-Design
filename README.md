# Secure Site-to-Site Enterprise Network Design 🔐🌐

## 📌 Project Overview
This project presents a **real-world enterprise network security design and implementation** using a **FortiGate Next-Generation Firewall (NGFW)**. The lab simulates a **Head Office (HO)** and a **Branch Office** connected securely over the Internet using **IPsec Site-to-Site VPN**, while enforcing advanced security controls such as **SSL Inspection, Identity-Based Policies, Web Filtering, IPS, Application Control, and QoS**.

The project was developed as a **Final Graduation Project** under the **Digital Egypt Pioneers Initiative (DEPI)** – *Fortinet Cyber Security Engineer Track*.

---

## 🎯 Project Objectives
The main goal of this project is to design and deploy a **secure, scalable, and enterprise-grade network architecture** that balances **security, availability, and performance**.

### Key Objectives:
- **Network Segmentation** using VLANs (Users, Guest, Managers, Network, DMZ)
- **Perimeter Security** with FortiGate NGFW
- **Secure Connectivity** via:
  - IPsec Site-to-Site VPN (HO ↔ Branch)
  - IPsec Remote Access VPN (FortiClient)
- **Identity-Based Security** using:
  - Active Directory
  - LDAP Integration
  - FSSO (Agent-Based Authentication)
- **Advanced Threat Protection**:
  - Deep SSL Inspection
  - Web Filtering
  - Antivirus
  - Application Control
  - Intrusion Prevention System (IPS)
- **Traffic Management & QoS** using Traffic Shaping
- **High Availability & Redundancy**:
  - Dual WAN (ISP Failover)
  - Link Aggregation / Redundant Interfaces
- **System Administration & Hardening**

---

## 🏗️ Network Architecture

### Head Office (HO)
- **FortiGate Firewall** acting as the security gateway
- **Cisco Layer 3 Core Switch** for Inter-VLAN routing & DHCP
- **Access Switches (L2)** for end devices
- **DMZ Zone** hosting isolated servers
- **Infrastructure Zone** (AD, DNS, NTP, FortiAnalyzer)

### Branch Office
- Local LAN connected to the Internet via ISP Router
- Secure connection to HO using **IPsec VPN**

### WAN / Internet
- Simulated ISP providing public IP addressing

---

## 🌐 IP Addressing & VLAN Design
- Internal networks are segmented using **802.1Q VLANs**
- Routing is handled by the **Core Switch**, with a **Transit VLAN** between Core and FortiGate
- FortiGate maintains static routes back to internal networks

---

## 🔧 Core Configurations

### 🔹 Switch Configuration
- VLAN creation and trunking on Access Switches
- DHCP configuration on Core Switch
- Default route pointing to FortiGate

### 🔹 FortiGate Configuration
- Interface assignment & static routing
- NAT (SNAT & DNAT)
- Firewall policies per VLAN
- Scheduled access policies
- DMZ isolation using zones
- Central NAT handling & conflict resolution

---

## 🔐 Authentication & Identity Management

### Methods Implemented:
- **Local Users + Captive Portal** (Active Authentication)
- **Active Directory Integration**
- **LDAP Authentication**
- **FSSO Agent-Based Authentication (Passive Authentication)**

✔ Enables **user/group-based firewall policies** instead of IP-based rules

---

## 🔍 SSL Inspection & Certificates

- Deployment of **Enterprise Certificate Authority (CA)** via Active Directory
- Certificate distribution using **Group Policy (GPO)**
- Comparison and implementation of:
  - Certificate Inspection
  - Deep SSL Inspection

⚠️ Deep SSL Inspection is mandatory for Web Filtering & Application Control

---

## 🛡️ Security Profiles

### Implemented Profiles:
- **Web Filtering**
  - Category-based blocking
  - Custom categories & overrides
  - URL filtering (Simple & Wildcard)
- **Antivirus**
  - Signature-based malware detection
  - Email & executable protection
- **Application Control**
  - Application-level restrictions
  - Protocol enforcement (e.g. FTP only on port 21)
- **Intrusion Prevention System (IPS)**

---

## 🚦 Traffic Shaping & QoS
- Bandwidth control for users and applications
- Guaranteed bandwidth for critical services
- Rate-limiting for non-essential traffic

---

## 🔗 VPN Configuration

### 🔸 IPsec Site-to-Site VPN
- Secure tunnel between HO and Branch
- Encrypted communication between internal networks

### 🔸 IPsec Remote Access VPN
- FortiClient-based VPN
- User-based access control
- Network-level permissions (e.g. Manager VLAN only)

---

## 🌍 Advanced Routing & High Availability

- **Dual WAN (ISP Failover)**
- Policy-Based Routing for specific users
- Multiple Interface Policies
- DNS & NTP synchronization

---

## ⚙️ System Administration

- Configuration Backup & Restore
- Trusted Hosts (restrict management access)
- Admin Profiles & Role-Based Access Control (RBAC)
- Security hardening best practices

---

## 📌 Key Takeaways
- Demonstrates a **complete enterprise-grade FortiGate deployment**
- Covers **networking, security, identity, VPN, and administration**
- Closely simulates **real corporate environments**
- Follows **Fortinet best practices**

---

## 👥 Team Members
- Aliaa Adel Saad Elshenawy
- AbdelRahman Mohamed Ismail AbdelSadek
- Mahdi Gebreil Mahdi Mohamed
- **Mohamed Al‑Sayed Al‑Tantawy Yehya**
- Zaid Mohammed Taha Emara

---

## 🔗 Repository
📌 GitHub Repository:
```
https://github.com/MohamedYehya1854/Secure-Site-to-Site-Enterprise-Network-Design
```

---

## 🏁 Final Notes
This project is intended for **learning, demonstration, and academic purposes** and reflects real-world enterprise security design principles using FortiGate NGFW solutions.

⭐ If you find this project helpful, feel free to **star the repository** on GitHub!

