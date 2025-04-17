# 🏢 Central and Branch Office Network Topology

This project shows a network topology that I created during my internship using Cisco Packet Tracer.  
It is designed as a central office located in Şişli, and two branch offices in Ataşehir and Sarıyer.  
The three offices are connected and can communicate through routers.

---

## 🧱 About the Topology

The network includes the following devices and features:

- 3 Cisco 1941 Routers (`Rt-Sisli`, `Rt-Atasehir`, `Rt-Sariyer`)
- One Cisco 2960-24TT Switch in each office
- End-user PCs connected to switches
- VLAN segmentation for traffic isolation
- Subnetting based on user count
- OSPF routing protocol between routers
- DHCP configuration for automatic IP assignment

> 🎯 Goal: To create a fully functional enterprise-style network with central and branch offices connected dynamically and logically using Cisco best practices.

---

## ⚙️ Technologies Used and Explanations

### 🔹 VLAN (Virtual LAN)
VLANs allow logical separation of devices within the same physical switch.  
This improves **security**, reduces **broadcast traffic**, and allows **better control** of the network.

### 🔹 Access Ports
Access ports are used when a switch port connects to a single device (like a PC).  
They carry traffic for **one specific VLAN** only.

### 🔹 Trunk Ports
Trunk ports are used between switches and routers (or switch-to-switch connections).  
They allow **multiple VLANs** to pass through using **802.1Q tagging**.

> 🔁 Example: Switch to Router connections are set to trunk so multiple VLANs can communicate with the router via sub-interfaces.

### 🔹 Subnetting / VLSM
Each office has its own IP subnet based on the number of users:

| Office      | Estimated Users | Subnet      |
|-------------|------------------|-------------|
| Ataşehir    | 75               | /25         |
| Sarıyer     | 10               | /28         |
| Central     | 200              | /24         |

This approach **prevents IP waste** and ensures better **IP address planning**.

### 🔹 OSPF (Open Shortest Path First)
OSPF is a dynamic routing protocol that automatically shares route information between routers.  
Each router becomes a neighbor, and the shortest path is calculated dynamically.

### 🔹 DHCP (Dynamic Host Configuration Protocol)
DHCP is configured on routers to assign IP addresses automatically to client devices.  
This simplifies device setup and ensures **no manual IP configuration is needed**.

---

## 💻 Configuration Files

Some router and switch configurations are stored under the `configs/` folder.

You can find the `running-config` of the devices to examine the commands used.

📚 What I Learned

During this project, I learned:

    How to design an office network topology with central and branch sites.

    How to configure VLANs, trunk and access ports on Cisco switches.

    Subnetting with VLSM based on user count.

    How to configure and verify OSPF routing between routers.

    DHCP configuration on routers to automate IP assignments.

    How to use Cisco Packet Tracer to simulate real-life scenarios.
