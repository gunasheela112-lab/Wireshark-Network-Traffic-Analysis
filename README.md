# Wireshark Network Traffic Analysis

A hands-on network traffic analysis project using Wireshark to capture and inspect common TCP/IP protocols and perform controlled connectivity troubleshooting.

## Overview

This project demonstrates practical packet-analysis skills by examining:

- **TCP** — Three-way connection establishment: SYN → SYN/ACK → ACK
- **ARP** — Request and reply behavior for local network address resolution
- **ICMP** — Echo requests and replies for connectivity verification
- **DNS** — Standard DNS query and response traffic
- **ICMP Troubleshooting** — Controlled analysis of an unreachable test destination

## Analysis Performed

### 1. TCP Three-Way Handshake

Inspected TCP packets to identify the connection-establishment sequence:

```
SYN → SYN/ACK → ACK
```

Wireshark filter used:

```
tcp.flags.syn == 1
```

### 2. ARP Request and Reply

Analyzed how a device resolves a local IPv4 address to a MAC address using ARP.

Example packet flow:

```
Who has <IP>? Tell <IP>
<IP> is at <MAC>
```

Filter:

```
arp
```

### 3. ICMP Connectivity Analysis

Captured ICMP Echo Request and Echo Reply packets to verify successful network connectivity.

Filter:

```
icmp
```

### 4. DNS Query and Response

Inspected DNS traffic to identify standard queries and corresponding responses.

Filter:

```
dns
```

### 5. Controlled ICMP Troubleshooting

Tested connectivity to the documentation-only address `192.0.2.1`. The test produced no Echo Replies, allowing the capture to be used to distinguish transmitted ICMP requests from successful responses.

Observed result:

- ICMP Echo Requests were transmitted
- No Echo Replies were received
- Ping reported 100% packet loss

## Screenshots

The repository will contain screenshots demonstrating each analysis:

| Analysis | Screenshot |
|---|---|
| TCP Three-Way Handshake | [View screenshot](screenshots/tcp-handshake.png) |
| ARP Request/Reply | [View screenshot](screenshots/arp-analysis.png) |
| ICMP Connectivity | [View screenshot](screenshots/icmp-analysis.png) |
| DNS Query/Response | [View screenshot](screenshots/dns-analysis.png) |
| ICMP Troubleshooting | [View screenshot](screenshots/icmp-troubleshooting.png) |

## Tools & Skills

- Wireshark
- Packet Capture & Analysis
- TCP/IP
- TCP Three-Way Handshake
- ARP
- ICMP
- DNS
- Network Troubleshooting
- Display Filters

## Project Evidence

The project is based on hands-on packet captures and Wireshark analysis. The public repository contains the documentation and selected screenshots; raw `.pcapng` capture files are kept separately rather than published.

## Learning Outcomes

- Understand common packet flows at the protocol level
- Use Wireshark display filters to isolate traffic
- Identify TCP connection establishment
- Interpret ARP, ICMP, and DNS packets
- Use packet captures to support basic network troubleshooting
