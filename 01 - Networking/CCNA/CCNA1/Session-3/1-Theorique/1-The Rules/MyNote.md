# CCNA 1 – ITN

# Chapter 3: Protocols and Models

## 1. Communication Fundamentals

Communication between network devices requires agreed-upon rules called **protocols**.

A successful communication process involves:

- **Source:** The device sending the message.
    
- **Destination:** The device receiving the message.
    
- **Channel:** The medium used to transmit the message.
    

### Communication Protocol Requirements

Protocols define five important aspects of communication:

1. **Message Encoding:** Converting information into a representation suitable for transmission.
    
2. **Message Formatting and Encapsulation:** Defining how information is structured and organized.
    
3. **Message Size:** Defining the maximum amount of data that can be transmitted at once.
    
4. **Message Timing:** Coordinating when data is transmitted and how devices respond.
    
5. **Message Delivery Options:** Defining how messages are delivered to destinations.
    

### Message Delivery Options

|Type|Description|
|---|---|
|Unicast|One sender communicates with one receiver.|
|Multicast|One sender communicates with a selected group of receivers.|
|Broadcast|One sender communicates with all devices in the local broadcast domain.|

### Message Timing

- **Flow Control:** Controls the rate of data transmission to prevent overwhelming the receiver.
    
- **Response Timeout:** Defines how long a sender waits for a response before taking further action.
    
- **Access Method:** Defines how devices share access to a communication medium.
    

---

## 2. Network Protocols

A **network protocol** is a set of rules and standards that define how devices communicate and exchange data.

Protocols are implemented through software, hardware, or both.

They define:

- How messages are formatted.
    
- How devices identify each other.
    
- How data is transmitted.
    
- How errors are detected or reported.
    
- How communication is established and terminated.
    

### Protocol Suite

A **protocol suite** is a collection of related protocols that work together to enable network communication.

The most important example is the TCP/IP protocol suite.

Examples of network protocols:

|Protocol|Purpose|
|---|---|
|HTTP / HTTPS|Web communication.|
|DNS|Resolves domain names into IP addresses.|
|DHCP|Automatically assigns IP configuration.|
|TCP|Provides reliable, ordered data delivery.|
|UDP|Provides connectionless transport.|
|IP|Handles logical addressing and packet delivery.|
|ICMP|Reports network errors and supports diagnostics.|
|ARP|Resolves IPv4 addresses into MAC addresses on a LAN.|
|SSH|Provides secure remote access.|

---

## 3. Standards Organizations

Standards organizations develop and maintain standards that allow devices from different manufacturers to communicate.

|Organization|Main Responsibility|
|---|---|
|ISO|Develops international standards, including the OSI model.|
|IEEE|Develops networking standards, such as Ethernet (802.3) and Wi-Fi (802.11).|
|IETF|Develops Internet protocols and standards through RFCs.|
|ICANN|Coordinates global Internet naming systems and identifiers.|
|IANA|Coordinates global IP address allocation functions and protocol parameters.|
|ITU-T|Develops international telecommunications standards.|
|TIA|Develops telecommunications and cabling standards.|

### Open Standards

Open standards allow different manufacturers to develop compatible devices and software.

**Interoperability:** The ability of different devices and systems to communicate with each other.

Example: A Windows computer can communicate with an Arch Linux computer because both implement common networking standards.

---

## 4. Reference Models

Reference models divide network communication into layers, with each layer having specific responsibilities.

The two main networking models are:

- OSI Model.
    
- TCP/IP Model.
    

### 4.1. OSI Model

The OSI (Open Systems Interconnection) model has seven layers.

|Layer|Name|Main Function|
|---|---|---|
|7|Application|Provides network services to applications.|
|6|Presentation|Handles data representation, translation, and encryption.|
|5|Session|Establishes and manages communication sessions.|
|4|Transport|Provides communication between applications.|
|3|Network|Handles logical addressing and routing.|
|2|Data Link|Handles framing and local network delivery.|
|1|Physical|Transmits bits through the physical medium.|

### 4.2. TCP/IP Model

The TCP/IP model has four layers.

|Layer|Name|Main Function|
|---|---|---|
|4|Application|Provides network services and application communication.|
|3|Transport|Provides end-to-end transport between applications.|
|2|Internet|Handles logical addressing and routing.|
|1|Network Access|Handles local network access and physical transmission.|

### 4.3. OSI and TCP/IP Comparison

|OSI Model|TCP/IP Model|
|---|---|
|Application|Application|
|Presentation|Application|
|Session|Application|
|Transport|Transport|
|Network|Internet|
|Data Link|Network Access|
|Physical|Network Access|

### Benefits of Layered Models

- Simplify network communication.
    
- Make troubleshooting easier.
    
- Separate network functions into manageable layers.
    
- Allow different manufacturers to develop compatible technologies.
    
- Allow protocols to evolve independently.
    

---

## 5. Data Encapsulation and De-encapsulation

### 5.1. Encapsulation

**Encapsulation** is the process of adding protocol information (headers and sometimes trailers) to data as it moves down the network layers.

Each layer adds information required for its specific function.

Example of encapsulation:

```
Application Data
       |
       v
TCP Segment / UDP Datagram
       |
       v
IP Packet
       |
       v
Ethernet Frame
       |
       v
Bits
```

### 5.2. Protocol Data Units (PDUs)

A **Protocol Data Unit (PDU)** is the name given to the data handled by a particular network layer.

|OSI Layer|PDU|
|---|---|
|Application|Data|
|Presentation|Data|
|Session|Data|
|Transport|Segment (TCP) / Datagram (UDP)|
|Network|Packet|
|Data Link|Frame|
|Physical|Bits|

### 5.3. De-encapsulation

**De-encapsulation** is the reverse process of encapsulation.

When the receiving device receives data, each layer processes and removes the corresponding protocol information until the original application data is delivered.

```
Bits
  |
  v
Ethernet Frame
  |
  v
IP Packet
  |
  v
TCP Segment / UDP Datagram
  |
  v
Application Data
```

### 5.4. Data Representation and Transmission

A packet is a logical structure containing headers and payload.

The packet is serialized into a sequence of bits before physical transmission.

The physical medium carries signals representing these bits:

- Copper cables: Electrical signals.
    
- Fiber-optic cables: Light signals.
    
- Wireless: Radio waves.
    

**Important:** The physical medium does not transport a visual table or matrix. It transports physical signals representing binary data.

---

## 6. Data Access

Data access explains how devices use addresses to communicate with local and remote devices.

Two important types of addresses are:

- IP addresses (Layer 3).
    
- MAC addresses (Layer 2).
    

### 6.1. IP Addresses

IP addresses provide logical addressing and identify source and destination devices across networks.

Example:

```
Computer A: 192.168.1.10
Server B:   192.168.2.10
```

Routers use destination IP addresses and routing tables to forward packets between networks.

### 6.2. MAC Addresses

MAC addresses are used for communication over a local network link.

Example:

```
Computer A: AA:AA:AA:AA:AA:AA
Router:     BB:BB:BB:BB:BB:BB
```

Ethernet switches use destination MAC addresses to forward frames.

### 6.3. Communication Within the Same LAN

When a computer communicates with another device in the same IP subnet:

1. It checks whether the destination IP belongs to its local network using its IP address and subnet mask.
    
2. It obtains the destination device's MAC address using ARP (for IPv4), if necessary.
    
3. It creates an Ethernet frame with the destination device's MAC address.
    
4. The switch forwards the frame to the destination device.
    

### 6.4. Communication With Another LAN

When a computer communicates with a device outside its local subnet:

1. It determines that the destination is remote.
    
2. It identifies its default gateway.
    
3. It obtains the default gateway's MAC address using ARP (for IPv4), if necessary.
    
4. It creates an Ethernet frame using the router's MAC address as the destination MAC.
    
5. The switch forwards the frame to the router.
    
6. The router examines the destination IP and uses its routing table to forward the packet.
    

**Important distinction:**

- Destination IP = Final destination device.
    
- Destination MAC = Next device on the local network link.
    

At each routed Ethernet hop, the Layer 2 MAC addresses are replaced with the addresses needed for the next link. The source and destination IP addresses normally remain unchanged, except when NAT is used.

---

## 7. Important Terms

|Term|Definition|
|---|---|
|Protocol|Rules governing communication between devices.|
|Protocol Suite|Collection of protocols working together.|
|Encoding|Converting information into an agreed representation.|
|Decoding|Interpreting encoded information.|
|Encapsulation|Adding protocol headers and trailers to data.|
|De-encapsulation|Processing and removing protocol information.|
|Segmentation|Dividing large messages into smaller pieces.|
|PDU|Protocol Data Unit.|
|Interoperability|Ability of different devices to communicate.|
|Flow Control|Managing the rate of data transmission.|
|Unicast|One-to-one communication.|
|Multicast|One-to-selected-group communication.|
|Broadcast|One-to-all communication within a broadcast domain.|
|Default Gateway|Router used to reach destinations outside the local network.|

---

## 8. Key Points to Remember

1. Protocols are rules that define how devices communicate.
    
2. A protocol suite is a collection of protocols working together.
    
3. The OSI model has seven layers; the TCP/IP model has four layers.
    
4. Encapsulation adds protocol information as data moves down the layers.
    
5. De-encapsulation processes that information at the receiving device.
    
6. Each network layer has its own PDU.
    
7. IP addresses provide logical addressing; MAC addresses provide local link addressing.
    
8. Switches forward Ethernet frames using destination MAC addresses.
    
9. Routers forward IP packets using routing tables.
    
10. When communicating with another LAN, a computer sends the Ethernet frame to its default gateway's MAC address.
    

## 9. Quick Revision – PDU Names

```
Application / Presentation / Session  -> Data
Transport                             -> Segment / Datagram
Network                               -> Packet
Data Link                             -> Frame
Physical                              -> Bits
```

## 10. Important Acronyms

|Acronym|Full Name|
|---|---|
|OSI|Open Systems Interconnection|
|TCP|Transmission Control Protocol|
|IP|Internet Protocol|
|UDP|User Datagram Protocol|
|PDU|Protocol Data Unit|
|MAC|Media Access Control|
|ARP|Address Resolution Protocol|
|DNS|Domain Name System|
|DHCP|Dynamic Host Configuration Protocol|
|HTTP|Hypertext Transfer Protocol|
|HTTPS|Hypertext Transfer Protocol Secure|
|IEEE|Institute of Electrical and Electronics Engineers|
|IETF|Internet Engineering Task Force|
|ISO|International Organization for Standardization|
|ICMP|Internet Control Message Protocol|