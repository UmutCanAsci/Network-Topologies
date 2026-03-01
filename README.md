#  Enterprise Network Infrastructure & Automated Services Simulation

This project is a comprehensive simulation of a **Scalable Enterprise Network** designed using **Cisco Packet Tracer**. It focuses on automating network management, providing internal communication services, and ensuring seamless connectivity between different network segments.

---

##  Real-World Business Scenario
Imagine a growing company with multiple departments spread across different floors or buildings. Setting up every new computer manually is inefficient and prone to errors. 

This project solves this by creating a **"Plug-and-Play" infrastructure**. When a new employee connects a PC to the network:
1. It automatically receives an IP address.
2. It can instantly communicate with the company's internal Mail and DNS servers.
3. It can reach other departments securely through a routed backbone.

---

##  Key Features & Technical Implementation

### 1. Zero-Touch Client Configuration (DHCP & IP Helper)
* **The Problem:** In large networks, a DHCP server might be in a different subnet than the clients. By default, DHCP requests (broadcasts) don't cross routers.
* **The Solution:** I implemented the **`ip helper-address`** command on the Router interfaces. This acts as a relay agent, capturing DHCP requests from clients and forwarding them to the central DHCP Server.
* **Result:** Any new device added to the network gets its IP, Subnet Mask, and Gateway automatically, regardless of its location.

### 2. Centralized Corporate Services (DNS & Mail)
* **DNS Server:** Configured to translate human-readable names (e.g., `company.com`) into IP addresses. This eliminates the need for employees to memorize server IPs.
* **Email Server (SMTP/POP3):** A fully functional internal mail system. I have configured user accounts so that departments can communicate through a private and secure mail ecosystem (e.g., `user@company.com`).

### 3. Intelligent Routing & Switching
* **Inter-VLAN Routing:** Routers are configured to allow controlled communication between different departments.
* **Switching Backbone:** High-speed internal data transfer is managed by switches, ensuring that local traffic stays local, reducing the load on the main routers.

---

##  Project Architecture

| Component | Description |
| :--- | :--- |
| **DHCP Server** | Dynamically assigns IP addresses to all end devices. |
| **DNS Server** | Manages domain name resolution for internal services. |
| **Mail Server** | Handles internal SMTP/POP3 email traffic. |
| **Routers** | Configured with `ip helper-address` and routing protocols. |
| **Switches** | Provide the physical and logical (VLAN) connectivity for PCs. |

---

##  Project Previews

### Network Topology Overview
*The high-level view of the entire infrastructure including routers, switches, and end devices.*
<img width="1288" height="705" alt="Ekran görüntüsü 2026-03-01 154021" src="https://github.com/user-attachments/assets/e575b8ff-6c70-4f5f-924e-a0ac271677c9" />

### Server Configurations (DHCP, DNS & Mail)
*A look into the service configurations that drive the network's intelligence.*
<img width="860" height="703" alt="Ekran görüntüsü 2026-03-01 154220" src="https://github.com/user-attachments/assets/6d2cd2bd-d7b8-46b0-a538-626175830779" />
<img width="856" height="462" alt="Ekran görüntüsü 2026-03-01 154235" src="https://github.com/user-attachments/assets/37270e70-f497-4d4f-bf3b-1b704b6850fd" />
<img width="867" height="710" alt="Ekran görüntüsü 2026-03-01 154313" src="https://github.com/user-attachments/assets/f0af7dee-79ff-4c7d-be10-67e5b5e353d1" />


---

##  How to Test the Simulation
1. Open the `.pkt` file in **Cisco Packet Tracer**.
2. Add a new **PC** to any switch.
3. Set the PC's IP configuration to **DHCP**.
4. Observe the PC receiving an IP address automatically.
5. Use the PC's web browser to navigate to your configured domain or send an email to another user via the Mail Server.

---

**Developed by Umut Can Aşcı** *Feel free to reach out for any questions regarding the configuration!*
