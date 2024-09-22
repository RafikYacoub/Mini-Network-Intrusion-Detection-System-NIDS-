# Mini Network Intrusion Detection System (NIDS)

This project implements a **mini Network Intrusion Detection System (NIDS)**, designed to detect suspicious activities such as port scanning and network intrusions by analyzing network traffic. The NIDS is built using **Python** and leverages the **Scapy** library for packet inspection.

## Project Overview

The purpose of this project is to provide a functional tool that detects network threats by monitoring TCP packets, identifying malicious scanning activities, and flagging any potential attacks. The system simulates a real-world scenario where malicious attackers attempt to breach the network, and the NIDS blocks or alerts the network administrator when such activities occur.

## Features

1. **TCP Header Analysis**: The system examines the TCP headers of network packets to identify different types of scanning and intrusion attempts.
   
2. **Port Scanning Detection**: Implements detection for multiple port scanning techniques, including:
   - TCP Stealth Scan
   - TCP NULL Scan
   - FIN Scan
   - Xmas Scan

3. **Nikto Scanner Detection**: Identifies attempts by attackers using the **Nikto** web server scanner to find vulnerabilities in the network.

4. **Geolocation-Based Detection**: Detects and flags attacks originating from **Antarctica** by checking the source IP range.

5. **Custom Features**: Includes additional functionality such as logging, customizable alerts, and the ability to block suspicious traffic.

## How It Works

The NIDS analyzes packet capture files (.pcap format) using the **Scapy** library. It checks for specific flags, patterns, and signatures commonly used in various scanning techniques. The system generates real-time alerts when potential threats are detected.

### Input:
The system accepts a pcap file as input for analysis:
```bash
python miniNIDS.py test.pcap

