<h1 align="center">🦅 Lammergeier</h1>

<p align="center">
  <b>An autonomous drone framework where the radio is a detail.</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/stage-design-orange?style=for-the-badge" />
  <img src="https://img.shields.io/badge/LoRa-2ea44f?style=for-the-badge" />
  <img src="https://img.shields.io/badge/UAV-1f6feb?style=for-the-badge" />
</p>

---

> ⚙️ **Design stage.** Architecture, hardware selection and communication models are still being
> defined. No implementation here yet.

Most drone stacks make you pick your radio early and then build around it. Swap Wi-Fi for LoRa, or
move to a high-power analog FPV setup, and you're reworking everything above the transport.

Lammergeier puts flight control, PID stabilization, mission automation and ground command under
**one architecture**, and keeps the transport swappable underneath it.

## Goals

- **One stack, not four.** Control, stabilization, mission logic and command as parts of a system.
- **Transport independence.** Wi-Fi · LoRa · FPV · analog, without touching the layers above.
- **Manual and autonomous together.** The handover designed in, not bolted on.
- **Hardware-adaptive.** Discover and accommodate the sensors and transmitters it finds.

## Where it's going

| | |
|---|---|
| **0. Design** *(current)* | Architecture, hardware, comms model |
| **1. Core** | Attitude/rate loops, PID, failsafe on one airframe |
| **2. Transport** | The abstraction that makes the radio swappable |
| **3. Autonomy** | Waypoints, mission state machine |
| **4. Command** | Centralized ground station |

## Related

**[gen-fsm](https://github.com/byte-me-pls/gen-fsm)**: the `no_std` navigation study behind this ·
**[alkor-simulation](https://github.com/byte-me-pls/alkor-simulation)**: consensus over the kind of
LoRa mesh this targets

## Contributing

Still at the design stage, so the useful contribution right now is **discussion**. Open an issue if
you've worked on any of the above.

## License

MIT
