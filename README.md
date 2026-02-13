# GRE-VPN-Network-Lab

GRE Tunnel VPN configuration between Toronto and Montreal using EIGRP and VLANs (Cisco Packet Tracer)

## 📋 Overview

This repository contains a practical lab implementation of a GRE (Generic Routing Encapsulation) VPN tunnel connecting two sites: Toronto and Montreal. The lab demonstrates secure site-to-site connectivity over a public network (ISP) using Cisco Packet Tracer.

## 🎯 Learning Objectives

- Configure GRE tunnels between remote sites
- Implement EIGRP routing protocol over GRE tunnels
- Understand VPN concepts and encapsulation
- Configure basic routing and NAT
- Verify tunnel connectivity and routing

## 🗂️ Repository Structure

```
GRE-VPN-Network-Lab/
│
├── README.md                          # This file - Project documentation
├── diagrams/                          # Network topology diagrams
│   └── network_topology.png          # Visual representation of the network
├── configs/                           # Router configuration files
│   ├── R1_config.txt                 # Toronto router configuration
│   ├── R2_config.txt                 # Montreal router configuration
│   └── ISP_config.txt                # ISP router configuration
├── screenshots/                       # Lab verification screenshots
│   ├── ping_test.png                 # Successful ping test between sites
│   └── tunnel_status.png             # GRE tunnel status verification
├── files/                            # Packet Tracer project files
│   └── Pratique_GRE.pkt              # Complete lab implementation
└── report/                           # Lab report documentation
    └── Rapport_lab_pratique_GRE.docx # Detailed lab report (French)
```

## 🌐 Network Topology

### Sites:
- **Toronto (R1)**: LAN Network 192.168.10.0/24
- **Montreal (R2)**: LAN Network 192.168.20.0/24
- **ISP**: Provides WAN connectivity between sites

### GRE Tunnel:
- **Tunnel Network**: 10.0.0.0/30
- **R1 Tunnel IP**: 10.0.0.1
- **R2 Tunnel IP**: 10.0.0.2

### WAN Connections:
- **R1 to ISP**: 200.1.1.0/30
- **R2 to ISP**: 200.2.2.0/30

## 🔧 Configuration Summary

### R1 (Toronto Router)
- WAN Interface: 200.1.1.1/30
- LAN Interface: 192.168.10.1/24
- Tunnel Interface: 10.0.0.1/30
- Tunnel Destination: 200.2.2.2

### R2 (Montreal Router)
- WAN Interface: 200.2.2.2/30
- LAN Interface: 192.168.20.1/24
- Tunnel Interface: 10.0.0.2/30
- Tunnel Destination: 200.1.1.1

### ISP Router
- Interface to R1: 200.1.1.2/30
- Interface to R2: 200.2.2.1/30

## 🚀 Getting Started

### Prerequisites
- Cisco Packet Tracer (version 7.3 or later)
- Basic understanding of:
  - IP addressing and subnetting
  - Cisco IOS commands
  - Routing protocols (EIGRP)
  - VPN concepts

### Usage Instructions

1. **Open the Packet Tracer File**
   ```
   Open files/Pratique_GRE.pkt in Cisco Packet Tracer
   ```

2. **Review Configurations**
   - Check the configs/ directory for detailed router configurations
   - Each file contains the complete configuration for its respective device

3. **Verify Connectivity**
   - Test ping from Toronto LAN to Montreal LAN
   - Verify GRE tunnel status using `show interface tunnel 0`
   - Check EIGRP neighbors with `show ip eigrp neighbors`
   - View routing table with `show ip route`

4. **Study the Lab Report**
   - Open report/Rapport_lab_pratique_GRE.docx for detailed documentation
   - Review screenshots/ directory for verification examples

## ✅ Verification Commands

On R1 or R2:
```cisco
show interface tunnel 0
show ip interface brief
show ip route
show ip eigrp neighbors
show ip eigrp topology
ping 192.168.20.1 source 192.168.10.1
```

## 📊 Key Features

- ✓ GRE Tunnel encryption between sites
- ✓ EIGRP dynamic routing protocol
- ✓ Site-to-site VPN connectivity
- ✓ Scalable network design
- ✓ Full documentation and verification

## 📚 Technologies Used

- **GRE (Generic Routing Encapsulation)**: Tunnel protocol
- **EIGRP**: Enhanced Interior Gateway Routing Protocol
- **Cisco IOS**: Router operating system
- **Cisco Packet Tracer**: Network simulation tool

## 🤝 Contributing

Feel free to fork this repository and submit pull requests for improvements or additional features.

## 📝 License

This project is for educational purposes.

## 👤 Author

Diallo Ramatoulaye Bah

## 📧 Contact

For questions or feedback, please open an issue in this repository.
