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


## TCP, UDP, # way Handshake