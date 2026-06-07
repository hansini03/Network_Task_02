# Networking Task 02: Network Devices & IP Addressing
**Date:** June 7, 2026  
**Intern:** Hansini Kulal  
---
## 🎯 Task Objectives
* Understand common network devices, their operational mechanisms, and real-world applications.
* Classify IP addresses into Public and Private categories with technical reasoning.
* Analyze local device network parameters and understand foundational DNS/Router roles.
* Map and document the step-by-step network communication flow when accessing a website.
* Execute network diagnostic commands (`ipconfig /all`, `nslookup`, `ping`) and analyze outputs.
---
## 🔬 Part A: Network Devices Research
### 1. Router
* **Purpose:** Connects multiple distinct networks (like your home local network and the internet) and routes data packets between them.
* **How it works:** It operates at Layer 3 (Network Layer) of the OSI model.It inspects the destination IP address of incoming data packets and uses routing tables to determine the most efficient path to send them forward.
* **Real-world usage:** The dual-band Wi-Fi router installed in your home by your Internet Service Provider (ISP) to give all your devices internet access.
### 2. Switch
* **Purpose:** Connects multiple devices together within the same Local Area Network (LAN) to share resources efficiently.
* **How it works:** Operates at Layer 2 (Data Link Layer).It learns and uses the hardware MAC addresses of connected devices to forward data packets only to the specific device they are intended for, avoiding network congestion.
* **Real-world usage:** Used in school computer labs or office floors to physically connect dozens of desktop PCs, printers, and local servers together via Ethernet cables.
### 3. Hub
* **Purpose:** A basic legacy networking device used to connect multiple devices in a local network.
* **How it works:** Operates at Layer 1 (Physical Layer).It has no intelligence; when it receives data on one port, it blindly broadcasts (copies) that data to all other ports, regardless of the intended destination. This causes data collisions and security issues.
* **Real-world usage:** Mostly obsolete today, but occasionally used in simple laboratory testing environments or legacy networks where traffic monitoring/sniffing on all ports is explicitly required.
### 4. Access Point (AP)
* **Purpose:** Extends an existing wired network by adding wireless (Wi-Fi) connectivity capabilities to it.
* **How it works:** It plugs directly into a wired router or switch via an Ethernet cable and projects a wireless radio signal, allowing devices to connect to the local network without physical cables.
* **Real-world usage:** Large office buildings, hotels, or college campuses install multiple wireless Access Points on ceilings to provide uninterrupted Wi-Fi coverage across huge areas.
### 5. Firewall
* **Purpose:** Acts as a security barrier that monitors and controls incoming and outgoing network traffic based on predetermined security rules.
* **How it works:** It inspects data packets passing through the network perimeter. Based on filters like IP address, port numbers, or protocols, it either permits safe traffic or blocks malicious/unauthorized traffic.
* **Real-world usage:** Windows Defender Firewall running on your PC blocking unauthorized applications from communicating with the internet, or corporate firewalls preventing hackers from accessing internal company networks.
### 6. Modem (Modulator-Demodulator)
* **Purpose:** Converts data signals between an internet service provider’s infrastructure and a local digital home network.
* **How it works:** It modulates digital data from a computer into analog signals to travel over telephone, fiber, or coaxial lines, and demodulates incoming analog signals back into digital data for your router to understand.
* **Real-world usage:** The physical box connected to the external fiber-optic or cable line coming into your house, translating the internet signal before passing it to your Wi-Fi router.
---
## 🏷️ Part B: IP Address Classification

| IP Address | Category | Technical Reasoning / Explanation |
| :--- | :--- | :--- |
| **192.168.1.10** | **Private** | Belongs to the Class C private IP range (`192.168.0.0` to `192.168.255.255`), reserved for local area networks. |
| **10.0.0.5** | **Private** | Belongs to the Class A private IP range (`10.0.0.0` to `10.255.255.255`), commonly used in large internal or enterprise networks. |
| **172.16.5.20** | **Private** | Belongs to the Class B private IP range (`172.16.0.0` to `172.31.255.255`), reserved for internal infrastructure. |
| **8.8.8.8** | **Public** | A globally unique routable IP address owned by Google, hosting their free public Anycast DNS service over the internet. |
| **1.1.1.1** | **Public** | A globally unique routable IP address owned by Cloudflare, used for their public internet DNS directory service. |
| **192.168.100.1** | **Private** | Belongs to the Class C private IP block, frequently assigned as the default gateway IP for local home router login page. |

---
## 🖥️ Part C: Understanding Your Network
### Local Device Network Parameters:
* **IPv4 Address:** 10.144.211.176
* **Default Gateway:** 10.144.211.120
* **DNS Server:** 8.8.8.8
### Network Setup Screenshot:
<img width="1100" height="615" alt="Screenshot 2026-06-07 220150" src="https://github.com/user-attachments/assets/cf95f470-2f4d-42da-aacc-2b1810e08738" />

### Analysis Questions:
1. **Which IP range does your device belong to?** My device belongs to the Class A Private IP range (`10.0.0.0` to `10.255.255.255`).
2. **Is it Public or Private?** It is a Private IP address, meaning it is used within a local network and is not directly accessible from the internet.
3. **What role does your router play in your network?** The router serves as the central gateway, directing traffic from the local network to external networks and performing NAT to mask private IPs.
4. **What would happen if the DNS server stopped working?** If the DNS server stopped working, domain names (like google.com) would no longer resolve to IP addresses, breaking web browsing by name, though raw IP communication would still function.
---
## 🗺️ Part D: Network Communication Flow
Below is the sequence of events that takes place when accessing **www.google.com**:
* **Step 1:** The local device sends a DNS request to the configured DNS Server to resolve the domain name `www.google.com` into an IP address.
* **Step 2:** The DNS Server responds back to the device with the resolved destination IP address (`2404:6800:4009:80a::200e`).
* **Step 3:** The device encapsulates the data and forwards packets to the local Default Gateway Router.
* **Step 4:** The Router routes the packet across external ISP gateways to the destination Google Server.
* **Step 5:** The Google Server processes the request and sends the response packets back across the router to the device, allowing the webpage to render.
---
## ⚡ Part E: Practical Command Exercise
### Diagnostic Execution Screenshot (Ping & Nslookup):
<img width="858" height="377" alt="Screenshot 2026-06-07 220500" src="https://github.com/user-attachments/assets/33455dc1-6dcc-4df6-b372-5fff1a231bdc" />
<img width="503" height="391" alt="Screenshot 2026-06-07 233554" src="https://github.com/user-attachments/assets/c0d62fb2-b150-45f4-aaa4-76fd7fbe6813" />


### Command Outputs & Observations:
1. **What IP address did DNS return for Google?** The DNS resolution returned the IPv6 destination address `2404:6800:4009:80a::200e` for google.com.
2. **Was the ping successful?** Yes, the ping was successful with 0% packet loss, 4 packets sent, 4 received, and an average round-trip latency of 126ms.
3. **Why is DNS important before communication begins?** DNS is essential because network devices and servers rely exclusively on numerical or hexadecimal IP addresses to route packets, meaning name resolution must occur before any host-to-host data exchange can start.
