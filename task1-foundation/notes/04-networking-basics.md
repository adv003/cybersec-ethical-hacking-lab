# Networking Basics

## OSI Model
| Layer | Name | Protocol Examples | Role |
|-------|------|-------------------|------|
| 7 | Application | HTTP, FTP, DNS, SMTP | User-facing services |
| 6 | Presentation | SSL/TLS, JPEG, MPEG | Encryption, encoding |
| 5 | Session | NetBIOS, RPC | Session management |
| 4 | Transport | TCP, UDP | End-to-end delivery |
| 3 | Network | IP, ICMP, OSPF | Routing |
| 2 | Data Link | Ethernet, ARP, MAC | Node-to-node delivery |
| 1 | Physical | Ethernet cable, Wi-Fi | Raw bit transmission |

## TCP/IP Suite
- TCP — connection-oriented, 3-way handshake (SYN → SYN-ACK → ACK)
- UDP — connectionless, faster, no delivery guarantee
- ICMP — diagnostic (ping, traceroute)

## DNS & HTTP/HTTPS
- DNS: resolves domain names to IPs — UDP port 53
- HTTP: plaintext web traffic — TCP port 80
- HTTPS: encrypted with TLS — TCP port 443
- TLS handshake: ClientHello → ServerHello → Certificate → Key Exchange → Finished

## IP Addressing & Subnetting
| CIDR | Subnet Mask | Hosts |
|------|-------------|-------|
| /24 | 255.255.255.0 | 254 |
| /25 | 255.255.255.128 | 126 |
| /30 | 255.255.255.252 | 2 |

## NAT (Network Address Translation)
Translates private IPs (192.168.x.x, 10.x.x.x) to a single public IP.
Types: Static NAT, Dynamic NAT, PAT (Port Address Translation)

## Lab Note
Reverse DNS lookup (nslookup 192.168.189.132) returns NXDOMAIN
as expected — no PTR records configured in an isolated lab 
environment with no local DNS server.

## ARP Table (Lab Environment)
```bash
arp -a
# 192.168.189.2   → VMware host-only gateway
# 192.168.189.132 → Metasploitable2 (00:0c:29:64:c6:81)
```
