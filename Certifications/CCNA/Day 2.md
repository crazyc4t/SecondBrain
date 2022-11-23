# Interfaces and cables
Switches have lots of interfaces (ports) that are connected with RJ-45s (Registered Jack) and they are really common, but before anything, what is ethernet?

# Ethernet
- Is a collection of network protocols/standards

**Why do we need to have network standards**
To have compatibility everywhere, so we can all communicate no matter the vendor or company behind it.

## Ethernet standards
- Defined in the IEEE 802.3 standard in 1983
- IEEE = Institute of Electrical and Electronics Engineers

**Copper standards**

| Speed    | Common Name      | IEEE Standard | Informal Name   | Maximum Length |
| -------  | ------------     | ------------- | --------------- | -------------- |
| 10 Mbps  | Ethernet         | 802.3i        | 10BASE-T        | 100 m          |
| 100 Mbps | Fast Ethernet    | 802.3u        | 100BASE-T       | 100 m          |
| 1 Gbps   | Gigabit Ethernet | 802.3ab       | 1000BASE-T      | 100 m          || 10 Gbps  | 10 gig Ethernet  | 802.3an       | 10GBASE-T       | 100 m          |

BASE = refers to baseband signaling
T = twisted pair

## 10BASE-T & 100BASE-T
- UTP (Unshielded twisted pair) 
- Being twisted protects the cable from EMI (Electromagnetic interference)

**Copper cable standards**
- 10BASE-T & 100BASE-T = 2 pairs (4 wires each RJ-45)

**Straight-through cable**
- Full duplex is when both devices can transmit and receive data at the same time without any collision
- Routers & PC network cards transmit data on pins 1 & 2 of a UTP cable and receive on 3 & 6
- Switches receive data on 1 & 2 and transmit data on 3 & 6

**Crossover cable**
This type of cable is used when trying to connect a router to a router or a switch to a switch, reversing the destination, meaning that if we transmit data on pin 3 & 6 of a UTP cable, the other end of the UTP cable would be the receiving pin 1 & 2.

| Device Type | Transmit (Tx) pins | Receive (Rx) Pins |
|-------------|--------------------|-------------------|
| Router      | 1 & 2              | 3 & 6             |
| Firewall    | 1 & 2              | 3 & 6             |
| PC          | 1 & 2              | 3 & 6             |
| Switch      | 3 & 6              | 1 & 2             |

**Auto MDI-X**
Although, is good knowing straight-through and crossover cable but nowadays that is no longer a problem since there's auto MDI-X, that automatically detects which pins the neighbor is transmitting and receiving data from and adjust accordingly.

## 1000BASE-T & 10GBASE-T
1000BASE-T & 10GBASE-T = 4 pairs (8 wires)

Each pin in the cable is **bidirectional**, meaning that each pin is made for transmitting and receiving data, making it faster.

## Fiber-Optic Connections
These are SFP transceiver (small form-factor pluggable), and you connect to it fiber optic cables, that send light over glass fiber, having two connectors, being one for receiving and other for transmitting, and there are different types of fiber optic cables:
- Single-mode:
  - Core diameter is narrower than multimode fiber
  - Light enters at a single angle (mode) from a laser-based transmitter
  - Allows longer cables than both UTP and multimode fiber 
  - More expensive than multimode fiber (due to more expensive laser-based SFP Tx)
- Multi-mode:
  - Core diameter is wider than single-mode fiber
  - Allows multiple angles (modes) of light waves to enter the fiberglass core 
  - Allows longer cables than UTP, but shorter cables than single-mode fiber
  - Cheaper than single mode fiber (due to cheaper LED-based SFP tx)

### Fiber-Optic Cable Standards
| Informal name | IEEE standard | Speed   | Cable type    | Maximum length        |
| ------------- | ------------- | ------  | ------------- | -------------         |
| 1000BASE-LX   | 802.3z        | 1 Gbps  | MM & SM       | 550m (MM) 5km (SM)    |
| 10GBASE-SR    | 802.3ae       | 10 Gbps | Multimode     | 400 m                 |
| 10GBASER-LR   | 802.3ae       | 10 Gbps | Single-mode   | 10 KM                 |
| 10GBASE-ER    | 802.3ae       | 10 Gbps | Single-mode   | 30 Km                 |

# UTP VS Fiber Optic Cabling
| UTP                             | Fiber-Optic                            |
| ---                             | -----------                            |
| Lower cost than fiber           | Higher cost than UTP                   |
| Shorter distance than fiber     | Longer distance than UTP               |
| Can be vulnerable to EMI        | No vulnerability to EMI                |
| RJ45 ports are cheaper than SFP | SFP ports are more expensive than RJ45 |
| More Security vulnerabilities   | No signal leaks                        |

## Bits and bytes
A bit one binary values, for example:
- 0
- 1 
  
And a byte is and octet of bits, meaning 8 bits is equal to 1 byte.

The way bits travel over networks is bit by bit, not with bytes as seen in hard drives.

Speed is measured in bits per second:

| Unit           | bits              |
| -------------- | ----------------- |
| 1 kilobit (kb) | 1000              |
| 1 megabit (mb) | 1,000,000         |
| 1 gigabit (gb) | 1,000,000,000     |
| 1 terabit (tb) | 1,000,000,000,000 |

## Resources

### Slides
![[Day 2 Slides - Interfaces and Cables.pdf]]

### Anki
![[Day 02 Flashcards - Interfaces and Cables.apkg]]

### Packet Tracer Labs
![[Day 02 Lab - Connecting Devices.pkt]]