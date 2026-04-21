# pfsense-beginner-project
Mini projet cybersécurité : mise en place d’un firewall pfSense et simulation de tests réseau avec Kali Linux (scan nmap)/Cybersecurity project focused on configuring a pfSense firewall and testing its security through network scans using Kali Linux

**Introduction**

This project demonstrates the setup of a pfSense firewall and basic network security testing using Kali Linux.

 **Network Setup**

A local network was created using VirtualBox, with pfSense acting as a firewall and Kali Linux as a client machine.

**Connectivity Test**

The ping command was used to verify communication between the two machines.

**Network Scan**

Nmap was used to identify open ports on the firewall.

**Security Implementation**

A firewall rule was created to block HTTP access.

**Observation**

The HTTP port remained open due to the default anti-lockout rule in pfSense.

**Conclusion**

This project demonstrates how firewall rules, network configuration, and security analysis work together.
it highlights real-world troubleshooting, including DHCP issues and firewall rule behavior.
