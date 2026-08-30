# 🦅 Lammergeier — Unified Autonomous Drone System

> ⚙️ **Project status: early design and planning.**
> System architecture, hardware selection and communication models are being defined before active
> development begins. There is no implementation in this repository yet.

Lammergeier is a modular, all-in-one autonomous drone framework that puts flight control, PID
stabilization, mission automation and centralized command under a single architecture.

## The idea

Most drone stacks make you choose your radio early and then build around it. Swapping a Wi-Fi link
for LoRa, or moving from digital telemetry to a high-power analog FPV setup, means reworking
everything above the transport.

Lammergeier is being designed so the transport is a detail. Wi-Fi, LoRa, FPV or analog — the core
structure stays the same, and the framework adapts to whatever hardware and environment it finds.

## Goals

- **One architecture, not four.** Flight control, stabilization, mission logic and ground command as
  parts of a single system rather than separately integrated projects.
- **Transport independence.** Wi-Fi, LoRa, FPV, high-power analog — swappable without touching the
  layers above.
- **Manual and autonomous in the same stack.** Full pilot control and fully autonomous missions,
  with the handover between them designed in rather than bolted on.
- **Scalable and open.** Usable from a single airframe up to a coordinated group.
- **Hardware-adaptive.** Sensor and transmitter configuration discovered and accommodated at
  runtime where possible.

## Planned scope

| Area | What it covers |
|---|---|
| Flight control | Attitude and rate loops, PID stabilization, failsafe behaviour |
| Mission automation | Waypoints, mission state machine, autonomous decision-making |
| Communication | Transport abstraction over Wi-Fi / LoRa / FPV / analog links |
| Command station | Centralized monitoring and control for one or more aircraft |
| Hardware layer | Sensor and transmitter abstraction |

## Roadmap

| Phase | Goal |
|---|---|
| **0 — Design** *(current)* | Architecture, hardware selection, communication model |
| **1 — Core** | Flight control and stabilization on a single airframe |
| **2 — Transport layer** | The abstraction that makes the radio swappable |
| **3 — Autonomy** | Mission automation and autonomous flight |
| **4 — Command** | Centralized ground station |

## Related work

- [**gen-fsm**](https://github.com/byte-me-pls/gen-fsm) — `no_std` stochastic-genetic state machine
  for embedded autonomy; its `drone_nav` example is the navigation study behind this.
- [**alkor-simulation**](https://github.com/byte-me-pls/alkor-simulation) — Rotating Leader
  consensus over a LoRa mesh, simulating the kind of link Lammergeier targets.

## Contributing

The project is still at the design stage, so the most useful contribution right now is discussion —
open an issue if you have experience with any of the areas above.

## License

MIT — see [LICENSE](LICENSE).
