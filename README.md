# Home Wireless Router Network Project (Cisco Packet Tracer)

## 🛰️ Project Overview

This project demonstrates a wireless home and enterprise network setup using **Cisco Packet Tracer**. The topology is designed with the integration of wireless and wired networks connected through OSPF routing, allowing smooth communication between all devices across different zones.

---

## 🧱 Topology Components

### 🔵 Home Network (Purple Zone)
- **Devices:**
  - Laptop0
  - Laptop1
  - Smartphone0
- **Wireless Router:** `HomeRouter-PT-AC`
- **Connected to Router0 via FastEthernet0/0` (IP: 192.168.2.1)`

### 🔷 Office Network (Blue Zone)
- **Devices:**
  - Laptop2
  - Smartphone1
  - Server0
- **Access Point & Switch:** For wireless and wired connectivity
- **Router0 (R0):** Connected to:
  - Wireless Router (Home) via Fa0/0 (IP: 192.168.2.1)
  - Office Switch via Fa0/1 (IP: 10.0.0.1)

### 🟢 Server Network (Green Zone)
- **Devices:**
  - Server1
  - Server2
- **Switch Connected to Router2 (R2):** Internal communication for the server zone

---

## 🔁 Routing Configuration: OSPF

All routers (Router0, Router1, Router2) are connected using serial interfaces and OSPF routing is used to enable communication across different networks.

### 🔧 OSPF Setup Example

```bash
Router(config)# router ospf 1
Router(config-router)# network 192.168.3.0 0.0.0.255 area 0
Router(config-router)# network 192.168.2.0 0.0.0.255 area 0
Router(config-router)# network 192.168.1.0 0.0.0.255 area 0
```

Repeat OSPF setup on each router with the appropriate networks.

---

## 📡 IP Addressing Scheme

| Device/Interface     | IP Address       | Purpose              |
|----------------------|------------------|-----------------------|
| Wireless Router      | 192.168.2.1      | Home Gateway          |
| Router0 (Fa0/0)      | 192.168.2.1      | Connects Home         |
| Router0 (Fa0/1)      | 192.168.1.1      | Office Network        |
| Router0 (Serial)     | 192.168.3.1      | To Router1            |
| Router1 (Serial)     | 192.168.3.2      | To Router0            |
| Router1 (Serial)     | 192.168.4.1      | To Router2            |
| Router2 (Serial)     | 192.168.4.2      | To Router1            |
| Router2 (Fa0/0)      | 192.168.5.1      | Server Network        |

> 📝 All end devices have IPs assigned based on subnet and gateway associated.

---

## 🌐 Connectivity Check

Use `ping` or `tracert` on any PC or server to check network connectivity and routing.

Example:

```bash
ping 192.168.5.1
```

---

## 📁 File

Packet Tracer File: `homewirelessrouter.pkt`

---

## 🔗 Usage

1. Open `homewirelessrouter.pkt` in Cisco Packet Tracer.
2. Verify interface IPs and OSPF configuration.
3. Use simulation mode to observe packet flow.
4. Ping across zones to test routing.

---

## 📌 Author

Created by **Harshit Gujjar** – [GitHub](https://github.com/Harshitsss)

---
