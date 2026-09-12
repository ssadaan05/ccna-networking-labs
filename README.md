# CCNA & Network Security Labs

Hands-on networking and security labs performed in **Cisco Packet Tracer** (and **Kali Linux** for attack simulations), covering CCNA-level routing, switching, network architecture, and offensive/defensive security techniques.

---

## 📖 Table of Contents

- [Fundamentals](#-fundamentals)
- [IP Connectivity & Routing](#-ip-connectivity--routing)
- [Switching](#-switching)
- [Security & Access Control](#-security--access-control)
- [Network Attacks & Mitigation](#-network-attacks--mitigation-kali-linux)
- [Site-to-Site VPN (IPsec)](#-site-to-site-vpn-ipsec)
- [Cryptographic Hashing](#-cryptographic-hashing)
- [Discovery Protocols](#-discovery-protocols)
- [Virtualization & Containers](#-virtualization--containers)
- [Wireless](#-wireless)
- [Network Architecture Concepts](#-network-architecture-concepts)

---

## 🧱 Fundamentals

- Cisco device classes (SOHO/SMB, Enterprise, Datacenter, Service Provider) and modular vs. fixed-configuration hardware
- Cisco IOS variants — IOS, IOS-XE, NX-OS, IOS-XR
- Router/switch memory types — ROM, Flash, RAM, NVRAM
- Device access methods — Console, AUX, CLI
- Configuration methods and the device boot process
- Cisco CLI, context-sensitive help, and EXEC modes

## 🌐 IP Connectivity & Routing

- Basic IPv4 addressing and connectivity on branch routers
- Basic IPv6 addressing, connectivity, and stateless autoconfiguration (SLAAC)
- IPv4 static & default routing (branch + head-office routers)
- IPv6 static & default routing
- Single-area OSPF configuration, router-ID assignment, passive-interface, and verification

## 🔀 Switching

- Switch operation and MAC address learning
- VLAN fundamentals — default allocation, VLAN creation, port assignment, management VLAN
- Trunking — DTP auto-negotiation, manual trunk configuration, 802.1Q encapsulation
- Inter-VLAN routing — Router-on-a-Stick and L3 switch (SVI) methods
- Spanning Tree Protocol — root bridge behavior, root bridge election, PortFast
- EtherChannel — PAgP, LACP, and protocol-less (static) bundling
- Port security with static MAC address limiting

## 🔐 Security & Access Control

- Standard and extended access control lists (ACLs)
- Static NAT and dynamic overload NAT (PAT)
- Securing console and remote access with SSH (SSHv2, RSA key pairs, VTY hardening)
- AAA authentication — local (privilege-level accounts) and server-based (RADIUS/TACACS+)
- RIPv2 authentication

## 🛡️ Network Attacks & Mitigation (Kali Linux)

Offensive simulations paired with the corresponding Cisco IOS mitigation for each.

- **Smurf Attack — Reflection:** Spoofed a victim router's IP as the source of ICMP echo requests, redirecting replies to the victim instead of the sender.
- **Smurf Attack — Amplification:** Enabled `ip directed-broadcast` on an intermediate router and sent a spoofed ICMP request to a subnet broadcast address, causing every host on that subnet to reply to the victim at once — a DDoS amplification pattern. Mitigated with `no ip directed-broadcast` and edge filtering of spoofed source addresses.
- **CDP Flooding:** Used Yersinia to flood a switch's CDP table with forged neighbor advertisements. Mitigated by disabling CDP on untrusted/access-facing ports.
- **DTP (Dynamic Trunking Protocol) Attack:** Spoofed a Kali host as a switch to negotiate an unauthorized trunk link, which would otherwise grant access to all VLANs on that trunk. Mitigated with `switchport mode access` / `switchport nonegotiate`.
- **MAC/CAM Table Flooding:** Flooded a switch's MAC address table with forged entries to force fail-open (hub-like) behavior. Mitigated using port security with static/limited MAC counts per port.
- **IP Spoofing & OSPF Route Injection:** Used Loki (Kali) to discover OSPF neighbors, spoof as a router, and inject a malicious route into legitimate routing tables. Mitigated with OSPF neighbor authentication (MD5/SHA) and passive-interface on untrusted segments.
- **Password Brute-Forcing:** Brute-forced basic router authentication from Kali, reinforcing the case for strong passwords, AAA with lockout policies, and SSH-only remote access.

## 🔒 Site-to-Site VPN (IPsec)

Built a site-to-site IPsec VPN tunnel between two branch routers across a simulated ISP (a third router acting as the provider network), encrypting traffic between branch subnets as it traverses untrusted transit infrastructure — verified end-to-end reachability before and after tunnel establishment.

## 🧮 Cryptographic Hashing

Explored hashing algorithms (MD5, SHA-1, SHA-2/256) in the context of routing protocol authentication (RIPv2) — covering how hashing provides integrity verification, why MD5 is now considered weak, and why SHA-256 is preferred in modern security contexts.

## 🔍 Discovery Protocols

- Neighbor discovery using CDP and LLDP
- Duplex mismatch detection via CDP

## 🖥️ Virtualization & Containers

- Creating virtual machines on a Type 1 (bare-metal) hypervisor
- Creating virtual machines on a Type 2 (hosted) hypervisor
- Building and operating containers

## 📡 Wireless

- Basic L3 switch configuration and DHCP server setup
- Wireless LAN Controller (WLC) configuration and LWAP registration
- SSID creation with local authentication
- SSID authentication via a AAA/RADIUS server

## 🏗️ Network Architecture Concepts

- **Three-Tier Architecture** — Core, Distribution, and Access layer design used in traditional campus/enterprise networks
- **Leaf-Spine Architecture** — Non-blocking, low-latency data center topology where every leaf switch connects to every spine switch, commonly used in modern data centers over the traditional three-tier model

---

## ⚠️ Disclaimer

All attacks were performed exclusively in isolated Cisco Packet Tracer lab environments for educational purposes. None of these techniques were used against production networks or systems without authorization.

## 🛠️ Tools Used

Cisco Packet Tracer · Kali Linux (Yersinia, Loki, brute-force tools) · SSH · IPsec

## 📫 Connect

[LinkedIn](https://www.linkedin.com/in/mohammed-sadaan-shaikh-810482152/)
