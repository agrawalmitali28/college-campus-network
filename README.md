# College Campus Network Design and Security

A VLAN-based college campus network designed and simulated using **Cisco Packet Tracer**, featuring network segmentation, centralized network services, access control, and an expanded topology.

## 📌 Project Overview

This project demonstrates how a college campus network can be organized to support students, faculty, and shared servers while applying fundamental networking and security concepts.

The network was expanded by adding a third switch and four additional PCs, reusing the existing VLANs and subnets to keep the design scalable and manageable.

## 🎯 Objectives

- Design a segmented college campus network.
- Configure VLANs and inter-VLAN routing.
- Provide automatic IP configuration using DHCP.
- Configure DNS for domain-based website access.
- Host a college website using HTTP.
- Implement access control and secure router management.
- Configure switch port security.
- Verify network connectivity and observe packets using Simulation Mode.

## 🏗️ Network Architecture

The topology consists of:

- **1 Cisco 2911 router** — inter-VLAN routing and access control.
- **3 Cisco 2960 switches** — connecting clients and servers.
- **7 PCs** — student and faculty endpoints.
- **2 servers** — centralized DHCP/DNS services and website hosting.

### VLAN and IP Addressing

| VLAN | Name | Network | Default Gateway |
|---|---|---|---|
| 10 | STUDENTS | `192.168.10.0/24` | `192.168.10.1` |
| 20 | FACULTY | `192.168.30.0/24` | `192.168.30.1` |
| 40 | SERVERS | `192.168.40.0/24` | `192.168.40.1` |

### Device Allocation

- **Student VLAN:** PC0, PC1, PC3, PC4
- **Faculty VLAN:** PC2, PC5, PC6
- **Server0:** DHCP and DNS — `192.168.40.2`
- **Server1:** HTTP website — `192.168.40.3`

Switch2 connects to Switch0 through a trunk carrying VLANs 10, 20, and 40.

## ⚙️ Technologies and Concepts

- Cisco Packet Tracer 9.0.1
- VLAN configuration and IEEE 802.1Q trunking
- Router-on-a-stick inter-VLAN routing
- DHCP and DHCP relay
- Domain Name System (DNS)
- HTTP web hosting
- Extended Access Control Lists (ACLs)
- SSH version 2
- Sticky MAC port security
- Switchport shutdown for unused ports
- Packet analysis using Simulation Mode

## 🔐 Security Features

**1. VLAN segmentation:** Separates student, faculty, and server networks into logical broadcast domains.

**2. Access Control List:** Restricts student access to the server subnet while permitting configured DNS and web traffic.

**3. SSH version 2:** Provides secure remote command-line management of the router.

**4. Port security:** Learns sticky MAC addresses, limits each configured user-facing port to one secure MAC address, and uses the restrict violation action.

**5. Unused-port shutdown:** Disables selected unused switch ports to reduce unauthorized connection opportunities.

## 🧪 Testing and Results

The following tests were performed in Cisco Packet Tracer:

- DHCP successfully assigned IP addresses to the added PCs.
- PC3 successfully accessed `http://www.collegenetwork.com`.
- PC5 successfully accessed `http://www.collegenetwork.com`.
- VLAN assignments and trunk configuration on Switch2 were verified.
- Sticky MAC address learning and port-security status were verified on Switch2.
- Simulation Mode was used to observe website-related DNS/HTTP packet events.
- Student ICMP ping to Server0 was blocked by the configured student ACL, as expected.

## 🚀 How to Run the Project

1. Install Cisco Packet Tracer 9.0.1 or a compatible version.
2. Clone or download this repository.
3. Open the `.pkt` project file in Cisco Packet Tracer.
4. Allow the topology to initialize.
5. Verify that DHCP and DNS are enabled on Server0 and HTTP is enabled on Server1.
6. Open a client PC and select **Desktop → IP Configuration → DHCP**.
7. Open the PC's web browser and visit:

   `http://www.collegenetwork.com`

8. Switch to **Simulation Mode** to observe relevant network events.

## 📁 Project Contents

The repository should contain the following project artifacts, using the actual filenames present in the repository:

- Cisco Packet Tracer `.pkt` topology
- Project report (`.docx`)
- Project presentation (`.pptx`)
- `README.md`

## 🔮 Future Enhancements

- Configure and verify HTTPS.
- Introduce a dedicated network management VLAN.
- Add centralized logging and network monitoring.
- Implement redundant links and evaluate network resilience.
- Extend testing to include more clients and failure scenarios.

## ⚠️ Limitations

- The project is a simulated network, not a production campus deployment.
- No external ISP, WAN, or public Internet connection is configured.
- The student ACL applies to the student VLAN; it is not a complete enterprise security policy.
- HTTP was tested; HTTPS has not been confirmed.

## 👩‍💻 Learning Outcomes

This project provided practical experience with network segmentation, routing, addressing, network services, access control, switch security, troubleshooting, and packet-level analysis.

---

**Project:** College Campus Network Design and Security  
**Platform:** Cisco Packet Tracer  
**Category:** Computer Networks / Network Security