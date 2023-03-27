# Networks
*1.3 Exchanging data*

Networks allow devices to communicate and share data, hardware (i.e., servers), and peripherials (e.g., printers and scanners). 

## Types of networks

There are two types of networks mentioned on the specification - LANs and WANs.

### LAN

A LAN is a Local Area Network consisting of two or more connected devices. These devices will only span a limited, small geographical area, such as a school or shop. The devices may be PCs, phones, printers, or more. They will be connected physically by cables or wirelessly with a WAP (Wireless Access Point).

### WAN

A WAN is a Wide Area Network consisting of two or more interconnected networks. The Internet is the world's largest WAN and consists of a large number of LANs. WANs typically span larger geographical areas. Third-party communication channels are often used to transmit data.

## DNS

The Domain Name System, known otherwise as DNS, enables the IP addresses' of servers to be accessed through domain names. The DNS catalogues all domain names and IP addresses in a series of global directories - domain name servers can access these to locate resources via domain names.

When a webpage is requested using the URL a user enters, the browser requests the corresponding IP address from a local server. If that DNS does not have the IP address, the request is escalated to a larger, albeit marginally slower, DNS. When the IP address is located and returned, the browser sends a request to that location to retrieve the web page data.

```
www  .  websitename  .  co  . uk
host    website         2LD   cTLD
```

`websitename.co.uk` is the website domain name. `www.websitename.co.uk` is the fully qualified domain name (FQDN).

### Fully qualified domain names

A fully qualified domain name is one that includes the host server name, for example `www`, `mail`, or `ftp` depending on whether the resource being request is hosted on the web, mail, or ftp server.

### IP addresses

An IP (Internet Protocol) address is a unique address assigned to a device on a network. It indicates where a packet of data is to be sent or has been sent from. Routers can use this address to direct the data packet accordingly. The IP address is the address of the server that a website resides on, for example.

`185.199.110.153`

### Domain name structure

TLDs (top level domains) sit at the end of domain names. They include cTLDs (country TLDs), such as `.uk`, `.ie`, and `.dk`, and generic TLDs, such as `.com`, `.org`, and `.net`.

2LDs (second level domains) come before TLDs. They include `.gov`, `.co`, and `.ac`.

3LDs (third level domains) come before 2LDs. For example, `.colchsfc`.

```
colchsfc  .  ac  .  uk
3LD          2LD    cTLD
```

## TCP/IP stack

Protocols allow devices to communicate by ensuring they all follow the same standards and therefore interpret data in the same way. The TCP/IP (Transmission Control Protocol/Internet Protocol) stack consists of four layers, each with its own set of protocols.

1. Application layer
2. Transport layer
3. Internet layer
4. Network interface layer

### Application layer

The application layer sits at the top of the stack and uses protocols relating to the application being used to transmit data over a network. If this application is a browser, it would select an appropriate protocol for any given communication, such as HTTP, POP3, or FTP.

### Transport layer

The transport layer uses TCP (Transmission Control Protocol) to establish an end-to-end connection with the recipient computer. The data is split into packets and labelled with a packet number, the total number of packets, and the port number through which the packet should route. This ensures it is handled by the correct application on the recipient computer. For example, port 80 is a common port used by the HTTP protocol.

Receipt of packets is acknowledged. The transport layer requests retransmission of any lost packets.

### Internet layer

The Internet layer adds the source and destination IP addresses to the packets. Routers operate on the Internet layer and will use these IP addresses to forward the packets on to the destination. The addition of an IP address to the port number forms a socket. A socket specifies which device the packet must be sent to and the application being used on that device.

`185.199.110.153:25565`

### Network interface layer

The network interface layer is the physical connection between network devices and adds their unique MAC (Media Access Control) addresses to the packets. These identify the source and destination computers. Once the packet finds the correct network using the IP address, it can then locate the correct piece of hardware. Unless the two computers are on the same network, the destination of the MAC address will initially be the MAC address of the fist router that the packet will be sent to.

At the receiving end, the MAC address is removed by the network interface layer. The Internet layer then removes the IP address and passes it on to the transport layer. The transport layer removes the port numbers and reassembles the packets in the correct order. The resulting data is then passed on to the application which presents the data to the user.
