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
```

### Output:
When suspicious activities are detected, the system generates alerts with the following format:
```bash
Alert: [Event Name], Source IP: [Source IP], Destination IP: [Destination IP]
```

### Detected Events:
- **Port Scanning**: Identifies common scanning methods based on manipulation of TCP flags.
- **Nikto Scanning**: Scans for raw packet signatures indicative of the Nikto web server scanner.
- **Antarctica-Based Attacks**: Alerts if any packets originate from IP addresses assigned to Antarctica.

---

## System Requirements

- **Python 3.x**
- **Scapy library** for packet analysis
- **Wireshark** (optional) for generating and testing pcap files

### Installation:

1. Clone this repository:
   ```bash
   git clone https://github.com/rafikyacoub/miniNIDS.git
   cd miniNIDS
   ```

2. Install the required dependencies:
   ```bash
   pip install scapy
   ```

3. Run the program:
   ```bash
   python miniNIDS.py test.pcap
   ```

---

## Research & Background

1. **TCP Header**: 
   The NIDS relies on deep understanding of the TCP header structure, which includes fields like source port, destination port, sequence number, acknowledgment number, flags, etc.

2. **TCP Handshake**:
   The tool monitors the 3-way TCP handshake, detecting anomalies or deviations from the expected behavior.

3. **Port Scanning**:
   The NIDS identifies multiple port scanning techniques, including:
   - **TCP Stealth**: A method to avoid detection by sending SYN packets without completing the handshake.
   - **NULL Scan**: A scan with no flags set, designed to elicit a response from open ports.
   - **FIN Scan**: A scan that sends packets with only the FIN flag set, targeting closed ports.
   - **Xmas Scan**: A scan that sets multiple flags to confuse some firewalls and IDS systems.

4. **Port Knocking**:
   The system could be extended with **port knocking** to enhance network security by allowing access to ports only after a secret "knock" sequence.

---

## Bonus Features

1. **Custom Port Scanning Detection**: 
   A new/custom port scanning technique is implemented for enhanced security coverage.

2. **Port Knocking**: 
   This feature improves network security by allowing a more dynamic, responsive firewall system.

---

## Testing

To assess the system, you can:
1. Use **Wireshark** to capture traffic and generate pcap files.
2. Use port scanning tools like **Nmap** to simulate attacks and verify the detection capabilities of the NIDS.

---

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Author
*Rafik Yacoub - CSCE 3313 Spring 2023*
```
