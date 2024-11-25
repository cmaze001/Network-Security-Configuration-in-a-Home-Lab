# Network-Security-Configuration-in-a-Home-Lab

## Overview

This project demonstrates the configuration and management of network security in a home lab using **pfSense**, **Wireshark**, and **Nmap**. The goal of this lab is to secure my home network by configuring pfSense as a firewall/router, segmenting network traffic, and monitoring the network for potential vulnerabilities.

## Tools Used
- **pfSense**: A powerful open-source firewall/router used to secure and segment the home network.
- **Wireshark**: A network protocol analyzer to monitor and capture network traffic for analysis.
- **Nmap**: A network scanning tool to identify vulnerabilities and open ports within the network.

## Objectives
- Configure pfSense to secure the home network and manage firewall rules.
- Use Wireshark to capture and analyze network traffic.
- Run regular Nmap scans to identify vulnerabilities and optimize firewall rules.

## Steps

### 1. pfSense Configuration
- **Install pfSense**: Set up pfSense on a dedicated machine to act as the router/firewall.
- **WAN and LAN Setup**: Configure the WAN interface to obtain an IP via DHCP and the LAN interface with a static IP (`192.168.1.1/24`).
- **Firewall Rules**: Create rules to block unsolicited inbound connections while allowing necessary services like HTTP (port 80) and HTTPS (port 443).
  
  Example of LAN rule to allow HTTP traffic:
  ```xml
  <rule>
    <interface>lan</interface>
    <source>any</source>
    <destination>any</destination>
    <protocol>TCP</protocol>
    <port>80</port>
    <action>pass</action>
    <descr>Allow HTTP traffic</descr>
  </rule>
  ```

- **NAT Configuration**: Set up outbound NAT to allow devices on the LAN to access the internet.
  
  Example of Outbound NAT rule:
  ```xml
  <rule>
    <interface>wan</interface>
    <source>192.168.1.0/24</source>
    <natport>any</natport>
    <target>any</target>
    <descr>Outbound NAT for LAN</descr>
  </rule>
  ```

### 2. Wireshark Traffic Capture
- Install Wireshark on a device within the network to capture network traffic.
- Set up Wireshark to filter specific traffic (e.g., HTTP, HTTPS, DNS, etc.).
  
  Example filter for HTTP traffic:
  ```
  tcp.port == 80
  ```
- Capture traffic between the pfSense router and the internal devices. Save the capture files (`.pcap`) for future analysis.

### 3. Nmap Network Scanning
- Use Nmap to scan devices within the local network for open ports and vulnerabilities.
  
  Example Nmap command to scan a specific device:
  ```bash
  nmap -v -sS 192.168.1.10
  ```

- Regularly run Nmap scans to monitor for new open ports or services and adjust firewall rules accordingly.

  Example Nmap output:
  ```plaintext
  Starting Nmap 7.80 ( https://nmap.org ) at 2024-11-23 12:34 PST
  Initiating SYN Stealth Scan at 12:34
  Scanning 192.168.1.10 [1000 ports]
  Discovered open port 22/tcp on 192.168.1.10
  Discovered open port 80/tcp on 192.168.1.10
  Discovered open port 443/tcp on 192.168.1.10

  Nmap scan report for 192.168.1.10
  Host is up (0.00014s latency).
  Not shown: 997 closed ports
  PORT    STATE SERVICE
  22/tcp  open  ssh
  80/tcp  open  http
  443/tcp open  https
  ```


## Outcome
- Successfully segmented the network traffic into different zones (LAN, DMZ, etc.) for enhanced security.
- Blocked unsolicited inbound connections and set up appropriate outbound rules.
- Gained hands-on experience in configuring firewalls, traffic analysis, and network vulnerability scanning.

## Future Improvements
- **VPN Setup**: Configure a VPN server for secure remote access to the home network.
- **IDS/IPS Integration**: Implement an Intrusion Detection and Prevention System (IDS/IPS) for more advanced threat detection.
- **Enhanced Monitoring**: Set up a monitoring system (e.g., SNMP, Syslog) for continuous tracking of network traffic and events.


