# Module 4: Physical Layer

[All modules](Startup.md) · [Module 3](Module-3.md)

[Full Module 4 study guide](Class-Documents/Module-4-Physical-Layer-Study-Guide.md)

The **physical layer (OSI Layer 1)** sends raw bits over a network link. The sending device converts bits into electrical signals on copper, light pulses in fiber, or radio waves over wireless. The receiving device converts those signals back into bits. Physical layer standards define the media, connectors, and signaling rules that let devices communicate.

## 4.1 Physical connections

A network interface card (NIC) connects a device to the local network. An Ethernet NIC uses a cable to reach a switch or LAN port. A wireless LAN NIC uses radio waves to reach an access point. A home wireless router often combines a Wi-Fi access point, several LAN switchports, and a separate Internet (WAN) port.

Layer 2 builds an Ethernet frame around the IP packet. Layer 1 takes the frame's bits and sends them as signals. The receiving interface recovers those bits and hands the frame back to Layer 2.

## 4.2 Standards, encoding, and signaling

Physical layer standards cover the components (NICs, ports, connectors, and media), how bits are encoded, and how the encoded information is sent. The lesson names IEEE, ISO, TIA/EIA, ITU, and ANSI among the organizations involved.

**Encoding** defines the pattern used to represent bits. In the lesson's Manchester example for 10BASE-T, the signal changes halfway through every bit period. A high-to-low transition represents 0, and low-to-high represents 1. **Signaling** is how the link puts that pattern onto the medium, such as changes in voltage on copper, light on fiber, or radio waves in the air.

## Network media

| Medium | How it carries bits | When to use it |
| --- | --- | --- |
| Copper | Electrical signals | Twisted-pair Ethernet is common for connecting PCs and switches. Twisting reduces crosstalk, and shielding can reduce outside interference. Coaxial is another type of copper cable. |
| Fiber optic | Pulses of light | Useful for longer links and locations with electrical interference. Single-mode fiber is typical for longer distances. Multimode fiber is common for shorter links within buildings and data centers. |
| Wireless | Radio waves | Useful when devices need mobility or running cable is impractical. Distance, walls, interference, and other devices sharing the channel can reduce performance. |

## 4.3 Copper cabling and interference

Copper is relatively inexpensive and easy to install. **Attenuation** is the weakening of the signal over distance, which is why cable standards specify length limits. **EMI** (electromagnetic interference) and **RFI** (radio-frequency interference) can distort a signal. **Crosstalk** happens when a signal on one pair interferes with another pair.

| Cable | Construction and use |
| --- | --- |
| UTP (unshielded twisted pair) | Four color-coded wire pairs in a plastic jacket. Twisting helps the receiver reject common noise, and different twist rates reduce coupling between pairs. Common for Ethernet LANs. |
| STP (shielded twisted pair) | Twisted pairs with additional foil or braid shielding. It provides better protection in electrically noisy locations and requires compatible shielded connectors and proper grounding. |
| Coaxial | A center conductor surrounded by insulation, a conductive shield, and an outer jacket. Used for cable internet and RF antenna connections. The lesson shows BNC, N-type, and F-type connectors. |

## Ethernet cabling

Twisted-pair Ethernet typically uses an **RJ-45** connector. **T568A** and **T568B** define the wire order. A straight-through cable uses the same wiring standard on both ends. A traditional crossover cable uses T568A on one end and T568B on the other. Ports with **auto-MDIX** can detect the wiring and adjust automatically.

### 4.4 UTP standards and termination

TIA/EIA-568 covers cable types and lengths, connectors, termination, and testing. The RJ-45 plug is crimped onto the cable. The socket is the matching jack on a device, wall outlet, or patch panel. For a clean termination, keep the pairs twisted close to the contacts and seat the outer jacket inside the plug so the strain relief grips it.

| Cable wiring | Typical use |
| --- | --- |
| Straight-through (A-to-A or B-to-B) | Host to switch or switch to router. |
| Traditional crossover (A-to-B) | Like devices on older Ethernet interfaces without auto-MDIX, such as switch to switch or PC to PC. |
| Cisco rollover | A workstation connection to a router or switch console port for management. |

Cat 3 was used for voice and early data. Cat 5 is associated with Fast Ethernet, and Cat 5e commonly supports Gigabit Ethernet. Higher categories such as Cat 6, 6A, and 8 can support faster Ethernet standards when the cable length and equipment meet the relevant specifications. If a link fails, check the ports, cable type, and termination first.

[RJ-45 wiring diagram and pinout](RJ-45-Cabling.md)

## 4.5 Fiber-optic cabling

Fiber carries pulses of light through a thin glass core. Cladding guides the light, and a coating protects the fiber. Compared with copper, fiber can cover longer distances with less signal loss and is immune to EMI and RFI. Optics and installation can cost more.

- **Single-mode fiber (SMF)** has a small core, about 9 µm in the lesson diagram. A laser sends light through a single mode, making SMF suitable for long-distance links.
- **Multimode fiber (MMF)** has a larger core that supports multiple light paths. The paths spread the pulse over distance, so MMF is usually used for shorter links within a building or data center.

### Fiber types and uses

Both types shown use 125 µm glass cladding. MMF has a 50 or 62.5 µm core. Its different light paths can arrive at different times, spreading the pulse. This is **modal dispersion**, which limits how far MMF can carry data at a given rate. Reach depends on the fiber grade and transceiver. SMF is common in long-haul networks, while MMF is common on shorter LAN links.

Fiber connects enterprise backbone equipment, brings broadband to homes (FTTH), links cities and countries, and carries high-capacity traffic across oceans.

### Fiber connectors and patch cords

| Connector | How to recognize it |
| --- | --- |
| ST (straight-tip) | Round connector with a twist-lock bayonet. |
| SC (subscriber connector) | Square connector with a push-pull mechanism. Used with SMF and MMF. |
| LC simplex (Lucent connector) | Compact latch connector for one fiber. |
| LC duplex | Two LC connectors paired for transmit and receive fibers. |

An **SFP** is a small form-factor pluggable transceiver that can provide an optical interface on supported switches and routers. A typical full-duplex optical link uses one strand per direction. A bidirectional standard such as **100BASE-BX** uses different wavelengths to send and receive on the same strand.

Patch cord names indicate the connector at each end. The lesson shows SC–SC and ST–LC multimode examples, plus LC–LC and SC–ST single-mode examples. Yellow is a common SMF jacket color, and orange or aqua are common MMF jacket colors. Dust caps protect unused connector ends.

| Feature | UTP copper | Fiber optic |
| --- | --- | --- |
| Typical role | Short links from hosts to switches | High-capacity backbones and links between buildings |
| Distance | Many Ethernet channels are limited to 100 m | Longer reach, depending on the fiber and optics |
| Interference | Susceptible to EMI and RFI | Optical signals are immune to EMI and RFI |
| Installation | Generally lower cost and simpler termination | Optics and specialized termination can raise cost |

## 4.6 Wireless media

Wireless carries bits using radio or microwave signals and lets users move around while staying connected. Walls and terrain limit coverage, and nearby radios or appliances can cause interference. Signals can reach beyond the intended coverage area, so access controls matter. Devices share airtime on a channel, and more active devices can reduce each user's throughput.

| Technology | Standard or family | Typical use |
| --- | --- | --- |
| Wi-Fi | IEEE 802.11 | Wireless LAN. With CSMA/CA, devices listen before transmitting and defer when the channel is busy. |
| Bluetooth | Wireless personal area networking (WPAN) | Short-range connections between paired devices. |
| WiMAX | IEEE 802.16 | Point-to-multipoint wireless broadband. |
| Zigbee | Based on IEEE 802.15.4 | Low-power, low-data-rate communication for sensors and other IoT devices. |

A **wireless access point (AP)** connects wireless clients to the wired LAN. A **wireless NIC** gives a host the ability to join the WLAN. A home wireless router often combines an AP, an Ethernet switch, and a router.

## Bandwidth, throughput, and goodput

- **Bandwidth** is the link's capacity, typically expressed in bits per second.
- **Latency** is the time data takes to travel between two points, including delays.
- **Throughput** is the rate actually achieved during a transfer. Congestion, shared media, and slower links can reduce it.
- **Goodput** is the rate of useful data delivered to the application, excluding overhead and retransmitted data.

For example, a 1 Gbps link might deliver 800 Mbps of throughput but only 750 Mbps of useful application data.

Bandwidth measures how many bits a link can carry per second. The slowest link along a path limits the end-to-end rate. A path with 1 Gbps links and one 100 Mbps link cannot deliver more than 100 Mbps across that bottleneck.

| Unit | Bits per second |
| --- | ---: |
| bps | 1 |
| kbps | 1,000 |
| Mbps | 1,000,000 |
| Gbps | 1,000,000,000 |
| Tbps | 1,000,000,000,000 |

*Expanded using the supplied Cisco Networking Academy Module 4 screenshots.*

[Source: Cisco Networking Academy course outline and standards alignment](https://go.netacad.com/rs/059-VFZ-834/images/Cisco%20NetAcad%20CCNA1%20ITN%20Education%20Standards.pdf)
