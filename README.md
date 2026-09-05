# Medium Enterprise Network with Inter-VLAN Routing, NAT, and ACLs

This repository contains a complete Packet Tracer simulation of a medium enterprise network. The project demonstrates advanced routing, secure network segmentation through VLANs, internet translation via NAT, and traffic control using Access Control Lists (ACLs).

---

## 🏗️ Network Topology & Architecture
* **Core Layer:** Cisco 3560 Multilayer Switch (Handles Inter-VLAN routing via SVI and core switching).
* **Edge Layer:** Cisco 2911 Router (Handles Internet gateway, NAT/PAT, and routing back to VLAN subnets).
* **Access Layer:** Cisco 2960 Switches (Connect departmental end-devices).
* **Departments / VLANs:**
  * **VLAN 10 (Sales):** `192.168.10.0/24`
  * **VLAN 20 (Finance):** `192.168.20.0/24`
  * **Core Link / Transit:** `192.168.100.0/24`

---

## 🛠️ Key Configurations Implemented

1. **Inter-VLAN Routing:** Configured `ip routing` and Switch Virtual Interfaces (SVIs) on the Layer 3 Catalyst switch to enable seamless cross-departmental communication without a router-on-a-stick bottleneck.
2. **Network Address Translation (NAT / PAT):** Enabled dynamic port address translation on the edge router using standard access lists (`access-list 1`) to share public IP translation.
3. **Security (Extended ACL):** Implemented an extended access control list (`access-list 100`) to restrict traffic flow (e.g., blocking Sales from accessing specific secure finance servers while allowing general internet access).
4. **Static Routing:** Configured static routes on the edge router to direct return traffic back to the internal VLAN subnets via the L3 switch.

---

## 🚀 How to Open and Test

1. Download and open **Cisco Packet Tracer**.
2. Open the `.pkt` file included in this repository.
3. Verify connectivity by pinging between departments or testing internet simulation traffic.
4. Check running configurations using `show running-config` on the core switch or router.

---

## 📂 Deliverables
* Fully configured Packet Tracer Topology File (`.pkt`)
* Device CLI configuration summaries
