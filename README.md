# Networking Task 02: Network Devices & IP Addressing
**Date:** June 7, 2026  
**Intern:** Hansini Kulal  
---
## 🎯 Task Objectives
* [span_1](start_span)Understand common network devices, their operational mechanisms, and real-world applications[span_1](end_span).
* [span_2](start_span)Classify IP addresses into Public and Private categories with technical reasoning[span_2](end_span).
* [span_3](start_span)Analyze local device network parameters and understand foundational DNS/Router roles[span_3](end_span).
* [span_4](start_span)Map and document the step-by-step network communication flow when accessing a website[span_4](end_span).
* [span_5](start_span)Execute network diagnostic commands (`ipconfig /all`, `nslookup`, `ping`) and analyze outputs[span_5](end_span).
---
## 🔬 Part A: Network Devices Research
### 1. Router
* **[span_6](start_span)Purpose:** Connects multiple distinct networks (like your home local network and the internet) and routes data packets between them[span_6](end_span).
* **[span_7](start_span)How it works:** It operates at Layer 3 (Network Layer) of the OSI model[span_7](end_span). [span_8](start_span)It inspects the destination IP address of incoming data packets and uses routing tables to determine the most efficient path to send them forward[span_8](end_span).
* **Real-world usage:** The dual-band Wi-Fi router installed in your home by your Internet Service Provider (ISP) to give all your devices internet access.
### 2. Switch
* **[span_9](start_span)Purpose:** Connects multiple devices together within the same Local Area Network (LAN) to share resources efficiently[span_9](end_span).
* **How it works:** Operates at Layer 2 (Data Link Layer). [span_10](start_span)It learns and uses the hardware MAC addresses of connected devices to forward data packets only to the specific device they are intended for, avoiding network congestion[span_10](end_span).
* **[span_11](start_span)Real-world usage:** Used in school computer labs or office floors to physically connect dozens of desktop PCs, printers, and local servers together via Ethernet cables[span_11](end_span).
### 3. Hub
* **[span_12](start_span)Purpose:** A basic legacy networking device used to connect multiple devices in a local network[span_12](end_span).
* **How it works:** Operates at Layer 1 (Physical Layer). [span_13](start_span)It has no intelligence; when it receives data on one port, it blindly broadcasts (copies) that data to all other ports, regardless of the intended destination[span_13](end_span). This causes data collisions and security issues.
* **[span_14](start_span)Real-world usage:** Mostly obsolete today, but occasionally used in simple laboratory testing environments or legacy networks where traffic monitoring/sniffing on all ports is explicitly required[span_14](end_span).
### 4. Access Point (AP)
* **[span_15](start_span)Purpose:** Extends an existing wired network by adding wireless (Wi-Fi) connectivity capabilities to it[span_15](end_span).
* **[span_16](start_span)How it works:** It plugs directly into a wired router or switch via an Ethernet cable and projects a wireless radio signal, allowing devices to connect to the local network without physical cables[span_16](end_span).
* **[span_17](start_span)Real-world usage:** Large office buildings, hotels, or college campuses install multiple wireless Access Points on ceilings to provide uninterrupted Wi-Fi coverage across huge areas[span_17](end_span).
### 5. Firewall
* **[span_18](start_span)Purpose:** Acts as a security barrier that monitors and controls incoming and outgoing network traffic based on predetermined security rules[span_18](end_span).
* **How it works:** It inspects data packets passing through the network perimeter. [span_19](start_span)Based on filters like IP address, port numbers, or protocols, it either permits safe traffic or blocks malicious/unauthorized traffic[span_19](end_span).
* **[span_20](start_span)Real-world usage:** Windows Defender Firewall running on your PC blocking unauthorized applications from communicating with the internet, or corporate firewalls preventing hackers from accessing internal company networks[span_20](end_span).
### 6. Modem (Modulator-Demodulator)
* **[span_21](start_span)Purpose:** Converts data signals between an internet service provider’s infrastructure and a local digital home network[span_21](end_span).
* **[span_22](start_span)How it works:** It modulates digital data from a computer into analog signals to travel over telephone, fiber, or coaxial lines, and demodulates incoming analog signals back into digital data for your router to understand[span_22](end_span).
* **[span_23](start_span)Real-world usage:** The physical box connected to the external fiber-optic or cable line coming into your house, translating the internet signal before passing it to your Wi-Fi router[span_23](end_span).
---
## 🏷️ Part B: IP Address Classification

| IP Address | Category | Technical Reasoning / Explanation |
| :--- | :--- | :--- |
| **192.168.1.10** | **Private** | [span_24](start_span)Belongs to the Class C private IP range (`192.168.0.0` to `192.168.255.255`), reserved for local area networks[span_24](end_span). |
| **10.0.0.5** | **Private** | [span_25](start_span)Belongs to the Class A private IP range (`10.0.0.0` to `10.255.255.255`), commonly used in large internal or enterprise networks[span_25](end_span). |
| **172.16.5.20** | **Private** | [span_26](start_span)Belongs to the Class B private IP range (`172.16.0.0` to `172.31.255.255`), reserved for internal infrastructure[span_26](end_span). |
| **8.8.8.8** | **Public** | [span_27](start_span)A globally unique routable IP address owned by Google, hosting their free public Anycast DNS service over the internet[span_27](end_span). |
| **1.1.1.1** | **Public** | [span_28](start_span)A globally unique routable IP address owned by Cloudflare, used for their public internet DNS directory service[span_28](end_span). |
| **192.168.100.1** | **Private** | [span_29](start_span)Belongs to the Class C private IP block, frequently assigned as the default gateway IP for local home router login pages[span_29](end_span). |

---
## 🖥️ Part C: Understanding Your Network
### Local Device Network Parameters:
* **[span_30](start_span)IPv4 Address:** 10.144.211.176[span_30](end_span)
* **[span_31](start_span)Default Gateway:** 10.144.211.120[span_31](end_span)
* **[span_32](start_span)DNS Server:** *Not Listed* (Configured automatically by local DHCP network)[span_32](end_span)
### Network Setup Screenshot:
<img width="1100" height="615" alt="Screenshot 2026-06-07 220150" src="https://github.com/user-attachments/assets/cf95f470-2f4d-42da-aacc-2b1810e08738" />

### Analysis Questions:
1. **[span_33](start_span)[span_34](start_span)Which IP range does your device belong to?** My device belongs to the Class A Private IP range (`10.0.0.0` to `10.255.255.255`)[span_33](end_span)[span_34](end_span).
2. **[span_35](start_span)[span_36](start_span)Is it Public or Private?** It is a Private IP address, meaning it is used within a local network and is not directly accessible from the internet[span_35](end_span)[span_36](end_span).
3. **[span_37](start_span)[span_38](start_span)What role does your router play in your network?** The router serves as the central gateway, directing traffic from the local network to external networks and performing NAT to mask private IPs[span_37](end_span)[span_38](end_span).
4. **[span_39](start_span)[span_40](start_span)What would happen if the DNS server stopped working?** If the DNS server stopped working, domain names (like google.com) would no longer resolve to IP addresses, breaking web browsing by name, though raw IP communication would still function[span_39](end_span)[span_40](end_span).
---
## 🗺️ Part D: Network Communication Flow
[span_41](start_span)Below is the sequence of events that takes place when accessing **www.google.com**[span_41](end_span):
* **[span_42](start_span)Step 1:** The local device sends a DNS request to the configured DNS Server to resolve the domain name `www.google.com` into an IP address[span_42](end_span).
* **[span_43](start_span)Step 2:** The DNS Server responds back to the device with the resolved destination IP address (`2404:6800:4009:80a::200e`)[span_43](end_span).
* **[span_44](start_span)Step 3:** The device encapsulates the data and forwards packets to the local Default Gateway Router[span_44](end_span).
* **[span_45](start_span)Step 4:** The Router routes the packet across external ISP gateways to the destination Google Server[span_45](end_span).
* **[span_46](start_span)Step 5:** The Google Server processes the request and sends the response packets back across the router to the device, allowing the webpage to render[span_46](end_span).
---
## ⚡ Part E: Practical Command Exercise
### Diagnostic Execution Screenshot (Ping & Nslookup):
<img width="858" height="377" alt="Screenshot 2026-06-07 220500" src="https://github.com/user-attachments/assets/33455dc1-6dcc-4df6-b372-5fff1a231bdc" />
<img width="503" height="391" alt="Screenshot 2026-06-07 233554" src="https://github.com/user-attachments/assets/c0d62fb2-b150-45f4-aaa4-76fd7fbe6813" />


### Command Outputs & Observations:
1. **[span_47](start_span)What IP address did DNS return for Google?** The DNS resolution returned the IPv6 destination address `2404:6800:4009:80a::200e` for google.com[span_47](end_span).
2. **[span_48](start_span)Was the ping successful?** Yes, the ping was successful with 0% packet loss, 4 packets sent, 4 received, and an average round-trip latency of 126ms[span_48](end_span).
3. **[span_49](start_span)Why is DNS important before communication begins?** DNS is essential because network devices and servers rely exclusively on numerical or hexadecimal IP addresses to route packets, meaning name resolution must occur before any host-to-host data exchange can start[span_49](end_span).
