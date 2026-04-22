<p align="center">
  <img src="assets/logo.svg" alt="IPIS Logo" width="200">
  <br>
  <em>Duranki – The Bond of Heaven and Earth</em>
</p>

# IPIS / Duranki – InterPlanetary Identity System

[![Concept Status](https://img.shields.io/badge/status-concept-blue)](https://github.com/snowdimon/IPIS)
[![Version](https://img.shields.io/badge/version-15.0-green)](https://github.com/snowdimon/IPIS/releases)
[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)
[![GitHub issues](https://img.shields.io/github/issues/snowdimon/IPIS)](https://github.com/snowdimon/IPIS/issues)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

> *“There’s a starman waiting in the sky…”* – David Bowie, *Starman* (1972)

**IPIS (InterPlanetary Identity System)** is a voluntary protocol for identification, access control, and navigation in the Solar System. Its codename is **Duranki** (ancient Sumerian for *The Bond of Heaven and Earth*).

> **IPIS is not just a design system — it is a socio‑technical operating system.**  
> Rockets are hardware. IPIS is the software that enables different people, nations, and machines to work together without conflict.

<p align="center">
  <img src="assets/circle_hex.svg" alt="Basic symbols" width="300">
</p>

IPIS gives every object (human, spacecraft, robot) a **human‑readable code** and a **stackable history of visited worlds** – the **Snezhkov Stack**.

It does not replace national flags or existing systems (NORAD, transponders). It works alongside them, creating a shared semantic layer for space activities.

---

## Key Features

- **Simple coding** – circle (human/base), hexagon (robot), numbers 01 (Earth), 02 (Moon), 03 (Mars), indices `'` (orbit), `E` (EVA), `00` (deep space).  
- **Snezhkov Stack** – horizontal row of touching small discs, each with a world number. First disc = birthplace, then work locations (>6 months). `E` disc after any world where EVAs were performed.  
  <p align="center"><img src="assets/stack_layout.svg" alt="Stack layout" width="200"></p>
- **Ship Thread** – straight line on the hull from start to end node (e.g. `01—03`). Intermediate manoeuvres are digital only.  
  <p align="center"><img src="assets/ship_thread.svg" alt="Ship thread" width="300"></p>
- **Two‑layer patch** – outer layer shows current code; under it hides a flat disc (future stack element). When you leave a base, the outer layer is peeled off and the disc is added to your stack. No need to print new patches in space.  
  <p align="center"><img src="assets/two_layer_patch.svg" alt="Two-layer patch" width="300"></p>
- **Ritual “Base Gulp”** – a glass of local water, a sip, the sound of Velcro – a symbolic admission into the new ecosystem.  
- **Technical integration** – RFID chips in patches for access control; `IPIS_CODE` field in NORAD / Space‑Track.org catalog. Stack verification is based on ship and base logbooks (digitally signed).  
---

## Star prefix (for far future)
SOL
CER

## Quick Example

A person born on Earth (`01`), who worked on a lunar orbital station with EVAs (`02’E`), and is currently on Mars (`03`):

- **Main patch:** circle with `03`  
- **Stack:** `01` `02’` `E`  
- **Two‑layer mechanism:** when leaving the lunar station, the outer `02’` patch was peeled off and the inner disc `02’` (plus the `E` disc earned there) became part of the stack.

---

## 🖼️ See It in Action

A picture is worth a thousand words. See how IPIS looks on a Martian suit, a spacecraft hull, and in mission control.

[![Visual Gallery](https://img.shields.io/badge/📸-Open_Gallery-blue)](https://snowdimon.github.io/IPIS/gallery/index.html)

> Click the badge above to open the interactive gallery.

---

## Repository Structure

- `presentation/` – slides (Markdown source, and eventually PDF)  
- `docs/` – full specifications, stack guide, RFID spec, NORAD extension, verification via logbooks, future expansion notes, cultural examples, quick start guide  
- `assets/` – SVG logo, patch designs, stack layout, ship thread, two‑layer diagram, basic symbols  
- `LICENSE` – CC BY-SA 4.0  
- `CONTRIBUTING.md` – how to help  
- `CODE_OF_CONDUCT.md` – community guidelines  

---

## How to Use This

1. **Quick start** – [Quick Start for Beginners](docs/quickstart.md) – make your first IPIS patch in 5 minutes.  
2. **Read the presentation** – [Slides](presentation/slides.md) (convert to PDF for printing).  
3. **Learn the stack mechanics** – [Stack Guide](docs/stack_guide.md) for detailed patch donning / updating.  
4. **Dive into technical integration** – [RFID spec](docs/rfid_spec.md) and [NORAD extension](docs/norad_extension.md).  
5. **Explore cultural examples** – [Stack Examples](docs/stack_examples.md) (Major Tom, John Carter, etc.).  

The system is **open** – you can adopt, modify, and pilot it. Feedback and contributions are welcome.

---

## Contributing

We welcome contributions of all kinds: bug reports, design improvements, code, translations, and community building.  
Please read [CONTRIBUTING.md](CONTRIBUTING.md) and our [Code of Conduct](CODE_OF_CONDUCT.md) before submitting anything.

**Ways to help**:
- Create a mod for Kerbal Space Program, Star Citizen, or Elite Dangerous.  
- Translate documentation into other languages.  
- Improve SVG assets or add new examples.  
- Write a script to convert NORAD IDs to `IPIS_CODE`.  
- Spread the word – articles, videos, social media.

---

## Author

**Snezhkov D.**, 01 — EARTH  
Codename: **Duranki** (The Bond of Heaven and Earth)  
Version 15.0, April 2026

*“We build not a wall, but a bridge.”*
