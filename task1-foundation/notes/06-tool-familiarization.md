# Tool Familiarization

## Wireshark
- GUI packet analyzer — captures and inspects network traffic
- Key filters:
```bash
http                    # show only HTTP traffic
ftp                     # show FTP traffic
tcp.port == 80          # filter by port
ip.addr == 192.168.x.x  # filter by IP
```

## Nmap
- Network scanner — discovers hosts, ports, services, OS
```bash
nmap -sn 192.168.1.0/24        # ping sweep (host discovery)
nmap -sS                # SYN scan (stealth)
nmap -sV                # service version detection
nmap -O                 # OS detection
nmap -A                 # aggressive (OS + version + scripts)
```

## Burp Suite
- Web proxy — intercepts HTTP/HTTPS traffic between browser and server
- Key modules: Proxy, Repeater, Intruder, Scanner
- Setup: configure browser to proxy through 127.0.0.1:8080

## Netcat
- "Swiss army knife" for TCP/UDP connections
```bash
nc -lvp 4444                    # listen on port 4444
nc  4444             # connect to target
nc -lvp 4444 > received.txt     # receive a file
nc  4444 < file.txt     # send a file
```
## Nmap Scan Results — Metasploitable2 (192.168.189.132)

### Key Findings
| Port | Service | Version | Risk |
|------|---------|---------|------|
| 21 | FTP | vsftpd 2.3.4 | CRITICAL — known backdoor CVE-2011-2523 |
| 23 | Telnet | Linux telnetd | HIGH — plaintext protocol |
| 1524 | Bindshell | Metasploitable root shell | CRITICAL — open root shell |
| 3306 | MySQL | 5.0.51a | HIGH — outdated, unauthenticated access |
| 6667 | IRC | UnrealIRCd 3.2.8.1 | CRITICAL — known backdoor CVE-2010-2075 |

### OS Detection
Linux 2.6.9 - 2.6.33 (confirmed via TCP/IP fingerprinting)

### Anonymous FTP
vsftpd allows anonymous login — confirmed by Nmap script scan
