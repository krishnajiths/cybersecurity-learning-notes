# Networking

## OSI Model
- **Application:** provides network services to end-user applications. (HTTP, DNS)
- **Presentation:** - ensures data is sent in a way application is able to understand. Responsible for encoding, compression, and encryption.
- **Session:** Responsible for establishing, maintaining, and synchronizing communication between applications running on different hosts (NFS).
- **Transport:** Enables end-to-end communication between running applications on different hosts (TCP).
- **Network:** An agreement between two systems on **different** network segments on how to communicate (IP).
- **Data Link:** An agreement between two systems on the **same** network segment on how to communicate (MAC address).
- **Physical:** Deals with the physical layer. It consists of the medium being the wire and the definition of the binary digits (0 or 1).

## TCP/IP Model
- **Application Layer:** OSI Model’s application, presentation, and session model combined.
- **Transport Layer:** OSI Model’s transport layer.
- **Internet Layer:** OSI Model’s network layer is renamed to the Internet Layer.
- **Link Layer:**  OSI Model’s data link layer.

## IP Address
- 8 bits per octet, 32 bits total in a IPV4
- Each octet can be a decimal from 0 to 255
- 0 for network address, 255 for broadcast address, /24 subnet mask

**Private IP Address Ranges:**
- 10.0.0.0 - 10.255.255.255 (10/8)
- 172.16.0.0 - 172.31.255.255 (172.16/12)
- 192.168.0.0 - 192.168.255.255 (192.168/16)

## UDP (User Datagram  Protocol)
- In the transport layer.
- **Speed** over confirmation.
- Connectionless protocol
- Data unit that encapsulates the application data is called a **UDP datagram**

## TCP (Transmission Control Protocol)
- In the transport layer
- **Confirmation** over speed
- Connection-oriented protocol
- Uses three-way-handshake
- Data unit that encapsulates the application data is called a **TCP segment**

## Encapsulation
- Applying headers so that the data can be correctly sent and organized to the receiver

## DHCP (Dynamic Host Configuration Protocol)
- Automatically assigns IP address to devices
- **D** - Discover | **O** - Offer | **R** - Request | **A** - Acknowledge

## ARP (Address Resolution Protocol)
- Protocol to find the MAC address of another device on the ethernet
- The translation of layer 3 addressing to layer 2 addressing

## ICMP (Internet Control Message Protocol)
- Used for network diagnostics and error reporting
- Commands used include ping and tracert
    - tracert stops when **Time-To-Live (TTL)** reaches 0

## DNS (Domain Name System)
- Operates at layer 7, the application layer of the OSI model
- Uses UDP port 53 and TCP port 53
- **A record:** sets a IPV4 to a domain name
- **AAAA record:** sets a IPV6 to a domain name
- **CNAME record:** sets a domain name to another domain name
- **MX record:** specifies the mail server responsible for handling emails for a domain
- ```nslookup www.example.com ``` to lookup the IP to a domain 

## WHOIS
- Public records on who owns a domain name
- Includes accurate contact details
- ```whois [website] ```

## HTTP(S) - Access the web
- Hyper Text Transfer Protocol (Secure)
- Use TCP port 80 (HTTP) and port 443 (HTTPS)
- ```telnet <target-ip> 80 ```

## FTP
- File Transfer Protocol
- Listen on TCP port 21
- ``` ftp <target-ip> ```

## SMTP
- Simple Mail Transfer Protocol
- Listens on TCP port 25
- ``` HELO ``` to start connection
- ``` MAIL FROM ``` who is the sender
- ``` RCPT TO ``` who is the recipient
- ``` DATA ``` start of message
- ```. ``` on its own line, end of message

## POP3
- Post Office Protocol V3
- Allows client to communicate with mail server and retrieve messages
- POP3 server listens on TCP port 110

## IMAP
- Internet Message Access Protocol
- Synchronizes mailbox across multiple devices
- Listens on TCP port 143

## Routing
- **OSPF (Open Shortest Path First):** Routers exchange data about state of their links in order to create a network map for efficient routing.
- **EIGRP (Enhanced Interior Gateway Routing Protocol):** Routers share data about their networks they can reach and their costs.
- **BGP (Border Gateway Protocol):** Primary protocol used on the internet. Allows different networks to give routing information.
- **RIP (Routing Information Protocol):** Simple protocol. Shares data on what networks it is connected to and how many hops away it is. Creates a table to find shortest route.

## NAT (Network Address Translation)
- One public IP provides internet access to multiple private IPs
    - Solution to IPv4 running out
- NAT-supporting routers create a table to track private IPs within a public IP
- Internal uses private IP, external uses public IP

## TELNET (Teletype Network)
- Allows you to connect to and communicate with a remote system and issue text commands

    - Echo server: This server echoes everything you send it. By default, it listens on port 7.
    - Daytime server: This server listens on port 13 by default and replies with the current day and time.
    - Web (HTTP) server: This server listens on TCP port 80 by default and serves web pages.

- **telnet [target IP] [port number]**
- (For web server) Type **GET/ HTTP/1.1** THEN identify the host **Host: [host name]**.

## HTTP Methods
- GET
- POST
- PUT
- DELETE
- HEAD: Sends the server header

# Security

## TLS
- **Transport Layer Security**
- Secures data being sent over the internet
- Secures confidentiality, integrity, and authenticity
- Adds “S” for secure to end of HTTP, SMTP, POP3, and IMAP
- TLS TCP Ports:
    - HTTPS: 443
    - SMPTS: 465 and 587
    - POP3S: 995
    - IMAPS: 993

## SSH
- More secure version of telnet, data is not sent in cleartext
- OpenSSH is the open-source implementation of the SSH protocol
- Using tunneling SSH is able to create a secure tunnel to route other protocols through SSH
- Using X11 Forwarding SSH allows the user to use the graphical application over the network for systems like Unix with graphical interfaces 
- SSH server listens on TCP port 22
- SFTP: SSH File Transfer Protocol, lets you securely transfer files over SSH | **Uses port 22**
- FTP: File Transfer Protocol, requires a proper TLS certificate to run securely | **Uses port 21**

## VPN
- Virtual Private Network
- All data is sent encrypted through a VPN tunnel
- VPN server address is shown instead of IP address

## Wireshark
- Detecting and troubleshooting network problems
- Detecting security anomalies 
- Investigating and learning protocol details

### Packet Details
- Frame: Physical layer
- Source MAC: Data link layer
- Sorce IP: Network layer
- Protocol: Transport Layer (Shows details of what protocol was used: UDP/TCP)
- Protocol Errors: Transport Layer (Shows specific segments of TCP need to be reassembled)
- Application Protocol: Application Layer (Shows details specific to the protocol used: HTTP, FTP, and SMB)
- Application Data: Application Layer (Shows application specific data)


