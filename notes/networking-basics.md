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

Move to Repo

## DNS (Domain Name System)
- Operates at layer 7, the application layer of the OSI model
- Uses UDP port 53 and TCP port 53
- **A record:** sets a IPV4 to a domain name
- **AAAA record:** sets a IPV6 to a domain name
- **CNAME record:** sets a domain name to another domain name
- **MX record:** specifies the mail server responsible for handling emails for a domain
- ```bash nslookup www.example.com ``` to lookup the IP to a domain 

## WHOIS
- Public records on who owns a domain name
- Includes accurate contact details
- ```bash whois [website] ```

## HTTP(S) - Access the web
- Hyper Text Transfer Protocol (Secure)
- Use TCP port 80 (HTTP) and port 443 (HTTPS)
- ```bash telnet <target-ip> 80 ```

## FTP
- File Transfer Protocol
- Listen on TCP port 21
- ```bash ftp <target-ip> ```

## SMTP
- Simple Mail Transfer Protocol

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

