### DNS (Domain Name System)
- Mapping a domain name to an IP address.
- Layer 7
- Uses UDP, port 53
- `nsloopup` look up address of a domain
- A record: ipv4
- AAAA record: ipv6
- CNAME record: maps a domain name to another domain name
- MX record: mail server

___

### whois
- information about the entity that registered a domain name

___

### HTTP & HTTPS
- How you browse the web, S stands for secure
- HTTPS uses TCP
- HTTP is not secured
  - `telnet [ip] 80`
  - `GET /file.html HTTP/1.1` to get raw html file
 
___

### FTP (File Transfer Protocol)
- listens on tcp port 21 by default
- `ftp [ip]`
- `type ascii` switch to ASCII mode (for text files)
- `GET [file].txt`

___

### SMTP (Simple Mail Transfer Protocol)
- listens on TCP port 25 by default

___

### POP3 (Post Office Protocol version 3)
- listens on TCP port 110 by default
- use more storage as email is kept on the server and synchronized across the email clients.

___

### IMAP (Internet Message Access Protocol)
- TCP port 143 by default
- use more storage as email is kept on the server and synchronized across the email clients.












