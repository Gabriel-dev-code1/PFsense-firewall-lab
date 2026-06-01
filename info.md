Overview

This project demonstrates the implementation of network segmentation and firewall policies using pfSense in a virtualized lab environment.

The objective was to create a controlled network where access to a protected Ubuntu Server is restricted according to the principle of least privilege.

Environment:

-pfSense Firewall
-Kali Linux
-Ubuntu Server
-VirtualBox


Network Architecture:

Kali Linux (192.168.56.103)

↓

pfSense Firewall (192.168.56.2)

↓

Ubuntu Server (192.168.56.110)



Implemented Controls:

-SSH allowed rule-
Allow SSH Access
Protocol: TCP
Destination Port: 22
Source: LAN Subnet
Block Unauthorized Traffic
Protocol: Any
Destination: Ubuntu Server
Action: Pass
Validation Tests
SSH Access

Rule image:

Test on kali:

Nmap ssh open:


-Other traffic blocked rule-
Protocol: TCP
Destination Port: 22
Source: LAN Subnet
Block Unauthorized Traffic
Protocol: Any
Destination: Ubuntu Server
Action: Block

Rule image:



-Http and dns allowed rule-
Rule image:

Test on kali:


-other traffic blocked, example: SMB-

log  SMB timeout:

test on kali:

-Http blocked rule-

Rule image:

test on kali:




Traffic was monitored through pfSense firewall logs to validate policy enforcement.

Security Concepts Demonstrated
Network Segmentation
Firewall Rule Management
Least Privilege Access
Traffic Filtering
Log Analysis
Secure Remote Administration
Screenshots

See the screenshots folder for evidence of configuration and validation tests.
