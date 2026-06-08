# SOC Traffic Monitoring and Automated Alert Triage System

## Overview

This project simulates a basic Security Operations Center (SOC) workflow by capturing network traffic, analyzing packet activity, detecting suspicious network behavior, generating structured security alerts, and performing automated alert triage.

The system uses TShark for packet capture, Python for traffic analysis, and an AI-powered triage engine to classify alerts, assess risk levels, and recommend response actions.

---

## Objectives

* Monitor network traffic in real time
* Detect suspicious network activity based on packet volume thresholds
* Generate structured security alerts in JSON format
* Automate initial SOC triage and risk assessment
* Demonstrate practical cybersecurity monitoring concepts

---

## Technologies Used

* Python 3
* TShark (Wireshark CLI)
* JSON
* Requests Library
* Linux (Kali Linux & Ubuntu)
* VirtualBox

---

## Project Architecture

Ubuntu VM (Traffic Generator)
|
| ICMP Traffic
v
Kali Linux VM (Monitoring System)
|
| TShark Packet Capture
v
traffic.pcap
|
v
Traffic Analysis
|
v
Alert Generation
|
v
alert.json
|
v
AI SOC Triage Engine
|
v
Risk Assessment & Recommendations

---

## Features

* Live ICMP traffic monitoring
* Packet capture using TShark
* Automatic PCAP to CSV conversion
* Source IP traffic analysis
* Threshold-based suspicious activity detection
* Structured JSON alert generation
* Automated alert triage
* Risk scoring and threat classification

---

## Workflow

### Step 1 – Capture Network Traffic

The system captures ICMP packets destined for the monitored host and stores them in a PCAP file.

Output:

traffic.pcap

### Step 2 – Convert PCAP to CSV

Captured packets are converted into a CSV format for easier analysis.

Extracted fields include:

* Timestamp
* Source IP
* Destination IP
* Protocol
* Packet Length

Output:

traffic.csv

### Step 3 – Analyze Traffic

The analyzer counts packets received from each source IP address.

If packet volume exceeds a predefined threshold, the source is flagged as suspicious.

### Step 4 – Generate Security Alert

When suspicious activity is detected, a structured JSON alert is generated.

Example fields:

* Alert ID
* Alert Type
* Source IP
* Destination IP
* Packet Count
* Time Window

Output:

alert.json

### Step 5 – Automated SOC Triage

The alert is submitted to an AI-powered SOC triage system for:

* Threat Classification
* Risk Scoring
* MITRE ATT&CK Mapping
* Recommended Response Actions

---

## Example Use Case

Ubuntu VM sends:

ping <Kali-IP> -c 50

The monitoring system detects:

* Source IP generated 50 packets
* Threshold configured at 40 packets

Result:

* Suspicious activity detected
* Alert generated
* Alert submitted for triage

---

## Project Structure

SOC-Traffic-Triage-System/

├── analyzer.py

├── README.md

├── requirements.txt

├── sample_alert.json

├── screenshots/

│   ├── capture.png

│   ├── alert.png

│   └── output.png

└── .gitignore

---

## Installation

Clone the repository:

git clone https://github.com/YOUR_USERNAME/soc-traffic-triage-system.git

Navigate to the project directory:

cd soc-traffic-triage-system

Install dependencies:

pip install -r requirements.txt

---

## Requirements

* Python 3.x
* TShark
* Wireshark
* Requests Library

Verify TShark installation:

tshark --version

---

## Future Improvements

* TCP and UDP traffic monitoring
* Port scan detection
* SSH brute-force detection
* Threat intelligence integration
* Real-time dashboard
* Wazuh integration
* Suricata integration
* ELK Stack integration
* PDF incident reporting

---

## Learning Outcomes

Through this project, I gained practical experience in:

* Network traffic monitoring
* Packet analysis
* Security alert generation
* SOC triage workflows
* Cybersecurity automation
* Incident detection and response concepts

---

## Author

Gayathri Silva

BSc (Hons) Information Technology – Cyber Security

Sri Lanka Institute of Information Technology (SLIIT)
