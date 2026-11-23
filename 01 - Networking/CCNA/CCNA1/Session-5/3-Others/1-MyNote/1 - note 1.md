
# Module 4 – Physical Layer

## 1. Introduction to the Physical Layer

The **Physical Layer (Layer 1)** is the first and lowest layer of the OSI (Open Systems Interconnection) model.

Its primary responsibility is to transmit raw bits (0s and 1s) across a physical transmission medium.

The Physical Layer defines how devices physically connect to the network and how bits are represented and transmitted through that medium.

### Main Responsibilities

- **Physical components:** Defines the physical characteristics of network devices, connectors, cables, and interfaces.
    
- **Encoding:** Defines how bits are represented as signals.
    
- **Signaling:** Defines how electrical, optical, or wireless signals represent bits.
    
- **Transmission:** Transmits and receives individual bits across the physical medium.
    
- **Data rate:** Defines the number of bits transmitted per second.
    
- **Synchronization:** Ensures that the sender and receiver can identify individual bits.
    

### Important Concept

The Physical Layer does not interpret the meaning of the transmitted data. It only handles the transmission and reception of bits.

---

## 2. Physical Layer Standards

Physical Layer standards define the characteristics required for devices to communicate over a physical medium.

These standards are developed by several organizations:

|Organization|Responsibility|
|---|---|
|IEEE (Institute of Electrical and Electronics Engineers)|Develops Ethernet and wireless LAN standards.|
|TIA (Telecommunications Industry Association)|Develops telecommunications and cabling standards.|
|EIA (Electronic Industries Alliance)|Historically developed electronic and telecommunications standards; its standards work is now handled by other organizations.|
|ITU-T (International Telecommunication Union - Telecommunication Standardization Sector)|Develops international telecommunications standards.|
|ISO (International Organization for Standardization)|Develops international networking and communication standards.|
|ANSI (American National Standards Institute)|Coordinates and approves voluntary standards in the United States.|

### Examples of Standards

- IEEE 802.3: Ethernet.
    
- IEEE 802.11: Wireless LAN (Wi-Fi).
    
- TIA-568: Commercial telecommunications cabling standards.
    

---

## 3. Physical Layer Components

The Physical Layer consists of three main types of physical transmission media:

1. Copper cable.
    
2. Fiber-optic cable.
    
3. Wireless transmission.
    

Each medium has different characteristics, advantages, and limitations.

---

## 4. Bandwidth

**Bandwidth** refers to the capacity of a medium to carry data.

In digital networking, bandwidth is commonly expressed in bits per second (bps).

### Common Units

|Unit|Equivalent|
|---|---|
|1 Kbps|1,000 bps|
|1 Mbps|1,000,000 bps|
|1 Gbps|1,000,000,000 bps|
|1 Tbps|1,000,000,000,000 bps|

**Important:** Network bandwidth is measured in bits per second, not bytes per second.

- b = bit
    
- B = Byte
    
- 1 Byte = 8 bits
    

### Example

A network connection with a bandwidth of 1 Gbps theoretically carries:

1,000,000,000 bits per second.

Converting to bytes:

1,000,000,000 / 8 = 125,000,000 bytes per second.

This is equivalent to 125 MB/s using decimal units.

**Note:** Actual application throughput is usually lower because of protocol overhead, congestion, and other factors.

---

## 5. Throughput

**Throughput** is the actual amount of data successfully transferred across a network during a given period.

Throughput is usually lower than the available bandwidth.

### Factors Affecting Throughput

- Network congestion.
    
- Latency.
    
- Transmission errors.
    
- Network device performance.
    
- Protocol overhead.
    
- Limitations of the transmission medium.
    

### Bandwidth vs. Throughput

|Bandwidth|Throughput|
|---|---|
|The maximum capacity of a connection or medium.|The actual data transfer rate achieved.|
|Represents theoretical or configured capacity.|Represents actual performance.|
|Usually higher than throughput.|Usually lower than bandwidth.|

**Example:**

A network connection has a bandwidth of 100 Mbps, but the actual throughput is 75 Mbps.

This means the connection has a capacity of 100 Mbps, while only 75 Mbps is currently being achieved.

---

## 6. Goodput

**Goodput** is the amount of useful application data successfully delivered to the destination over a given period.

Goodput excludes protocol overhead and retransmitted data.

### Bandwidth, Throughput, and Goodput

- Bandwidth: Available transmission capacity.
    
- Throughput: Actual amount of data transferred.
    
- Goodput: Actual useful application data delivered.
    

Generally:

Bandwidth ≥ Throughput ≥ Goodput.

---

## 7. Transmission Media

Transmission media are the physical or wireless paths through which data travels between network devices.

### 7.1 Copper Media

Copper cables transmit data using electrical signals.

Common types:

- Unshielded Twisted Pair (UTP).
    
- Shielded Twisted Pair (STP).
    
- Coaxial cable.
    

#### Twisted-Pair Cables

Twisted-pair cables contain pairs of insulated copper wires twisted together.

Twisting helps reduce electromagnetic interference (EMI) and crosstalk.

**UTP (Unshielded Twisted Pair):**

- Does not have additional metallic shielding.
    
- Commonly used in Ethernet LANs.
    
- Relatively inexpensive and easy to install.
    

**STP (Shielded Twisted Pair):**

- Contains additional shielding to reduce electromagnetic interference.
    
- Useful in environments with significant electrical interference.
    
- More expensive and requires proper grounding.
    

#### Common Ethernet Cable Categories

|Category|Typical Maximum Frequency|Common Uses|
|---|---|---|
|Cat 5e|100 MHz|Gigabit Ethernet|
|Cat 6|250 MHz|Gigabit Ethernet; 10 Gigabit Ethernet over shorter distances|
|Cat 6a|500 MHz|10 Gigabit Ethernet up to 100 m|

_The supported Ethernet speed and distance depend on the cabling category and installation conditions._

#### Coaxial Cable

Coaxial cable consists of:

- A central copper conductor.
    
- An insulating layer.
    
- A metallic shield.
    
- An outer protective jacket.
    

It is commonly used for cable television and some broadband Internet services.

### Advantages of Copper Media

- Relatively inexpensive.
    
- Easy to install.
    
- Widely available.
    
- Supports common Ethernet standards.
    

### Disadvantages of Copper Media

- Susceptible to electromagnetic interference.
    
- Limited transmission distance.
    
- Electrical signals can be affected by noise.
    

---

### 7.2 Fiber-Optic Media

Fiber-optic cables transmit data using pulses of light instead of electrical signals.

They consist of:

- Core: The central glass or plastic section through which light travels.
    
- Cladding: Surrounds the core and keeps light within it through total internal reflection.
    
- Buffer coating: Protects the fiber.
    
- Outer jacket: Provides additional physical protection.
    

#### Types of Fiber-Optic Cable

**Single-Mode Fiber (SMF):**

- Has a very small core.
    
- Uses laser light.
    
- Supports long-distance transmission.
    
- Commonly used in ISP networks and telecommunications backbones.
    

**Multimode Fiber (MMF):**

- Has a larger core.
    
- Commonly uses LED or VCSEL-based optical sources.
    
- Supports shorter distances than single-mode fiber.
    
- Commonly used in buildings and data centers.
    

#### Single-Mode vs. Multimode

|Single-Mode|Multimode|
|---|---|
|Smaller core|Larger core|
|Long-distance transmission|Shorter-distance transmission|
|Typically uses laser sources|Typically uses LED or VCSEL sources|
|Common in ISP backbones|Common in LANs and data centers|

### Advantages of Fiber-Optic Media

- Supports high bandwidth.
    
- Supports long-distance transmission.
    
- Immune to electromagnetic interference.
    
- Difficult to tap without detection compared with ordinary copper cabling.
    

### Disadvantages of Fiber-Optic Media

- More expensive optical equipment.
    
- Requires specialized installation and testing equipment.
    
- More sensitive to improper bending and physical handling.
    

---

### 7.3 Wireless Media

Wireless networks transmit data through electromagnetic waves without requiring a physical cable between communicating devices.

Wireless communication uses antennas to transmit and receive radio-frequency signals.

#### Common Wireless Technologies

- Wi-Fi: Wireless LAN communication.
    
- Bluetooth: Short-range wireless communication.
    
- Cellular: Mobile communication networks.
    
- Satellite: Long-distance communication using satellites.
    

### Advantages of Wireless Media

- Mobility and flexibility.
    
- No physical cable required for each connection.
    
- Easy to expand in many environments.
    

### Disadvantages of Wireless Media

- Susceptible to interference.
    
- Signals can be affected by obstacles and distance.
    
- Shared wireless bandwidth.
    
- Security risks if wireless networks are improperly configured.
    

---

## 8. Copper Cabling and Interference

Copper cables can be affected by several types of interference.

### Electromagnetic Interference (EMI)

EMI occurs when external electromagnetic signals interfere with the electrical signals traveling through a cable.

Examples:

- Electric motors.
    
- Power cables.
    
- Fluorescent lighting.
    
- Radio transmitters.
    

### Radio Frequency Interference (RFI)

RFI is interference caused by radio-frequency signals.

Examples:

- Radio transmitters.
    
- Wireless devices.
    
- Broadcast equipment.
    

### Crosstalk

Crosstalk occurs when signals from one wire pair interfere with signals in another wire pair.

Twisting wire pairs helps reduce crosstalk.

### Mitigation Techniques

- Use twisted-pair cables.
    
- Use properly shielded cables when necessary.
    
- Maintain appropriate separation from electrical power cables.
    
- Use fiber-optic cables in environments with significant EMI.
    
- Follow proper cable installation practices.
    

---

## 9. Network Connectors

Connectors are used to physically connect transmission media to network devices.

|Connector|Common Use|
|---|---|
|RJ-45 (8P8C)|Ethernet twisted-pair cables|
|RJ-11|Telephone connections|
|LC|Fiber-optic connections|
|SC|Fiber-optic connections|
|ST|Fiber-optic connections|
|F-type|Coaxial cable connections|

**Note:** RJ-45 is the commonly used networking name for the 8-position, 8-contact modular Ethernet connector.

---

## 10. Copper Ethernet Cabling Types

Ethernet twisted-pair cables are commonly wired using two standards:

- T568A.
    
- T568B.
    

Both standards define the arrangement of the eight wires inside an Ethernet connector.

### Straight-Through Cable

A straight-through cable uses the same wiring standard on both ends.

Examples:

- T568A on both ends.
    
- T568B on both ends.
    

Traditionally used to connect:

- Computer to switch.
    
- Router to switch.
    
- Switch to server.
    

### Crossover Cable

A crossover cable uses different wiring standards on each end.

Example:

- T568A on one end.
    
- T568B on the other end.
    

Traditionally used to connect:

- Computer to computer.
    
- Switch to switch.
    
- Router to router.
    

**Important:** Modern Ethernet interfaces commonly support Auto-MDIX, which automatically detects and adjusts the transmit and receive pairs. Therefore, straight-through cables can often be used instead of crossover cables.

---

## 11. Physical Layer Encoding and Signaling

The Physical Layer must convert binary data into signals that can travel through the transmission medium.

### Encoding

Encoding is the process of converting bits into a specific pattern that can be recognized by the receiver.

### Signaling

Signaling is the process of representing encoded data using physical signals.

Common signal types:

- Electrical signals: Used in copper cables.
    
- Optical signals: Used in fiber-optic cables.
    
- Radio waves: Used in wireless communication.
    

### Important Distinction

- Encoding determines how bits are represented.
    
- Signaling determines how those representations are transmitted through the medium.
    

---

## 12. Physical Layer Performance

Several factors affect the performance of physical transmission.

### Attenuation

Attenuation is the reduction in signal strength as the signal travels through a medium.

### Latency

Latency is the time required for data to travel from the source to the destination.

### Noise

Noise refers to unwanted signals that can interfere with the transmitted signal.

### Bandwidth

Bandwidth determines the capacity of the transmission medium.

---

## 13. Key Terms to Remember

|Term|Definition|
|---|---|
|Physical Layer|OSI Layer 1, responsible for transmitting bits.|
|Bandwidth|Maximum transmission capacity.|
|Throughput|Actual amount of data transferred.|
|Goodput|Useful application data successfully delivered.|
|Encoding|Converting bits into recognizable patterns.|
|Signaling|Representing data using physical signals.|
|EMI|Electromagnetic interference.|
|RFI|Radio-frequency interference.|
|Crosstalk|Interference between signals in nearby wire pairs.|
|Attenuation|Reduction in signal strength.|
|UTP|Unshielded Twisted Pair.|
|STP|Shielded Twisted Pair.|
|SMF|Single-Mode Fiber.|
|MMF|Multimode Fiber.|
|OLT|Optical Line Terminal.|
|ONT|Optical Network Terminal.|

---

## 14. Module Summary

The Physical Layer is responsible for transmitting raw bits across a physical transmission medium.

Its responsibilities include defining:

- Physical connections and components.
    
- Electrical, optical, and wireless signals.
    
- Encoding and signaling.
    
- Transmission speed and characteristics.
    

Three main transmission media are used in networking:

1. Copper: Transmits electrical signals.
    
2. Fiber-optic: Transmits light signals.
    
3. Wireless: Transmits electromagnetic waves.
    

**Remember:** The Physical Layer deals with the physical transmission of bits, not the interpretation of network data.