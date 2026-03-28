# 🌐 Secure Multi-Site Enterprise Network

## 🏢 Project Overview
A production-ready enterprise network simulating real-world corporate infrastructure used by companies like Orange, Cisco, and Capgemini.

## 📊 Network Stats
- **2 Offices** (HQ + Branch)
- **2 Routers** (Cisco 2911)
- **3 Switches** (Cisco 2960)
- **8 PCs + 1 Web Server**
- **5 VLANs** across both sites
- **WAN Link**: 10.0.0.0/30

## 🔧 Technologies Implemented
| Technology | Purpose |
|------------|---------|
| VLAN 802.1Q | Network segmentation (HR, IT, SALES, GUEST, SERVERS) |
| Inter-VLAN Routing | Router-on-a-Stick for cross-VLAN communication |
| OSPF | Dynamic routing between HQ and Branch |
| DHCP | Automatic IP assignment for all devices |
| ACL | Security policy blocking unauthorized access |
| SSH v2 | Secure encrypted remote management |
| Web Server | Internal company website (192.168.50.10) |

## 📡 IP Addressing Scheme
| VLAN | Name | Network | Gateway |
|------|------|---------|---------|
| 10 | HR | 192.168.10.0/24 | 192.168.10.1 |
| 20 | IT | 192.168.20.0/24 | 192.168.20.1 |
| 30 | SALES (Switch-1) | 192.168.30.0/24 | 192.168.30.1 |
| 30 | SALES (Switch-2) | 192.168.31.0/24 | 192.168.31.1 |
| 40 | GUEST (Switch-1) | 192.168.40.0/24 | 192.168.40.1 |
| 40 | GUEST (Switch-2) | 192.168.41.0/24 | 192.168.41.1 |
| 50 | SERVERS | 192.168.50.0/24 | 192.168.50.1 |
| WAN | Link | 10.0.0.0/30 | 10.0.0.1/2 |

## 🔒 Security Features
- **ACL 100**: Blocks SALES (192.168.30.0/24) from accessing HR (192.168.10.0/24)
- **SSH v2**: Secure router management with RSA 1024-bit encryption
- **VLAN Segmentation**: Department isolation
- **Port Security**: Access ports assigned to specific VLANs

## ✅ Testing Results
| Test | Source | Destination | Result |
|------|--------|-------------|--------|
| DHCP | PC1 | - | 192.168.20.11 ✓ |
| DHCP | PC6 | - | 192.168.31.11 ✓ |
| Inter-VLAN | PC1 (IT) | PC6 (SALES) | Success ✓ |
| Web Access | Any PC | 192.168.50.10 | Success ✓ |
| ACL | PC3 (SALES) | 192.168.10.1 | Blocked ✓ |
| SSH | Any PC | Router-HQ | Secure Login ✓ |

## 🛠️ Tools Used
- Cisco Packet Tracer 8.2+
- Git / GitHub
- Command Line Interface (CLI)

## 📁 Repository Contents
