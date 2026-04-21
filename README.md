# pfsense-beginner-project
Mini projet cybersécurité : mise en place d’un firewall pfSense et simulation de tests réseau avec Kali Linux (scan nmap)/Cybersecurity project focused on configuring a pfSense firewall and testing its security through network scans using Kali Linux

## Network Architecture

The lab environment was created using VirtualBox with the following setup:

- pfSense → Firewall (WAN + LAN)
- Kali Linux → Client machine (simulating an attacker)


Kali Linux (192.168.1.10) → pfSense (192.168.1.1) → Internet


---

**Configuration Steps**

# 1. Network Setup#
- pfSense configured with:
  - WAN → NAT
  - LAN → Internal Network (LAN)
- Kali Linux connected to the same internal network

---

### 2. Connectivity Test

The `ping` command was used to verify communication between Kali and pfSense:

```bash
ping 192.168.1.1

Result: Successful communication between both machines.

# 3. Network Scan#

A scan was performed using Nmap:

nmap 192.168.1.1

Open ports detected:

80/tcp (HTTP)
53/tcp (DNS)
**4. Mise en place d’une règle firewall**

A firewall rule was created to block HTTP access:

Action → Block
Protocol → TCP
Destination → This Firewall
Port → 80
**5. Security Observation**

Despite the rule, port 80 remained accessible.

_Reason:_
pfSense includes a default anti-lockout rule that prevents administrators from being locked out of the web interface.

Key Learnings
Understanding how a firewall controls network traffic
Using ping for connectivity testing
Using nmap for network scanning
Troubleshooting DHCP issues
Understanding firewall rule priority
Learning about pfSense anti-lockout protection
Troubleshooting

During the project, a DHCP issue occurred:

Kali Linux received an APIPA address (169.254.x.x)
This indicated that no DHCP server was responding

_Solution:_
A static IP was manually assigned:

sudo ip addr add 192.168.1.10/24 dev eth0
Screenshots

Screenshots of the project are available in the screenshots/ folder:

Ping test
Nmap scan results
Firewall rule configuration
Conclusion

This project demonstrates a complete basic cybersecurity workflow:

Network configuration
Connectivity testing
Network scanning
Firewall rule implementation
Security analysis

It provides a solid introduction to firewall management and network security concepts.
