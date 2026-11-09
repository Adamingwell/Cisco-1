# Module 4: Physical Layer

[All modules](Startup.md) · [Module 3](Module-3.md)

The **physical layer (OSI Layer 1)** sends raw bits over a network link. The sending device converts bits into electrical signals on copper, light pulses in fiber, or radio waves over wireless. The receiving device converts those signals back into bits. Physical layer standards define the media, connectors, and signaling rules that let devices communicate.

## Network media

| Medium | How it carries bits | When to use it |
| --- | --- | --- |
| Copper | Electrical signals | Twisted-pair Ethernet is common for connecting PCs and switches. Twisting reduces crosstalk, and shielding can reduce outside interference. Coaxial is another type of copper cable. |
| Fiber optic | Pulses of light | Useful for longer links and locations with electrical interference. Single-mode fiber is typical for longer distances. Multimode fiber is common for shorter links within buildings and data centers. |
| Wireless | Radio waves | Useful when devices need mobility or running cable is impractical. Distance, walls, interference, and other devices sharing the channel can reduce performance. |

## Ethernet cabling

Twisted-pair Ethernet typically uses an **RJ-45** connector. **T568A** and **T568B** define the wire order. A straight-through cable uses the same wiring standard on both ends. A traditional crossover cable uses T568A on one end and T568B on the other. Ports with **auto-MDIX** can detect the wiring and adjust automatically.

## Bandwidth, throughput, and goodput

- **Bandwidth** is the link's capacity, typically expressed in bits per second.
- **Throughput** is the rate actually achieved during a transfer. Congestion, shared media, and slower links can reduce it.
- **Goodput** is the rate of useful data delivered to the application, excluding overhead and retransmitted data.

For example, a 1 Gbps link might deliver 800 Mbps of throughput but only 750 Mbps of useful application data.

[Source: Cisco Networking Academy course outline and standards alignment](https://go.netacad.com/rs/059-VFZ-834/images/Cisco%20NetAcad%20CCNA1%20ITN%20Education%20Standards.pdf)
