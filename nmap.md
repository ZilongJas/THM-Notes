### tips for protecting against nmap
- block unused ports, it minimizes the information exposed to the attacker, reducing resource strain and good security practice. 
___

### nmap things for scanning
- There are 65535 ports available
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
- `-A` agressive mode, scans for OS, service, traceroute, and scripts
- `-T5` increase speed at level 5, [0-5], 0 being slowest
- `-p [port]` scan a specific port
- `-p [port-port]` scan ports with a range
- `-p-` scans all ports
- `--script` activate a script from nmap scripting library
- `--script=vuln` activate all scripts in vuln category
- 


























