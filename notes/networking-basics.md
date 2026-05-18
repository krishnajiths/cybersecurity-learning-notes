# Networking Basics

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

# IP Address
- 8 bits per octet, 32 bits total in a IPV4
- Each octet can be a decimal from 0 to 255
- 0 for network address, 255 for broadcast address, /24 subnet mask

**Private IP Address Ranges:**
- 10.0.0.0 - 10.255.255.255 (10/8)
- 172.16.0.0 - 172.31.255.255 (172.16/12)
- 192.168.0.0 - 192.168.255.255 (192.168/16)

# UDP (User Datagram  Protocol)
- In the transport layer.
- **Speed** over confirmation.
- Connectionless protocol
- Data unit that encapsulates the application data is called a **UDP datagram**

# TCP (Transmission Control Protocol)
- In the transport layer
- **Confirmation** over speed
- Connection-oriented protocol
- Uses three-way-handshake
- Data unit that encapsulates the application data is called a **TCP segment**

# Encapsulation
- Applying headers so that the data can be correctly sent and organized to the receiver

# TELNET (Teletype Network)
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
