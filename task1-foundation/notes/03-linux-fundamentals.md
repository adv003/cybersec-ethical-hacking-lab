# Linux Fundamentals

## File System Navigation
```bash
pwd           # print working directory
ls -la        # list all files with permissions
cd /var/log   # change directory
find / -name "*.conf" 2>/dev/null  # find config files
```

## File & Directory Permissions
```bash
# Permission format: [type][owner][group][others]
# Example: -rwxr-xr-- = file, owner:rwx, group:r-x, others:r--

chmod 755 script.sh     # rwxr-xr-x
chmod +x script.sh      # add execute
chown root:root file    # change owner and group

# Octal reference
# 4=read  2=write  1=execute
# 7=rwx   6=rw-   5=r-x   4=r--
```

## Package Management
```bash
apt update              # refresh package list
apt upgrade             # upgrade installed packages
apt install nmap        # install a package
apt remove nmap         # remove a package
dpkg -l                 # list installed packages
dpkg -i package.deb     # install .deb file
```

## Networking Commands
```bash
ifconfig                # show network interfaces (legacy)
ip a                    # modern equivalent
ping -c 4 8.8.8.8      # test connectivity (4 packets)
netstat -tuln           # show listening ports
ss -tuln                # modern netstat equivalent
traceroute google.com   # trace route to host
```
```
