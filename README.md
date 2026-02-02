\# Home Network intrusion detection system



\## Overview

The aim of this project is to build a small-scale intrusion detection system (IDS) to monitor and analyse network traffic in a home or lab environment.



\## Environment

* Host machine : HP Laptop
* Virtualisation : Oracle VM VirtualBox
* Operating System : Ubuntu Server 24.04 LTS



\## Phase 1 - Environment Setup and Baseline Analysis



\### Environment Setup

* Installed Ubuntu Server 24.04 LTS on VirtualBox
* Configured default NAT networking with DHCP
* Enabled OpenSSH Server
* Verified successful login and system stability



\### Baseline Network Analysis

* Identified active network interfaces using 'ip a'
* Verified outbound connectivity using 'ping'
* Installed 'net-tools' to inspect active services
* Analysed listening services using 'netstat'
* Identified SSH listening port 22 (IPv4 and IPv6)
* Observed DNS services bound to loopback only
* Confirmed minimal default attack prior to IDS deployment



\## Phase 2 - Traffic Capture (Planned)

The next phase of this project will focus on capturing and analysing live network traffic using 'tcpdump'.
This will help establish a baseline for normal traffic patterns before deploying an intrusion detection engine.

* Installed and configured 'tcpdump' for packet capture
* Identified our primary network interface ('enp0s3')
* Captured live ICMP traffic generated using 'ping'
* Observed DNS resolution and background network activity
* Successfully captured bidirectional traffic with zero packet loss
* Established a baseline of normal network behaviour
