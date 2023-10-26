# Networking

## IP Addresses

used to identify and locate devices on a network. (layer 3)

* types
    1. IPV4
        inet `192.168.57.139` . dotted decimal format -> 32bit -> can range from 0 to 255
    2. IPV6
        inetv6 `fe90::20c:29ff:fe0a:4205` . hexadecimal format -> 123 bit


        - IPv4 and IPv6 are versions of the Internet Protocol that provide unique addresses to devices on a network
        - transition from IPv4 to IPv6 is necessary due to the depletion of available IPv4 addresses
        - IPv6 provide better security, auto-configuration etc




[128    64     32   16   8   4   2   1] 

* NAT Network address translation

1. Private IP Address (ex: in home 
, a lot of devices are connected to the internet and all devices are assigned Ip addresses)
    - class A   `10.0.0.0` -> used by companies bcz small amount of network but large amount of hosts
    - class B   `172.16.0.0` to `172.31.0.0`
    - class c   `192.168.0.0` to `192.1680255.255` -> used at home
    - Loopback  `127.0.0.0` to `127.0.0.7`

2. Public Ip Address (The one's that are brought from ISP, internet service provider)


## MAC Addresses , Media Access Control
layer 2

* MAC adress is a unique identifier assigned to network interface controllers (NICs) of network devices. It is a hardware address that is permanently assigned by the manufacturer and is stored in the device's firmware or read-only memory (ROM).

*  MAC addresses are used at the data link layer(layer 2) of the OSI model to ensure that data is delivered to the correct device within a local network.

* 48 bits in length and are expressed as a sequence of six pairs of hexadecimal digits separated by colons or hyphens `00:1A:2B:3C:4D:5E` -> first three pairs of digits identify the manufacturer of the network interface card, while the last three pairs provide a unique identifier for the specific device.

* Routers and switches use these MAC addresses to forward the data to the appropriate destination.

* MAC addresses are specific to the local network and do not have global uniqueness like IP addresses. They are only relevant within the scope of the local network segment. When data needs to be transmitted beyond the local network, it is encapsulated in network packets that contain source and destination IP addresses.


## TCP, UDP, # way Handshake (more notes in basics)
layer 4

- wireshark can be used to find the protocols


1. TCP is a connection-oriented protocol that provides reliable, ordered, and error-checked delivery of data packets over an IP network. It guarantees that data sent from one device is received correctly by the destination device. TCP achieves this reliability through mechanisms like acknowledgement, retransmission, and flow control. It breaks data into smaller packets, assigns sequence numbers to them, and ensures they are reassembled correctly at the receiving end. TCP is widely used for applications that require guaranteed delivery, such as web browsing, email, file transfer, and remote login.

2. UDP, on the other hand, is a connectionless protocol that does not provide the same level of reliability as TCP. It is simpler and more lightweight, making it suitable for applications that can tolerate some data loss or delay. UDP does not establish a connection or guarantee delivery of packets. It simply sends data packets from one device to another without waiting for acknowledgements or retransmissions. UDP is commonly used for real-time applications like streaming media, online gaming, DNS (Domain Name System), and VoIP (Voice over IP).

* The three-way handshake is a process used by TCP to establish a connection between two devices. It is a sequence of three steps that takes place before data transmission can begin. Here's how the three-way handshake works:

SYN (Synchronize): The initiating device (often referred to as the client) sends a TCP packet with the SYN flag set to the destination device (often referred to as the server). This packet indicates the desire to establish a connection and includes an initial sequence number.
SYN-ACK (Synchronize-Acknowledge): Upon receiving the SYN packet, the destination device responds with a TCP packet that has both the SYN and ACK (acknowledge) flags set. This packet acknowledges the receipt of the initial SYN packet and also includes its own initial sequence number.
ACK (Acknowledge): Finally, the initiating device acknowledges the SYN-ACK packet by sending an ACK packet back to the destination. This packet confirms the establishment of the connection and typically contains an incremented sequence number.
Once the three-way handshake is complete, the connection is established, and both devices are ready to exchange data. The sequence numbers exchanged during the handshake are used to ensure that data is transmitted and received in the correct order.

In summary, TCP is a reliable, connection-oriented protocol that guarantees delivery of data, while UDP is a simpler, connectionless protocol that does not provide the same level of reliability. The three-way handshake is a process used by TCP to establish a connection between devices, involving the exchange of SYN, SYN-ACK, and ACK packets.

## Common Ports and Protocols

1. TCP
    - FTP (File Transfer Protocol): Port 21 -> welac log in to the server, we can a put a file or get a file from server
    - SSH (Secure Shell): Port 22 (TCP)
    - Telnet: Port 23 (TCP) -> ability to log into a machine remotely, ssh is the same but in encrypted format
    - SMTP (Simple Mail Transfer Protocol): Port 25 -> SMTP, POP3, IMAP all related to mail
    - POP3 (Post Office Protocol version 3): Port 110
    - IMAP (Internet Message Access Protocol): Port 143
    - DNS (Domain Name System): Port 53 (TCP and UDP)-> to resolve IP addressses to names
    - HTTP (Hypertext Transfer Protocol): Port 80 (TCP)
    - HTTPS (Hypertext Transfer Protocol Secure): Port 443 (TCP)
    - SMB (Server Message Block): Port 445 (TCP) -> it was originally 139


2. UDP 

    - DNS (Domain Name System): Port 53 (TCP and UDP)-> to resolve IP addressses to names
    - DHCP (Dynamic Host Configuration Protocol): Port 67 (UDP) and Port 68 (UDP)
    - TFTP (Trivial File Transfer Protocol): Port 69 (UDP)
    - SNMP (Simple Network Management Protocol): Port 161 (UDP)



## OSI Model  

- The OSI (Open Systems Interconnection) model is a conceptual framework that standardizes the functions of a communication system into seven distinct layers. 

- Each layer has specific responsibilities and interacts with the layers above and below it. The OSI model provides a structured approach to understanding and designing network protocols and communication systems. Here's a brief overview of each layer:

+ Physical - data cables, cat6
+ data - switching, Mac addresses
+ Network - IP  







__please do not throw sausage pizza away__ 

1. Physical Layer: The physical layer is responsible for the transmission and reception of raw unstructured data bits over a physical medium. It defines the electrical, mechanical, and functional characteristics of the physical interface between devices.

2. Data Link Layer: The data link layer handles the reliable transmission of data frames between directly connected nodes over a physical link. It provides error detection and correction, flow control, and handles access to the physical medium. Ethernet, Wi-Fi, and PPP (Point-to-Point Protocol) are examples of data link layer protocols.

3. Network Layer: The network layer enables the routing of data packets across different networks. It deals with logical addressing and determines the best path for data delivery based on network conditions and routing protocols. The IP (Internet Protocol) is a key network layer protocol.

4. Transport Layer: The transport layer ensures the reliable and orderly delivery of data between end systems. It breaks data into smaller segments, manages end-to-end communication, and provides error recovery, flow control, and congestion control. TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) operate at this layer.

5. Session Layer: The session layer establishes, manages, and terminates communication sessions between applications. It provides synchronization and dialog control mechanisms to enable seamless communication between devices. This layer also handles session checkpointing and recovery.

6. Presentation Layer: The presentation layer is responsible for data representation, encryption, compression, and formatting. It ensures that data sent by the application layer of one system is understandable by the application layer of another system. This layer deals with data syntax and semantics.

7. Application Layer: The application layer is the closest layer to the end-user and provides services directly to user applications. It includes protocols for various application-level services such as file transfer, email, web browsing, and remote access. Examples of protocols at this layer include HTTP, SMTP, FTP, and DNS.


- The key idea behind the OSI model is to separate the complex task of network communication into manageable layers, with each layer focused on specific functions. This modular approach facilitates interoperability, ease of implementation, and troubleshooting in network systems.

- It's important to note that the OSI model is a conceptual model and does not necessarily reflect the exact implementation of all networking systems, which often use a hybrid of various layers and protocols. However, the OSI model remains a useful reference for understanding network communication and protocols.