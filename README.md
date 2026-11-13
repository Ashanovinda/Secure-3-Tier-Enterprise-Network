# Secure 3-Tier Enterprise Network Architecture

## 📌 Project Overview
This project demonstrates the design, configuration, and implementation of a highly available 3-Tier Enterprise Network (Core, Distribution, Access) using Cisco networking protocols. The project integrates virtual simulated environments (GNS3) with physical hardware (VMware Workstation & secondary physical host) to create a fully functional hybrid intranet environment hosting a Windows Server 2022 IIS Web Server.

## 🛠️ Technologies & Tools Used
* **Network Simulator:** GNS3
* **Virtualization:** VMware Workstation
* **Routers/Switches:** Cisco 7200 Series Routers
* **Server OS:** Windows Server 2022 (Desktop Experience)
* **Web Services:** IIS (Internet Information Services)
* **Routing Protocols:** OSPF (Single Area 0), BGP (External)
* **Network Services:** Static/Dynamic NAT, ICMP

## 🏗️ Network Architecture
The network is structured based on the Cisco Hierarchical Model:
1. **Core Layer:** High-speed packet switching using dual Core routers (CORE1, CORE2) configured with OSPF for internal routing.
2. **Distribution Layer:** Policy-based connectivity and boundary control (DIS1, DIS2).
3. **Access Layer:** End-user and server connectivity (A1 Switch connecting VPCS and Windows Server).
4. **Edge & ISP:** An EDGE router connects the enterprise intranet to the ISP using BGP. Overload NAT (PAT) is configured to translate private subnets to public IPs for external access.

*Insert `Topology.jpg` here*

## ⚙️ Key Configurations
* **OSPF Integration:** Established neighbor adjacencies across Core and Distribution layers.
* **BGP Peering:** Configured eBGP between the Enterprise Edge router and the ISP for external routing.
* **Network Address Translation (NAT):** Implemented inside-to-outside NAT on the Edge router to allow internal PCs to reach the internet.
* **VMware Integration:** Bridged the virtual GNS3 topology with a VMware VMnet adapter to connect a Windows Server 2022 virtual machine.
* **Physical-to-Virtual Connection:** Successfully accessed the virtualized IIS Web Server from an external secondary physical laptop via RJ45 ethernet connection.

## 🚀 Proof of Concept (POC)
The following tests were conducted to verify the stability and functionality of the network:
1. **OSPF & BGP Adjacencies:** Verified routing tables and active neighbor connections.
2. **NAT Translation Verification:** Monitored active translations during external pings.
3. **End-to-End Reachability:** Successful ICMP echo requests between internal VPCS and the external ISP.
4. **Intranet Web Hosting:** Successfully hosted and accessed an IIS default web page from an external physical machine traversing the GNS3 network.

*(You can upload the screenshot images here in your GitHub repository to show the proof)*

## 📂 Configuration Files
The raw Cisco IOS configuration files for all routers are included in this repository for reference.
