# Campus Network Design in Cisco Packet Tracer

This project is a comprehensive hierarchical network topology designed for a university with two campuses, multiple buildings, and distinct faculties. The entire network was built, configured, and simulated in **Cisco Packet Tracer** to meet specific connectivity, security, and routing requirements.


## Project Overview

The goal of this project was to design a scalable and secure network for a university. The topology includes a main campus with three buildings (Admin/Business, Engineering/Arts, and IT/Labs) and a separate branch campus for Health Sciences. 

The design focuses on segmenting traffic logically using **VLANs**, providing dynamic IP addressing via **DHCP**, ensuring secure device management with **SSH**, and enabling robust internal routing between all subnets using the **OSPF** protocol.

---

## Key Features & Technologies Implemented

- **Hierarchical Network Design:** A core, distribution, and access layer model for scalability and efficient traffic management.
- **VLANs for Network Segmentation:** Each department and faculty (Admin, HR, Finance, Business, E&C, A&D, IT Dept, etc.) is isolated on its own VLAN to enhance security and reduce broadcast traffic.
- **Inter-VLAN Routing:** Configured "Router on a Stick" on the main router to enable communication between different VLANs across the campus.
- **OSPF Routing Protocol:** Implemented **OSPFv2** instead of RIPv2 for faster and more efficient dynamic routing between the main campus and branch campus routers.
- **DHCP Server Configuration:** The main router is configured as a DHCP server to dynamically assign IP addresses to host devices in Building A.
- **Switchport Security:** Enabled port security on access layer switches to prevent unauthorized device connections by limiting MAC addresses.
- **Secure Remote Management:** Configured **SSH** on network devices (routers and switches) to allow for secure command-line access.
- **Static & Default Routing:** Used a default route on the main router to direct traffic to the external cloud-hosted email server.

---

## Network Breakdown

* **Main Campus:**
    * **Router:** Central device performing Inter-VLAN routing, DHCP, and OSPF.
    * **Building A:** Admin, HR, Finance, and Business VLANs. Hosts use DHCP.
    * **Building B:** Engineering/Computing and Art/Design VLANs.
    * **Building C:** IT Department, Student Labs, and internal servers (Web, FTP) on separate VLANs.
* **Branch Campus:**
    * **Router:** Connects to the main campus via OSPF.
    * **Floors:** Staff and Student Lab VLANs provide logical separation.
* **External Network:**
    * A cloud-hosted Email Server is reachable via a default route from the main campus router.

---

## How to Use

1.  Download the **`CAMPUS_NETWORK.pkt`** file.
2.  Open the file using **Cisco Packet Tracer** (version 7.3 or higher recommended).
3.  The network is fully configured. You can inspect device configurations, view routing tables, and test connectivity using `ping` and other commands from host devices.