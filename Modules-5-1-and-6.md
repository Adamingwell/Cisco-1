# Cisco Introduction to Networks — Section 5.1 and Module 6

[All modules](Startup.md) · [Module 4](Module-4.md)

## 5.1 Binary Number System

### 5.1.1 Binary and IPv4 Addresses

An IPv4 address is 32 bits, grouped into four octets. Dotted decimal is a readable way to write the same address, one number per octet.

| Device or interface | Network | Dotted decimal | Binary |
| --- | --- | --- | --- |
| PC1 | LAN A | `192.168.10.10` | `11000000.10101000.00001010.00001010` |
| R1 G0/0/0 (PC1's gateway) | LAN A | `192.168.10.1` | `11000000.10101000.00001010.00000001` |
| R1 G0/0/1 (PC2's gateway) | LAN B | `192.168.11.1` | `11000000.10101000.00001011.00000001` |
| PC2 | LAN B | `192.168.11.10` | `11000000.10101000.00001011.00001010` |

LAN A is `192.168.10.0/24) and LAN B is `192.168.11.0/24`. A `/24` uses the first 24 bits for the network prefix. R1 connects both LANs, so each PC uses R1's interface on its own LAN to reach the other network.

### 5.1.3 Binary Positional Notation

The **radix** is the number base. The rightmost digit has exponent 0, and the exponent increases by one for each place to its left. In base 10, `1234` is 1 × 1000 + 2 × 100 + 3 × 10 + 4 × 1. In base 2, each bit contributes either its place value or zero.

| Exponent | 7 | 6 | 5 | 4 | 3 | 2 | 1 | 0 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Power of 2 | 2⁷ | 2⁶ | 2⁵ | 2⁴ | 2³ | 2² | 2¹ | 2⁰ |
| Place value | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |

### 5.1.5 Binary to Decimal

Convert each octet separately by adding the place values with a 1.

| Binary octet | Add these values | Decimal |
| --- | --- | --- |
| `11000000` | 128 + 64 | 192 |
| `10101000` | 128 + 32 + 8 | 168 |
| `00001011` | 8 + 2 + 1 | 11 |
| `00001010` | 8 + 2 | 10 |

Join the results in order to get **`192.168.11.10`**.

### 5.1.7 Decimal to Binary

Start at 128 and work toward 1. If the place value fits the remainder, write 1 and subtract it. Otherwise, write 0. Keep all eight bits, including leading zeros.

For **192**, subtract 128 to get 64, then subtract 64 to get zero. The remaining places are all zero, giving `11000000`. Applying the same process to each octet, **`192.168.10.11`** becomes **`11000000.10101000.00001010.00001011`**.

<details>
<summary>Check your practice conversions</summary>

- `00010011` → **19** (16 + 2 + 1).
- **226** → `11100010` (128 + 64 + 32 + 2).

</details>

## 6.1 Purpose of the Data Link Layer

Layer 2 lets network interfaces exchange frames without requiring IP to handle the details of each medium. A **node** can be an endpoint, such as a PC or server, or an intermediary, such as a switch or router.

| IEEE 802 sublayer | Job |
| --- | --- |
| **LLC (Logical Link Control)** | Connects upper-layer protocols to the interface. Protocol identification lets IPv4 and IPv6 share the same interface and medium. |
| **MAC (Media Access Control)** | Handles frame boundaries, link-layer addressing, and error detection. On shared media it also manages when devices can transmit. |

The lesson pairs LLC with **IEEE 802.2** and shows **802.3** for Ethernet, **802.11** for wireless LANs, and **802.15** for wireless personal area networks.

**Local example.** When PC1 (`192.168.1.110`) sends to a web server (`192.168.1.5`) on the same LAN, the Layer 2 header identifies the two interfaces by their Ethernet MAC addresses. The Layer 3 packet inside the frame carries the two IP addresses.

**Across a router.** A router can receive an Ethernet frame on its LAN interface and forward the packet in a different frame over a serial WAN link.

1. Receive the incoming frame.
2. Remove the Layer 2 framing to recover the packet.
3. Select the outgoing interface and wrap the packet in a new frame for that link.
4. Send the new frame over the outgoing medium.

For a remote destination, the first Ethernet frame goes to the default gateway’s MAC address. The packet still names the remote host’s IP address as its destination.

### Network access standards

The lesson highlights IEEE (Institute of Electrical and Electronics Engineers), ITU (International Telecommunication Union), ISO (International Organization for Standardization), and ANSI (American National Standards Institute) as organizations involved in network access standards. The IETF publishes RFCs for many TCP/IP protocols, while IEEE defines Ethernet and Wi-Fi standards.

## 6.2 Topologies and Media Access

### Physical and logical topology

A **physical topology** shows device locations and connections, such as the switch, rack, and cable that serve a classroom. A **logical topology** shows how data travels, including the interfaces and subnets that connect each classroom to the router. The logical layout helps determine the framing and access rules for each link.

| Topology | How devices connect |
| --- | --- |
| WAN point-to-point | A link joins two endpoints. It can appear direct to the endpoints even when a provider's equipment lies between them. Serial PPP assumes a single peer. Ethernet still checks destination MAC addresses on a two-device link. |
| WAN hub and spoke | Branch sites connect to a central site. Traffic between branches typically passes through the hub. |
| WAN mesh | Sites have multiple connections. A full mesh connects every pair of sites, while a partial mesh connects only some pairs. |
| LAN star and extended star | End devices connect to a central switch. Linking several switches extends the star. |
| Legacy LAN bus and ring | A bus uses a shared backbone terminated at both ends. A ring forms a loop, as in legacy Token Ring and FDDI networks. |

### Duplex and access methods

**Half duplex** permits transmission in one direction at a time, as on a legacy Ethernet hub link. **Full duplex** permits simultaneous sending and receiving, as on a typical switched Ethernet link. Both ends should agree on duplex. A mismatch can cause errors, slow transfers, and delays.

| Access method | How it works | Example |
| --- | --- | --- |
| Contention with CSMA/CD | A device listens before sending. If two devices transmit and collide, they stop, wait for random intervals, and retry. A hub repeats signals to its other ports. | Legacy shared Ethernet |
| Contention with CSMA/CA | A device checks the channel and waits before sending. Duration information tells nearby stations how long to defer. A successful unicast exchange normally gets an acknowledgment. | Wi-Fi (IEEE 802.11) |
| Controlled access | Devices wait for permission to send, such as receiving a token. | Legacy Token Ring and ARCNET |

Full-duplex switched Ethernet links can carry traffic in both directions without competing for a shared channel, so they do not use CSMA/CD.

## 6.3 The Data Link Frame

A frame wraps a packet in a **header** and **trailer**. The exact fields depend on the link protocol. Wi-Fi, for example, needs control information for sharing the wireless channel.

| Field or part | Role |
| --- | --- |
| Frame boundaries | Help the receiver recognize the beginning and end of a frame. |
| Header | May carry local source and destination addresses, a protocol type, and control information such as traffic priority. |
| Payload | Carries the encapsulated data, such as an IPv4 or IPv6 packet. |
| Trailer | In Ethernet, the Frame Check Sequence (FCS) stores a value calculated with a cyclic redundancy check (CRC). The receiver calculates its own value and discards the frame if the values differ. |

### Layer 2 addresses across routed links

Layer 2 addresses identify interfaces on the current link. IP addresses identify the source and final destination across networks. In the lesson's example, the IP source is `192.168.1.110` and the IP destination is `172.16.1.99` throughout ordinary routing without address translation.

| Ethernet hop | Source MAC | Destination MAC |
| --- | --- | --- |
| PC1 to R1 | PC1's interface | R1's LAN interface |
| R1 to R2 | R1's outgoing interface | R2's receiving interface |
| R2 to web server | R2's outgoing interface | Web server's interface |

Routers replace the frame for each outgoing link. Link protocols such as serial PPP can use a different addressing format from Ethernet. Examples of Layer 2 protocols include Ethernet, Wi-Fi, PPP, HDLC, and Frame Relay. The choice depends on the medium and logical topology.

*Study summary based on the supplied Cisco Networking Academy lesson screenshots.*

[Source — Cisco Press Introduction to Networks Companion Guide](https://www.ciscopress.com/store/introduction-to-networks-companion-guide-ccnav7-9780136633556)
