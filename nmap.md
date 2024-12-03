### tips for protecting against scans

- block unused ports using a firewall, it minimizes the information exposed to the attacker, reducing resource strain and good security practice

  
___


### network quick tips

- There are 65535 ports available
- `-sn` ping sweep, sends an ICMP packet to each possible IP address to see which one is online, not always accurate but is a baseline (ARP)
- CIDR: `/8` `x.0.0.0`
- CIDR: `/16` `x.x.0.0`
- CIDR: `/24` `x.x.x.0`
  
___


### nmap scans

- `nmap -h` or `man nmap` for help
- `-sS` TCP scan, sends a SYN packet but does not complete the handshake. More stealthy. Need more permissions
  - half-life/stealth scans gives nmap CAP_NET_RAW, CAP_NET_ADMIN and CAP_NET_BIND_SERVICE capabilities so some NSE scripts might not work 
- `-sU` UDP scan, scans for open UDP ports
  - open/filtered: no response
  - closed port: target responds with an ICMP (ping) packet
  - very slow, good to use `--top-ports [#]` to scan the top # of common used UDP ports
- `-sT` TCP scan, scans for open TCP ports, completes the handshake
  - `-sN` TCP Null Scan: sends packets with no TCP flags
    - open/filtered ports: no response
    - closed ports: respond with RST (reset)
  - `-sF` TCP FIN Scan: sends packets with only FIN flag set
    - open/filtered ports: no response
    - closed ports: respond with RST 
  - `-sX` TCP Xmas Scan: sneds packets with FIN,PSH,URG flags set
    - open/filtered ports: no response
    - closed ports: respond with RST
    - more detectable
- NULL, FIN, Xmas scans are used to evade firewall but most modern systems are not effective against, windows may respond to it with RST flag 
- `O` detect target operating system
- `sV` detect version of services
- `v` verbose, more info, add more v's for more info
- `-oA` saves the output in 3 major formats at once so you don't have to rescan the target
- `-oN` saves nmap result in a normal format
- `oG` saves nmap ressult in a grepable format
- `-A` aggressive mode, scans for OS, service, traceroute, and scripts
- `-T5` increase speed at level 5, [0-5], 0 being slowest
- `-p [port]` scan a specific port
- `-p [port-port]` scan ports with a range
- `-p-` scans all ports
- `--script` activate a script from nmap scripting library
- `--script=vuln` activate all scripts in vuln category
  
___


### NSE Scripts (Nmap Scripting Engine)

- written in Lua programming language
  
#### Categories

- `safe` won't affect the target
- `intrustive` not safe, likely to affect the target
- `vuln` scans for vulnerabilities
- `exploit` attempt to exploit a vulnerability
- `auth` attempt to bypass authentication for running services
- `brute` attempt to bruteforce credentials for running services
- `discovery` attempt to query running services for further information about the network
- More: https://nmap.org/book/nse-usage.html
- `--script=<script-name>` run a specific script, works with categories and is separated by commas if more than one
- `--script-args` some scripts require arguments so use this.
  
Example: 

```
nmap -p 80 <ip> --script http-put --script-args http-put.url='/uploads/rootme.php',http-put.file='/tmp/rootme.php'
```

- more: https://nmap.org/nsedoc/
- finding scripts locally, its in `/usr/share/nmap/scripts/scripts.db`
  
___

### Firewall evasion

- window host with a default firewall will block all ICMP packets, nmap sends ICMP packets by default before scanning so with a firewall configured this way, nmap will see it as dead or won't scan it at all
- `-Pn` do not ping the host before scanning
- if you are on the local network, just use ARP requests
- `-f` splitting packets into smaller pieces, making it less likely for the packets to be detected by a firewall or IDS
- `--mtu [#]` more control over the size of the packets, accepts a max transmission unit size for packets to be sent. Must be multiple of 8
- `--scan-delay [time]ms` add a delay between packets sent, avoids time-based firewall/IDS or network is unstable
- `--badsum` generate invalid checksum for packets, firewalls might respond without checking checksum for the packets, so it will determine the presence of a firewall/IDS
- more: https://nmap.org/book/man-bypass-firewalls-ids.html
  



















