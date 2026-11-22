
# ITN Module 4 – Physical Layer

**Course:** CCNA 1 – Introduction to Networks  
**Module:** 4 – Physical Layer  
**OSI Layer:** Layer 1

---

## 1. Introduction to the Physical Layer

The **Physical Layer** is the first and lowest layer of the OSI model. It is responsible for transmitting raw bits (`0` and `1`) across a physical transmission medium.

Its main responsibility is to convert bits into signals that can travel through a transmission medium.

### Main Responsibilities

- Transmitting individual bits over a physical medium.
    
- Defining the physical characteristics of network interfaces.
    
- Specifying how signals represent binary data.
    
- Defining data transmission rates.
    
- Synchronizing the transmission of bits.
    
- Defining physical connections and topologies.
    
- Specifying the characteristics of cables, connectors, and wireless interfaces.
    

> [!NOTE]  
> The Physical Layer handles the transmission of bits, not the interpretation of the information contained in those bits. Higher OSI layers handle that responsibility.

### Transmission Media and Signals

Different transmission media use different types of signals:

|Transmission Medium|Signal Type|
|---|---|
|Copper cable|Electrical signals|
|Fiber-optic cable|Light pulses|
|Wireless|Electromagnetic waves|

---

## 2. Physical Layer Standards

Physical Layer standards define how devices communicate through physical connections.

These standards ensure interoperability between network devices manufactured by different companies.

### Organizations Responsible for Networking Standards

|Organization|Responsibility|
|---|---|
|IEEE|Develops Ethernet and wireless networking standards|
|TIA|Develops telecommunications cabling standards|
|ISO|Develops international standards, including the OSI model|
|ANSI|Coordinates standards development in the United States|
|ITU-T|Develops telecommunications standards|

### Examples of Standards

- IEEE 802.3 – Ethernet.
    
- IEEE 802.11 – Wireless LAN (Wi-Fi).
    
- TIA-568 – Telecommunications cabling standards.
    

### Three Functional Areas of Physical Layer Standards

1. **Physical Components:** Hardware, cables, connectors, and network interfaces.
    
2. **Encoding:** Converts a stream of bits into a recognizable pattern.
    
3. **Signaling:** Represents encoded bits as physical signals.
    

### Physical Components

Physical components are the hardware devices and transmission media used to transmit signals representing bits.

Examples:

- Network Interface Cards (NICs).
    
- Ethernet ports.
    
- Copper cables.
    
- Fiber-optic cables.
    
- Wireless antennas.
    
- Cable connectors.
    

### Encoding

**Encoding** is the process of converting a stream of bits into a predefined pattern that can be recognized by the receiving device.

Examples:

- Manchester encoding.
    
- 4B/5B encoding.
    
- 8B/10B encoding.
    

### Signaling

**Signaling** is the process of representing encoded bits as signals that travel through a transmission medium.

Examples:

- Electrical signals in copper cables.
    
- Light pulses in fiber-optic cables.
    
- Electromagnetic waves in wireless communication.
    

### Encoding vs. Signaling

|Encoding|Signaling|
|---|---|
|Defines patterns for representing bits|Transmits those patterns as physical signals|
|Determines how bits are represented|Determines how signals are transmitted|
|Examples: Manchester, 4B/5B|Electrical, optical, radio signals|

---

## 3. Network Performance

### 3.1 Bandwidth

**Bandwidth** is the capacity of a transmission medium to carry data over a given period.

It is commonly measured in bits per second (bps).

|Unit|Equivalent|
|---|---|
|bps|1 bit per second|
|Kbps|1,000 bits per second|
|Mbps|1,000,000 bits per second|
|Gbps|1,000,000,000 bits per second|
|Tbps|1,000,000,000,000 bits per second|

Example:

A network connection with a bandwidth of 1 Gbps has a theoretical capacity of 1 billion bits per second.

> [!IMPORTANT]  
> Bandwidth represents capacity, not necessarily the actual amount of data successfully transferred.

### 3.2 Latency

**Latency** is the time required for data to travel from its source to its destination.

It is usually measured in milliseconds (ms).

Factors affecting latency:

- Physical distance between devices.
    
- Transmission medium.
    
- Network congestion.
    
- Routing and processing delays.
    

### 3.3 Throughput

**Throughput** is the actual amount of data successfully transferred across a network over a given period.

Throughput is usually lower than the available bandwidth because of:

- Network congestion.
    
- Transmission errors.
    
- Protocol overhead.
    
- Network equipment limitations.
    
- Competing network traffic.
    

Example:

A connection has a bandwidth of 100 Mbps, but the actual measured throughput is 75 Mbps.

### 3.4 Goodput

**Goodput** is the amount of useful application data successfully delivered over a period of time.

Goodput excludes protocol overhead and retransmitted data.

Example:

When downloading a file, the network also transmits headers and may retransmit lost packets. Goodput measures only the useful file data delivered.

### Comparison

|Term|Meaning|
|---|---|
|Bandwidth|Transmission capacity|
|Throughput|Actual data transfer rate|
|Goodput|Useful application data transfer rate|
|Latency|Time taken for data to travel|

> [!TIP]  
> Remember:
> 
> - Bandwidth = Capacity.
>     
> - Throughput = Actual transfer rate.
>     
> - Goodput = Useful data rate.
>     
> - Latency = Delay.
>     

---

## 4. Copper Cabling

Copper cables transmit data using electrical signals.

They are widely used in Ethernet networks, particularly for connecting computers, switches, routers, and other network devices.

### 4.1 Characteristics of Copper Cabling

**Advantages:**

- Relatively inexpensive.
    
- Easy to install.
    
- Widely available.
    
- Flexible and practical for local networks.
    

**Disadvantages:**

- Susceptible to electromagnetic interference (EMI).
    
- Signal quality can deteriorate over distance.
    
- Generally supports shorter transmission distances than fiber-optic cables.
    

### 4.2 Electromagnetic Interference (EMI)

**EMI** is unwanted electrical noise that can interfere with signals transmitted through copper cables.

Sources of EMI include:

- Electric motors.
    
- Power cables.
    
- Fluorescent lighting.
    
- Electrical equipment.
    

EMI can cause signal degradation and transmission errors.

### 4.3 Types of Copper Cabling

There are three common types of copper cables:

1. Unshielded Twisted-Pair (UTP).
    
2. Shielded Twisted-Pair (STP).
    
3. Coaxial cable.
    

### 4.4 Unshielded Twisted-Pair (UTP)

UTP is a copper cable containing pairs of insulated copper wires twisted together.

The twisting helps reduce electromagnetic interference and crosstalk.

**Characteristics:**

- Contains four pairs of twisted copper wires (eight wires total) in standard Ethernet UTP cables.
    
- Does not have additional metallic shielding.
    
- Uses RJ-45 (8P8C) connectors in common Ethernet installations.
    
- Commonly used in LANs.
    

**Crosstalk** occurs when signals from one wire interfere with signals in another nearby wire.

### 4.5 Shielded Twisted-Pair (STP)

STP is a twisted-pair copper cable that includes additional shielding to protect against electromagnetic interference.

**Characteristics:**

- Uses shielding around the wire pairs or cable.
    
- Provides better protection against EMI than unshielded cabling.
    
- Generally more expensive than UTP.
    
- Requires proper grounding and installation to work effectively.
    

### 4.6 Coaxial Cable

Coaxial cable consists of a central copper conductor surrounded by insulation, metallic shielding, and an outer protective jacket.

Its structure includes:

1. Inner conductor.
    
2. Insulating layer (dielectric).
    
3. Metallic shield.
    
4. Outer protective jacket.
    

**Characteristics:**

- Provides protection against external interference.
    
- Used in cable television and broadband internet installations.
    
- Historically used in Ethernet networks.
    

---

## 5. UTP Cabling

UTP is one of the most commonly used physical media in Ethernet LANs.

### 5.1 Properties of UTP Cabling

A standard Ethernet UTP cable contains four pairs of twisted copper wires.

Each pair consists of two insulated copper conductors twisted around each other.

The twisting helps reduce:

- Electromagnetic interference (EMI).
    
- Crosstalk.
    

### 5.2 UTP Cabling Standards

Two important organizations involved in UTP cabling standards are:

- TIA – Telecommunications Industry Association.
    
- EIA – Electronic Industries Alliance.
    

The TIA/EIA-568 standards define telecommunications cabling requirements, including wire termination arrangements.

### 5.3 RJ-45 Connector

The RJ-45 connector is commonly used to terminate Ethernet twisted-pair cables.

It has eight contact positions and is commonly referred to as an 8P8C connector.

### 5.4 T568A and T568B Wiring Standards

T568A and T568B define the arrangement of the eight wires inside an Ethernet cable connector.

The difference between them is the arrangement of the green and orange pairs.

|Pin|T568A|T568B|
|---|---|---|
|1|White/Green|White/Orange|
|2|Green|Orange|
|3|White/Orange|White/Green|
|4|Blue|Blue|
|5|White/Blue|White/Blue|
|6|Orange|Green|
|7|White/Brown|White/Brown|
|8|Brown|Brown|

**Important:** Both standards are valid. The key is using the correct arrangement at both ends of the cable.

### 5.5 Types of UTP Ethernet Cables

There are two traditional Ethernet cable wiring configurations:

#### Straight-Through Cable

- Uses the same wiring standard on both ends.
    
- T568A to T568A, or T568B to T568B.
    
- Traditionally used to connect different types of devices.
    

Examples:

- Computer to switch.
    
- Switch to router.
    

#### Crossover Cable

- Uses T568A on one end and T568B on the other.
    
- Traditionally used to connect similar types of devices.
    

Examples:

- Computer to computer.
    
- Switch to switch.
    
- Router to router.
    

> [!NOTE]  
> Modern Ethernet devices commonly support Auto-MDI/MDIX, which automatically detects and adjusts the transmit and receive pairs. Therefore, crossover cables are much less necessary today.

### 5.6 UTP Cable Categories

UTP cables are classified into different categories based on their performance characteristics.

|Category|General Characteristics|
|---|---|
|Cat 5e|Supports Gigabit Ethernet up to 100 m|
|Cat 6|Supports 1 Gbps up to 100 m; 10 Gbps over shorter distances|
|Cat 6a|Supports 10 Gbps up to 100 m|
|Cat 8|Supports high-speed data rates up to 40 Gbps over shorter distances|

_Note: Actual supported performance depends on the complete cabling system, installation, and applicable Ethernet standard._

### 5.7 UTP Cable Distance

A standard Ethernet twisted-pair channel is generally limited to 100 meters:

- Up to 90 meters of horizontal cable.
    
- Up to 10 meters of patch cables combined.
    

This is a common design limit for structured cabling.

---

## 6. Fiber-Optic Cabling

Fiber-optic cables transmit data using pulses of light instead of electrical signals.

They use thin strands of glass or plastic called **optical fibers**.

Fiber-optic cabling is commonly used for:

- Connecting buildings.
    
- Internet service provider networks.
    
- Long-distance communications.
    
- Data center interconnections.
    
- High-speed network backbones.
    

### 6.1 Characteristics of Fiber-Optic Cabling

**Advantages:**

- Supports very high bandwidth.
    
- Can transmit data over long distances.
    
- Immune to electromagnetic interference (EMI).
    
- Provides resistance to electrical noise.
    
- Does not conduct electricity.
    
- Offers better resistance to electrical interference than copper.
    

**Disadvantages:**

- Generally more expensive than UTP.
    
- Installation and termination can require specialized tools.
    
- Fiber strands can be damaged by excessive bending.
    
- Troubleshooting may require specialized equipment.
    

### 6.2 Fiber-Optic Cable Structure

A fiber-optic cable generally consists of:

1. **Core:** The central part through which light travels.
    
2. **Cladding:** Surrounds the core and keeps light within it through total internal reflection.
    
3. **Coating:** Protects the optical fiber from physical damage.
    
4. **Strength Members:** Provide mechanical strength.
    
5. **Outer Jacket:** Protects the cable from environmental damage.
    

### 6.3 Types of Fiber-Optic Cables

There are two main types:

#### Single-Mode Fiber (SMF)

- Uses a very small core.
    
- Allows light to travel primarily along one propagation mode.
    
- Commonly uses laser light sources.
    
- Supports long-distance transmission.
    
- Commonly used by telecommunications providers and in network backbones.
    

#### Multimode Fiber (MMF)

- Has a larger core than single-mode fiber.
    
- Allows multiple light propagation modes.
    
- Commonly uses LED or VCSEL light sources.
    
- Generally used for shorter distances.
    
- Commonly used in buildings and data centers.
    

### 6.4 Single-Mode vs. Multimode

|Characteristic|Single-Mode|Multimode|
|---|---|---|
|Core size|Small|Larger|
|Light source|Laser|LED or VCSEL|
|Distance|Longer|Shorter|
|Bandwidth potential|Very high|High|
|Common use|Long-distance links|Buildings and data centers|

### 6.5 Fiber-Optic Connectors

Common fiber-optic connectors include:

- **SC (Subscriber Connector):** Square-shaped connector with a push-pull mechanism.
    
- **LC (Lucent Connector):** Small connector commonly used in high-density installations.
    
- **ST (Straight Tip):** Uses a bayonet-style locking mechanism.
    

### 6.6 Fiber vs. Copper

|Characteristic|Copper|Fiber|
|---|---|---|
|Signal|Electrical|Light|
|EMI susceptibility|Yes|Immune|
|Transmission distance|Generally shorter|Generally longer|
|Bandwidth potential|High|Very high|
|Installation|Easier|More specialized|
|Electrical conductivity|Yes|No|

> [!IMPORTANT]  
> Fiber-optic cables are particularly useful when high bandwidth, long-distance transmission, or immunity to electromagnetic interference is required.

---

## 7. Wireless Media

Wireless media transmit data using electromagnetic waves through the air instead of physical cables.

Wireless communication allows devices to communicate without requiring a physical cable connection.

Examples:

- Wi-Fi.
    
- Bluetooth.
    
- Cellular networks.
    
- Satellite communication.
    

### 7.1 Characteristics of Wireless Media

**Advantages:**

- Mobility: Devices can communicate while moving within coverage areas.
    
- Flexibility: No physical cable connection is required.
    
- Easy deployment: Wireless networks can be installed without extensive cabling.
    
- Scalability: Additional devices can often connect without installing additional cables.
    

**Disadvantages:**

- Signal interference.
    
- Limited coverage range.
    
- Security concerns if improperly configured.
    
- Signal attenuation caused by walls and other obstacles.
    
- Shared wireless bandwidth.
    

### 7.2 Types of Wireless Media

Wireless networks commonly use electromagnetic waves in different frequency ranges.

#### Radio Waves

- Used by Wi-Fi and Bluetooth.
    
- Can travel through walls and other obstacles, depending on frequency and materials.
    
- Commonly used for wireless LAN communication.
    

#### Microwaves

- Used in cellular communications, satellite links, and point-to-point wireless connections.
    
- Often use directional antennas.
    
- Some microwave links require a clear line of sight.
    

#### Infrared

- Uses infrared light to transmit information.
    
- Generally operates over short distances.
    
- Usually requires a direct or reflected optical path.
    
- Cannot penetrate walls.
    

### 7.3 Wireless Technologies

|Technology|Common Use|
|---|---|
|Wi-Fi (IEEE 802.11)|Wireless LAN|
|Bluetooth (IEEE 802.15.1 historically)|Short-range device communication|
|Cellular|Mobile communication networks|
|Satellite|Long-distance communication|
|Infrared|Short-range communication|

### 7.4 Wireless Limitations

Wireless transmission is affected by:

- Distance between transmitter and receiver.
    
- Physical obstacles.
    
- Interference from other wireless devices.
    
- Frequency used.
    
- Antenna characteristics.
    
- Environmental conditions.
    

> [!NOTE]  
> Unlike a dedicated physical cable, wireless communication uses a shared transmission medium. Multiple devices may compete for access to the same wireless channel.

---

## 8. Comparing the Three Main Transmission Media

|Characteristic|Copper|Fiber Optic|Wireless|
|---|---|---|---|
|Transmission|Electrical signals|Light pulses|Electromagnetic waves|
|Physical cable|Yes|Yes|No|
|EMI interference|Susceptible|Immune|Radio interference possible|
|Mobility|Limited|Limited|High|
|Distance|Generally short|Short to very long|Depends on technology|
|Typical use|Ethernet LAN|Backbone and long links|Wi-Fi and mobile networks|

---

## 9. Important Terminology

|Term|Definition|
|---|---|
|Physical Layer|OSI Layer 1, responsible for transmitting bits|
|NIC|Network Interface Card; connects a device to a network|
|Encoding|Converts bits into a recognizable pattern|
|Signaling|Represents encoded bits using physical signals|
|EMI|Electromagnetic interference|
|Crosstalk|Interference between signals in nearby wires|
|UTP|Unshielded Twisted-Pair|
|STP|Shielded Twisted-Pair|
|SMF|Single-Mode Fiber|
|MMF|Multimode Fiber|
|Bandwidth|Transmission capacity|
|Throughput|Actual data transfer rate|
|Goodput|Useful application data transfer rate|
|Latency|Time taken for data to travel|
|RJ-45|Common name for the 8P8C Ethernet connector|
|T568A|Ethernet cable wire termination standard|
|T568B|Ethernet cable wire termination standard|

---

## 10. Module Summary

The Physical Layer is responsible for transmitting bits across network media.

### Three Main Transmission Media

1. **Copper:** Transmits electrical signals.
    
2. **Fiber Optic:** Transmits light pulses.
    
3. **Wireless:** Transmits electromagnetic waves.
    

### Physical Layer Standards Define

- Physical components.
    
- Encoding.
    
- Signaling.
    

### Network Performance Terminology

- Bandwidth: Capacity.
    
- Throughput: Actual transfer rate.
    
- Goodput: Useful data delivered.
    
- Latency: Transmission delay.
    

### Copper Cabling Types

- UTP.
    
- STP.
    
- Coaxial.
    

### Fiber-Optic Types

- Single-mode.
    
- Multimode.
    

### Wireless Technologies

- Wi-Fi.
    
- Bluetooth.
    
- Cellular.
    
- Satellite.
    
- Infrared.
    

---

## 11. Knowledge Check

Use these questions to test your understanding:

1. What is the primary responsibility of the Physical Layer?
    
2. What is the difference between encoding and signaling?
    
3. What are the three main transmission media?
    
4. What is the difference between bandwidth, throughput, and goodput?
    
5. What is latency?
    
6. What is electromagnetic interference (EMI)?
    
7. What is crosstalk?
    
8. What are the differences between UTP and STP?
    
9. What are the three main types of copper cabling?
    
10. What is the purpose of the RJ-45 connector?
    
11. What is the difference between T568A and T568B?
    
12. What is the difference between straight-through and crossover cables?
    
13. What is the standard maximum Ethernet twisted-pair channel length?
    
14. What are the advantages of fiber-optic cables?
    
15. What is the difference between single-mode and multimode fiber?
    
16. What are SC, LC, and ST connectors?
    
17. What are the main advantages and disadvantages of wireless media?
    
18. What is the difference between radio waves, microwaves, and infrared?
    

---

## 12. Related Notes

- [[OSI Model]]
    
- [[Ethernet]]
    
- [[UTP Cabling and RJ-45]]
    
- [[T568A and T568B]]
    
- [[Fiber-Optic Communication]]
    
- [[Network Performance - Bandwidth, Throughput and Latency]]
    

**Reference:** Cisco Networking Academy – Introduction to Networks (ITN), Module 4: Physical Layer.