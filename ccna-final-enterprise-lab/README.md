# CCNA Final Enterprise Lab

## 📌 Overview
This lab simulates a small enterprise network including:
- Core layer, Distribution (Data) layer
- VLAN segmentation
- Inter-VLAN Routing
- Dual ISP connectivity
- IPv4 & IPv6 configuration
- DHCP services

---

## 🖼️ Topology
![topology](topology.jbg)

---

## 🧠 Technologies Used
- VLAN, Trunking
- EtherChannel (PAgP, LACP)
- Inter-VLAN Routing (Router-on-a-Stick)
- Static Routing / Default Route
- IPv4 & IPv6 Dual Stack
- DHCP
- Redundant WAN (2 ISPs)

---

## 🌐 IP Addressing Plan

| Device | Interface | IPv4 Address | IPv6 Address |
|--------|----------|-------------|--------------|
| CORE-1 | F0/1 | 172.16.50.1/24 | 2020:BABA:50::1/64 |
| DATA-1 | G0/2 | 172.16.50.2/24 | 2020:BABA:50::2/64 |
|        | G0/1 | 10.0.1.1/24 | 2020:BABA:200::1/64 |
|        | G0/0 | 192.168.100.1/24 | 2020:BABA:100::1/64 |
| DATA-2 | G0/0 | 192.168.100.2/24 | - |
|        | G0/1 | 10.0.2.2/24 | - |
| GATE   | G0/0 | 10.0.1.3/24 | 2020:BABA:200::3 |
|        | G0/1 | 10.0.2.3/24 | - |
|        | S0/0/0 | 200.209.105.3/24 | 2020:ABCD:105::3/64 |
|        | S0/0/1 | 200.209.109.3/24 | 2020:ABCD:109::3/64 |
| ISP1   | S0/1/0 | 200.209.105.1/24 | 2020:ABCD:105::1/64 |
| ISP2   | S0/1/1 | 200.209.109.1/24 | 2020:ABCD:109::1/64 |

---

## ⚙️ Main Configurations

### 1. VLAN & Trunk
- Create VLAN 10, 20, 30, 40
- Configure trunk between switches
- Allow VLANs on trunk links

---

### 2. EtherChannel
- Configure PAgP on Access switches
- Configure LACP on Distribution switches

---

### 3. Inter-VLAN Routing
- Use Router-on-a-Stick on GATE
- Subinterfaces:
  - G0/2.30 → VLAN 30
  - G0/2.40 → VLAN 40

---

### 4. IP Routing
- Configure static routes between DATA-1, DATA-2, GATE
- Default route from GATE to ISP

---

### 5. IPv6 Configuration
- Assign IPv6 addresses
- Enable routing:

ipv6 unicast-routing


---

### 6. DHCP
- Configure DHCP for:
  - INS
  - Student
  - Guest

---

## 🧪 Verification

### ✔️ Ping Test
- PC → Gateway ✅
- VLAN to VLAN ✅
- Internal → Internet ✅

### ✔️ Routing Table

show ip route
show ipv6 route


---

## 📸 Screenshots (Required)
- Topology
- VLAN configuration
- EtherChannel status
- Routing table
- Ping successful

---

## 🚀 Result
- All VLANs communicate successfully
- Internet access works via ISP
- IPv4 & IPv6 fully functional

---

## 📁 Files
- `Skill-S2.pka`
- `topology.png`
