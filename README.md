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



\## Phase 3 - Intrusion Detection System Deployment

In this phase, the Suricata intrusion destection system (IDS) was deployed to monitor live network traffic and evaluate packets against a predefined set of detection rules.
Suricata was executed in IDS mode on the primary network interface to observe and analyse network activity without actively blocking traffic.



\### Key Activities

* Installed Suricata IDS using the default Ubuntu package repository
* Deployed Suricata in IDS mode on the primary network interface
* Generated normal and scan-based trafffic for testing purposes
* Monitored Suricata log output to evaluate rule processing and event logging



\### Observations

* Suricata successfully processed live network traffic
* Protocol, flow, and statistical events were logged to 'eve.json'
* No alert events were generated during baseline or scan-based testing
* This behaviour is consistent with non-malicious traffic and conservative default rule configurations

The successful logging of traffic statistics and protocol data confirms that Suricata was correctly deployed and actively inspecting network traffic.



\## Phase 4 - Custom Intrusion Detection Rule Development

In this phase, a custom Suricata intrusion detection rule was developed to demonstrate signature-based detection and alert generation.

A custom ICMP rule was written to detect ICMP echo request traffic. Live network traffic was first captured usin tcpdump and then replayed through Suricata using PCAP analysis mode. This approach allowed controlled, repeatable testing of the detection rule.



\### Key Activities

* Created a custom Suricata rule to detect ICMP echo requests
* Assigned a unique SID to the custom rule for identification
* Captured real network traffic using tcpdump
* Replayed captured traffic through Suricata for offline analysis
* Successfully triggered and verified alerts in both fast.log and eve.json



\### Result

* The custom rule successfully generated alerts when matching traffic was detected, confirming correct rule syntax, rule loading and IDS functionality.
* This phase demonstrates practical understanding of signature-based intrusion detection and alert validation.