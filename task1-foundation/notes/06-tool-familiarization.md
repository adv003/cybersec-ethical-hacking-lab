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
