# Linux Cheat-Sheet for Penetration Testing

## Navigation
| Command | Description |
|---------|-------------|
| `pwd` | Print current directory |
| `ls -la` | List all files with permissions |
| `cd ~` | Go to home directory |
| `find / -name "*.txt"` | Find files by name |
| `locate filename` | Fast file search |

## File Operations
| Command | Description |
|---------|-------------|
| `cat file.txt` | Print file contents |
| `nano file.txt` | Edit file |
| `cp src dst` | Copy file |
| `mv src dst` | Move/rename file |
| `rm -rf dir/` | Remove directory |
| `chmod 755 file` | Set permissions |
| `chown user:group file` | Change ownership |

## Networking
| Command | Description |
|---------|-------------|
| `ifconfig` | Show interfaces |
| `ip a` | Show IP addresses |
| `ping -c 4 host` | Test connectivity |
| `netstat -tuln` | Show open ports |
| `ss -tuln` | Modern netstat |
| `traceroute host` | Trace network path |
| `nslookup domain` | DNS lookup |
| `whois domain` | Domain info |

## Process & System
| Command | Description |
|---------|-------------|
| `ps aux` | List running processes |
| `kill -9 PID` | Force kill process |
| `top` | Live process monitor |
| `uname -a` | System info |
| `df -h` | Disk usage |
| `free -h` | Memory usage |

## Package Management
| Command | Description |
|---------|-------------|
| `apt update` | Refresh package list |
| `apt install pkg` | Install package |
| `apt remove pkg` | Remove package |
| `dpkg -l` | List installed packages |

## Useful Pentesting One-liners
```bash
# Who else is on the network?
nmap -sn 192.168.1.0/24

# What ports are open?
nmap -sV -p- 

# Listen for incoming connection
nc -lvp 4444

# Check for SUID binaries (privesc)
find / -perm -4000 2>/dev/null
```
