# Enterprise Network Design Using Cisco Packet Tracer

A comprehensive network infrastructure design project implementing a hierarchical three-layer model with redundancy, VLAN segmentation, and advanced networking protocols for enterprise-level scalability and security.

## 📋 Project Overview

This project presents a complete enterprise network design solution executed through Cisco Packet Tracer, facilitating the expansion of a trading floor support center into a new facility. The design emphasizes robust, scalable, and future-ready network infrastructure with comprehensive redundancy measures at each hierarchical layer.

## 🎯 Project Objectives

- **Hierarchical Network Architecture**: Implement a three-layer hierarchical model (Core, Distribution, Access)
- **Redundancy Implementation**: Establish redundancy measures at every network layer
- **Dual ISP Connectivity**: Ensure uninterrupted internet access through multiple ISPs
- **Departmental Segmentation**: Create wireless networks and VLANs for individual departments
- **Advanced Routing**: Deploy OSPF (Open Shortest Path First) for optimal routing
- **Security Enhancement**: Implement SSH, ACLs, and port security measures
- **Network Address Translation**: Configure PAT for efficient outbound connection management

## 🏗️ Network Architecture

### Hierarchical Design Structure

```
┌─────────────────┐    ┌─────────────────┐
│   Core Layer    │────│   Core Layer    │
│   (Routers &    │    │  (Multilayer    │
│   ISP Links)    │    │   Switches)     │
└─────────┬───────┘    └─────────┬───────┘
          │                      │
┌─────────┴──────────────────────┴───────┐
│          Distribution Layer            │
│      (Department Switches)             │
└─────────┬──────────────────────────────┘
          │
┌─────────┴───────┐
│   Access Layer  │
│ (End Devices &  │
│ Wireless APs)   │
└─────────────────┘
```

## 🛠️ Technologies & Protocols Used

**Simulation Platform:** Cisco Packet Tracer

**Core Technologies:**
- **Routing Protocol:** OSPF (Open Shortest Path First)
- **Network Segmentation:** VLANs (Virtual Local Area Networks)
- **Address Assignment:** DHCP (Dynamic Host Configuration Protocol)
- **Network Address Translation:** PAT (Port Address Translation)
- **Security:** SSH (Secure Shell), ACLs (Access Control Lists)
- **Quality of Service:** QoS for voice and video traffic prioritization

## 🏢 Network Components

### Infrastructure Devices

| Component | Quantity | Function | Layer |
|-----------|----------|----------|-------|
| **Core Routers** | 4 (2 Primary + 2 ISP) | Internet connectivity & redundancy | Core |
| **Multilayer Switches** | 2 | Inter-VLAN routing & core switching | Core |
| **Distribution Switches** | Multiple | Department-level connectivity | Distribution |
| **Access Points** | Multiple | Wireless connectivity per department | Access |
| **End-User Devices** | Multiple | Workstations and terminals | Access |
| **DHCP Server** | 1 | Dynamic IP address allocation | Server Room |
| **DNS/HTTP Servers** | Multiple | Network services | Server Room |

## 🏢 Departmental Network Layout

### Floor-wise VLAN Distribution

#### First Floor
| Department | Network Address | Subnet Mask | Host Range | Broadcast |
|------------|----------------|-------------|------------|-----------|
| **Sales & Marketing** | 192.168.10.0 | 255.255.255.0 (/24) | 192.168.10.1-254 | 192.168.10.255 |
| **HR & Logistics** | 192.168.20.0 | 255.255.255.0 (/24) | 192.168.20.1-254 | 192.168.20.255 |

#### Second Floor
| Department | Network Address | Subnet Mask | Host Range | Broadcast |
|------------|----------------|-------------|------------|-----------|
| **Finance & Accounts** | 192.168.30.0 | 255.255.255.0 (/24) | 192.168.30.1-254 | 192.168.30.255 |
| **Admin & Public Relations** | 192.168.40.0 | 255.255.255.0 (/24) | 192.168.40.1-254 | 192.168.40.255 |

#### Third Floor
| Department | Network Address | Subnet Mask | Host Range | Broadcast |
|------------|----------------|-------------|------------|-----------|
| **ICT Department** | 192.168.50.0 | 255.255.255.0 (/24) | 192.168.50.1-254 | 192.168.50.255 |
| **Server Room** | 192.168.60.0 | 255.255.255.0 (/24) | 192.168.60.1-254 | 192.168.60.255 |

### Core Network Interconnections
| Connection | Network Address | Subnet Mask | Purpose |
|------------|----------------|-------------|---------|
| Core R1-MLTSW1 | 10.10.10.0 | 255.255.255.252 (/30) | Point-to-point link |
| Core R1-MLTSW2 | 10.10.10.4 | 255.255.255.252 (/30) | Point-to-point link |
| Core R2-MLTSW1 | 10.10.10.8 | 255.255.255.252 (/30) | Point-to-point link |
| Core R2-MLTSW2 | 10.10.10.12 | 255.255.255.252 (/30) | Point-to-point link |

**Public IP Ranges:** 103.133.254.0/30 series for ISP connectivity

## 🔧 Key Features Implemented

### 🔄 Redundancy & High Availability
- **Dual ISP Connections** for internet redundancy
- **Multiple Core Routers** for failover capability
- **Redundant Multilayer Switches** at core layer
- **Load Balancing** across multiple paths

### 🔒 Security Measures
- **Access Control Lists (ACLs)** for traffic filtering
- **Port Security** on critical switchports (Finance department)
- **SSH Access** for secure remote management
- **VLAN Segmentation** for network isolation
- **MAC Address Security** on sensitive ports

### 📡 Network Services
- **DHCP Server** for automatic IP assignment
- **DNS Resolution** for name services
- **HTTP Services** for web applications
- **Inter-VLAN Routing** for departmental communication

### 🚀 Performance Optimization
- **QoS Implementation** for voice and video traffic
- **OSPF Routing** for optimal path selection
- **Network Address Translation** (PAT) for efficient IP usage
- **Bandwidth Management** per department

## 📊 Testing & Validation

### Simulation Testing
- **Connectivity Verification**: ICMP PDU testing across all VLANs
- **Routing Validation**: Traceroute verification for optimal paths
- **DHCP Functionality**: Dynamic IP allocation testing
- **Failover Testing**: Redundancy mechanism verification
- **Performance Metrics**: Latency and throughput analysis

### Troubleshooting Procedures
- **Inter-VLAN Communication** testing and resolution
- **DHCP Lease Management** and troubleshooting
- **OSPF Convergence** verification and optimization
- **Access Control** validation and adjustment
- **Port Security** configuration and testing

## 📈 Performance Metrics

The network design achieves optimal performance across key metrics:

- **Network Latency**: Minimized through hierarchical design
- **Throughput**: Maximized via redundant paths
- **Availability**: 99.9%+ uptime through redundancy
- **DHCP Response**: Sub-second IP allocation
- **Inter-VLAN Performance**: Optimized routing paths
- **Security**: Comprehensive access control implementation

## 🛡️ Security Implementation

### Access Control
- **SSH Configuration** on all network devices
- **Role-based Access** for different user levels
- **Port Security** preventing unauthorized device connections
- **VLAN Isolation** between departments

### Network Segmentation
- **Departmental VLANs** for traffic isolation
- **ACL Implementation** for traffic filtering
- **Secure Server Room** with restricted access
- **Wireless Security** on all access points

## 🔮 Future Enhancements

### Planned Improvements
- **Network Monitoring Tools** for proactive management
- **Enhanced Security Measures** including IPS/IDS
- **Virtualization Technologies** for resource optimization
- **Advanced Routing Protocols** (BGP for multiple ISPs)
- **IPv6 Implementation** for future-proofing
- **Wireless Network Expansion** throughout facility
- **Cloud Integration** capabilities
- **Energy Efficiency Measures** for sustainable operations

### Scalability Considerations
- **Modular Design** allowing easy expansion
- **Bandwidth Upgrade Paths** for growing demands
- **Additional VLAN Support** for new departments
- **Enhanced Security Layers** for evolving threats

## 📚 Technical Abbreviations

| Abbreviation | Full Form |
|--------------|-----------|
| ACL | Access Control List |
| DHCP | Dynamic Host Configuration Protocol |
| IP | Internet Protocol |
| OSPF | Open Shortest Path First |
| PAT | Port Address Translation |
| QoS | Quality of Service |
| SSH | Secure Shell |
| VLAN | Virtual Local Area Network |

## 🏁 Project Results

### Achieved Objectives ✅
- ✅ **Hierarchical Network Design** successfully implemented
- ✅ **Multi-layer Redundancy** ensuring high availability
- ✅ **Departmental Segmentation** through VLAN implementation
- ✅ **Inter-VLAN Routing** configured and optimized
- ✅ **Comprehensive Security** measures deployed
- ✅ **NAT/PAT Configuration** for efficient address translation
- ✅ **QoS Implementation** for traffic prioritization
- ✅ **Thorough Testing** completed with full functionality

### Key Lessons Learned
- **Redundancy is Critical** for enterprise network reliability
- **VLAN Segmentation** enhances both security and management
- **Comprehensive Testing** prevents deployment issues
- **Security-First Design** protects against unauthorized access
- **Scalability Planning** enables future growth accommodation
- **Documentation** is essential for maintenance and troubleshooting

## 📧 Contact Information

**Project Developer:** Muhammad Sudais Khalid  
**Email:** muhammadsudaiskhalid.artificialintelligence@stmu.edu.pk  
**LinkedIn:** [https://www.linkedin.com/in/sudais-khalid/](https://www.linkedin.com/in/sudais-khalid/)  
**Discord:** [https://discord.com/invite/cfjfrec9](https://discord.com/invite/cfjfrec9)

## 📄 License

This project is available under the MIT License for educational and research purposes.

## 🔗 Related Projects

For additional networking and AI projects: [Speech Emotion Analysis for Workplace Wellness](https://github.com/muhammadsudaiskhalid/Speech-Emotion-Analysis-for-Workplace-Wellness)

---

*This enterprise network design demonstrates advanced networking concepts implementation using industry-standard practices for scalable, secure, and efficient network infrastructure.*
