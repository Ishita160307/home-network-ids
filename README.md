\# Home Network intrusion detection system



\## Overview

The aim of this project is to build a small-scale intrusion detection system (IDS) to monitor and analyse network traffic in a home or lab environment.



\## Environment

* Host machine : HP Laptop
* Virtualisation : Oracle VM VirtualBox
* Operating System : Ubuntu Server 24.04 LTS



\## Day 1 - Environment Setup

* Installed Ubuntu Server 24.04 LTS in VirtualBox
* Configured default NAT networking with DHCP
* Enabled OpenSSH Server
* Verified successful login and system stability



\## Day 2 - Network Behaviour Analysis

* Verified outbound connectivity using 'ping'
* Installed 'net-tools- to inspect active services
* Identified SSH listening port 22 (IPv4 and IPv6)
* Observed DNS services bound to loopback only
* Confirmed minimal default attack prior to IDS deployment





