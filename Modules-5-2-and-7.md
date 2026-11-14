# Switching Unit Part 2

[All modules](Startup.md) · [Modules 5.1 and 6](Modules-5-1-and-6.md)

This deck covers Section 5.2 (Hexadecimal Number System) and Module 7 (Ethernet Switching).

[Original slide PDF](Slides/Switching-Unit-Part-2/Switching-Unit-Part-2.pdf)

## Presentation slides

### Introduction

![Slide 1 — The Switching Unit Part 2](Slides/Switching-Unit-Part-2/Slide-01.png)

![Slide 2 — Agenda](Slides/Switching-Unit-Part-2/Slide-02.png)

### Hexadecimal and binary

![Slide 3 — Hexadecimal](Slides/Switching-Unit-Part-2/Slide-03.png)

![Slide 4 — Hexadecimal to Binary Conversion](Slides/Switching-Unit-Part-2/Slide-04.png)

![Slide 5 — Hexadecimal to Binary Conversion](Slides/Switching-Unit-Part-2/Slide-05.png)

![Slide 6 — Hexadecimal to Binary Conversion](Slides/Switching-Unit-Part-2/Slide-06.png)

![Slide 7 — Hexadecimal to Binary Conversion](Slides/Switching-Unit-Part-2/Slide-07.png)

![Slide 8 — Hexadecimal to Binary Conversion](Slides/Switching-Unit-Part-2/Slide-08.png)

![Slide 9 — Hexadecimal to Binary Conversion](Slides/Switching-Unit-Part-2/Slide-09.png)

![Slide 10 — Hexadecimal to Binary Conversion](Slides/Switching-Unit-Part-2/Slide-10.png)

![Slide 11 — Hexadecimal to Binary Conversion](Slides/Switching-Unit-Part-2/Slide-11.png)

![Slide 12 — Hexadecimal to Binary Conversion](Slides/Switching-Unit-Part-2/Slide-12.png)

![Slide 13 — Hexadecimal to Binary Conversion](Slides/Switching-Unit-Part-2/Slide-13.png)

![Slide 14 — Hexadecimal to Binary Conversion](Slides/Switching-Unit-Part-2/Slide-14.png)

![Slide 15 — Hexadecimal to Binary Conversion](Slides/Switching-Unit-Part-2/Slide-15.png)

![Slide 16 — Binary to Hexadecimal Conversion](Slides/Switching-Unit-Part-2/Slide-16.png)

![Slide 17 — Binary to Hexadecimal Conversion](Slides/Switching-Unit-Part-2/Slide-17.png)

![Slide 18 — Binary to Hexadecimal Conversion](Slides/Switching-Unit-Part-2/Slide-18.png)

#### Decimal, binary, and hexadecimal equivalents (0–F)

![Decimal and Binary Equivalents of 0 to F Hexadecimal](Slides/Switching-Unit-Part-2/Decimal-Binary-Hexadecimal-Equivalents.png)

#### Selected decimal, binary, and hexadecimal equivalents (8-bit)

![Selected Decimal, Binary, and Hexadecimal Equivalents](Slides/Switching-Unit-Part-2/Selected-Decimal-Binary-Hexadecimal-Equivalents.png)

### Ethernet frames and address types

![Slide 19 — Ethernet Frames](Slides/Switching-Unit-Part-2/Slide-19.png)

![Slide 20 — Broadcast](Slides/Switching-Unit-Part-2/Slide-20.png)

![Slide 21 — Multicast](Slides/Switching-Unit-Part-2/Slide-21.png)

![Slide 22 — Unicast](Slides/Switching-Unit-Part-2/Slide-22.png)

### Switch learning, forwarding, and filtering

![Slide 23 — Switch Fundamentals](Slides/Switching-Unit-Part-2/Slide-23.png)

![Slide 24 — Switch Learning](Slides/Switching-Unit-Part-2/Slide-24.png)

![Slide 25 — Switch Forwarding](Slides/Switching-Unit-Part-2/Slide-25.png)

![Slide 26 — Switch Filtering](Slides/Switching-Unit-Part-2/Slide-26.png)

### Switch It practice

![Slide 27 — Switch It!](Slides/Switching-Unit-Part-2/Slide-27.png)

![Slide 28 — Switch It!](Slides/Switching-Unit-Part-2/Slide-28.png)

![Slide 29 — Switch It!](Slides/Switching-Unit-Part-2/Slide-29.png)

![Slide 30 — Switch It!](Slides/Switching-Unit-Part-2/Slide-30.png)

### Forwarding methods and auto-MDIX

![Slide 31 — Switch Forwarding](Slides/Switching-Unit-Part-2/Slide-31.png)

![Slide 32 — Auto MDIX](Slides/Switching-Unit-Part-2/Slide-32.png)

![Slide 33 — Auto MDIX](Slides/Switching-Unit-Part-2/Slide-33.png)

![Slide 34 — Questions?](Slides/Switching-Unit-Part-2/Slide-34.png)


---

## Expanded learning reference — Modules 5.2 and 7


### Module 5.2 — Hexadecimal number system

**Number systems** use a base (radix). Decimal is base 10 (digits 0–9); binary is base 2 (0 and 1); hexadecimal is base 16 (0–9 and A–F). In hex, A=10, B=11, C=12, D=13, E=14, and F=15. A **bit** is one binary digit; a **nibble** is 4 bits; a **byte** is 8 bits. One hex digit represents exactly four bits, so two hex digits represent a byte.

**Hex → binary:** Replace each hex digit with its four-bit equivalent, preserving leading zeros. Example: `CA` = `C` (`1100`) + `A` (`1010`) = `11001010`. For `0F`, write `0000 1111`, not just `1111`, when showing a full byte.

**Binary → hex:** Split the bits into groups of four starting at the right. Pad the leftmost group with zeros if necessary. Example: `1100 1010` → `1100` (`C`) and `1010` (`A`) → `CA`.

**Decimal → hex:** Divide repeatedly by 16 and read remainders from last to first. Example: 202 ÷ 16 = 12 remainder 10 → `C` and `A` → `CA`. Or use place values: `CA` = 12×16 + 10 = 202.

**Useful byte landmarks:** `00`=0, `0A`=10, `0F`=15, `10`=16, `20`=32, `40`=64, `80`=128, `C0`=192, `CA`=202, `F0`=240, `FF`=255. A byte ranges from decimal 0 to 255. Hexadecimal is used to display MAC addresses and other binary values compactly.

### Module 7 — Ethernet frames

Ethernet is a Layer 2 technology that carries data in **frames**. An Ethernet frame contains addressing information, payload, and error detection. The study guide's frame-field table is reproduced in the original document; this is a plain-language guide to what each field does.

| Field | Typical size | Why it matters |
| --- | --- | --- |
| Preamble + Start Frame Delimiter (SFD) | 7 + 1 bytes | Helps receiving devices synchronize and recognize the start of a frame. |
| Destination MAC | 6 bytes | Identifies the intended receiver or receiver group; switches inspect it to decide where to forward. |
| Source MAC | 6 bytes | Identifies the sender's interface; switches use it to learn where devices are connected. |
| Type/Length | 2 bytes | Indicates the encapsulated protocol (EtherType) or payload length, depending on framing. |
| Data and padding | 46–1500 bytes in standard Ethernet | Contains the upper-layer data; padding brings short payloads to the minimum size. |
| Frame Check Sequence (FCS) | 4 bytes | Contains a CRC value used to detect frame corruption; bad frames are discarded. |

A standard Ethernet frame from destination MAC through FCS is normally **64–1518 bytes**, excluding preamble and SFD, without a VLAN tag. A VLAN-tagged frame is typically four bytes longer. The **64-byte minimum** is why short payloads require padding.

### Unicast, broadcast, and multicast MAC destinations

| Type | Meaning | Typical behavior |
| --- | --- | --- |
| Unicast | One destination interface | If the destination MAC is learned, the switch forwards to the matching port. |
| Broadcast | All devices in the local broadcast domain | Ethernet destination `FF:FF:FF:FF:FF:FF`; the switch floods to other ports in the same VLAN. |
| Multicast | A selected group of receivers | Frames are addressed to a multicast group; forwarding depends on switch features and group membership information. |

A frame has a **source MAC** and a **destination MAC**. The terms above describe its *destination*, not a special kind of source. A switch does not normally forward broadcasts beyond a router into a different broadcast domain.

### How a switch learns, forwards, floods, and filters

1. **Learn from the source:** On each received frame, the switch records the **source MAC → incoming port** association in its MAC address table (per VLAN). If already present, it refreshes the entry; if the device moves, the association may change.
2. **Look up the destination:** The switch compares the **destination MAC** with entries in its table.
3. **Known unicast:** Forward the frame only through the associated outgoing port, rather than every port.
4. **Unknown unicast:** Flood the frame out eligible ports in the same VLAN **except** the port it arrived on. The receiving device's reply can help the switch learn its location.
5. **Broadcast:** Flood to other eligible ports in the VLAN. Multicast forwarding may be selective or flooded, depending on configuration.
6. **Filter:** If the destination is on the same port as the source, the switch need not send the frame back out that port. More broadly, known-unicast forwarding avoids sending copies to unrelated ports.

**Worked example:** PC-A is on port 1 and PC-B on port 3. When PC-A sends a frame, the switch learns `A → port 1`. If B is unknown, it floods the frame to other eligible ports. When B replies, the switch learns `B → port 3`. Later traffic from A to B can go directly to port 3. Many switches age out inactive dynamic entries after about **300 seconds (5 minutes)**, though the configured aging time can vary.

**Cisco verification:** `show mac address-table` displays learned MAC addresses and their associated VLANs/ports. A MAC address table is **not** the same as an ARP table: MAC learning maps MAC addresses to switch ports, while ARP maps IPv4 addresses to MAC addresses.

### Frame forwarding methods

| Method | What the switch does | Tradeoff |
| --- | --- | --- |
| **Store-and-forward** | Receives the entire frame, checks the FCS, then forwards valid frames. | Better error checking; must wait for the full frame. |
| **Cut-through** | Begins forwarding once it has read enough header information to identify the destination. | Lower forwarding latency, but may forward a corrupted frame because full FCS verification has not yet happened. |

Store-and-forward is commonly used on modern switches and supports decisions that require inspecting the whole frame. The key distinction is **whether the switch waits for the complete frame before forwarding**.

### Auto-MDIX

**Auto-MDIX** (automatic medium-dependent interface crossover) automatically detects the required transmit/receive pair arrangement on supported copper Ethernet ports. This means a compatible switch can typically work with either a straight-through or crossover Ethernet cable without manually selecting the cable type. It does **not** repair damaged cables or guarantee a link when speed, wiring, or hardware is incompatible. Cisco devices may enable it by default depending on model and software; where supported, the interface command is `mdix auto`.

### Quick concept checks (for self-study)

- Why does one hexadecimal digit always correspond to four binary bits?
- What would change in the MAC table when a computer is moved from port 1 to port 4?
- Why does an unknown-unicast frame reach more ports than a known-unicast frame?
- Which Ethernet field helps detect corrupted frames?
- Why might a switch use store-and-forward rather than cut-through?
- What wiring problem does Auto-MDIX help avoid?

**Source boundary:** Topics and terminology follow the uploaded Module 5.2 / Module 7 study guide and existing switching slide deck. Worked examples, clarifications, and concept checks above are newly written study explanations, not copied responses from the assignment.
