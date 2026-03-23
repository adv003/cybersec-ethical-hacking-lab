# Lab Environment Setup

## Topology
```
```
Host Machine (Windows/Linux)
└── VMware Workstation
    ├── Kali Linux 2024.x (Attacker) — 192.168.x.x
    ├── Metasploitable2 (Target 1)   — 192.168.x.x
    └── DVWA on Ubuntu (Target 2)    — 192.168.x.x

Network: Host-Only Adapter (isolated — no internet access)
## Setup Steps
1. Install VMware Workstation / VirtualBox
2. Import Kali Linux ISO — allocate 4GB RAM, 2 CPUs, 50GB disk
3. Import Metasploitable2 OVA
4. Install DVWA (or import pre-built VM)
5. Set all VMs to Host-Only Adapter
6. Verify connectivity: ping each target from Kali

## Verification Commands
```bash
# Check Kali IP
ifconfig eth0

# Ping Metasploitable2
ping -c 4 

# Verify DVWA is reachable
curl http:///dvwa/
```
