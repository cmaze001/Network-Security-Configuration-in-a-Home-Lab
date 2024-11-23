# Network-Security-Configuration-in-a-Home-Lab
Tools Used:
pfSense: A powerful open-source firewall/router used to secure and segment the home network.
Wireshark: A network protocol analyzer to monitor and capture network traffic for analysis.
Nmap: A network scanning tool to identify vulnerabilities and open ports within the network.
Project Description:

This project demonstrates the configuration and management of network security in a home lab. By using pfSense as a firewall/router, I was able to secure my home network and configure rules to prevent unauthorized access. I also used Wireshark to capture and analyze network traffic, ensuring safe communication within the network. Additionally, regular network scans with Nmap were run to discover vulnerabilities and improve network security.

Steps:
pfSense Configuration:
Installed pfSense as the main router/firewall on the home network.
Set up different network segments (LAN, DMZ, and guest network) to separate traffic types and ensure proper security.
Configured firewall rules to block unsolicited inbound connections and limit outbound traffic to trusted IPs.
Wireshark Setup:
Installed Wireshark on key devices to monitor and capture traffic, particularly focusing on identifying potential threats and analyzing unusual traffic patterns.
Network Scanning with Nmap:
Ran regular Nmap scans to identify open ports and services within the network.
Analyzed scan results and adjusted pfSense firewall rules to block unnecessary or potentially vulnerable services.

Outcome:
Successfully segmented network traffic to ensure secure communication between different devices and networks.
Blocked unsolicited inbound connections, significantly reducing the potential attack surface.
Gained hands-on experience in configuring firewalls, managing network security, and analyzing network traffic for vulnerabilities.

Key Takeaways:
Importance of network segmentation in improving security.
Experience in configuring firewall rules to prevent unauthorized access.
Understanding of network monitoring and traffic analysis with tools like Wireshark.
Practical experience using Nmap to scan for vulnerabilities and improve network defenses.

Files:
pfSense configuration export
Wireshark capture samples
Nmap scan reports

Future Improvements:
Implement VPN for secure remote access.
Set up IDS/IPS for deeper network threat detection.
Continue refining firewall rules based on further traffic analysis.
