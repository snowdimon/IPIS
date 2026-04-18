# IPIS / Duranki – InterPlanetary Identity System

[![Concept](https://img.shields.io/badge/status-concept-blue)](https://github.com/yourname/IPIS-Duranki)
[![Version](https://img.shields.io/badge/version-15.0-green)](https://github.com/yourname/IPIS-Duranki)
[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)

> *“There’s a starman waiting in the sky…”* – David Bowie, *Starman* (1972)

**IPIS (InterPlanetary Identity System)** is a voluntary protocol for identification, access control, and navigation in the Solar System. Its codename is **Duranki** (ancient Sumerian for *The Bond of Heaven and Earth*).

IPIS gives every object (human, spacecraft, robot) a **human‑readable code** and a **stackable history of visited worlds** – the **Snezhkov Stack**.

It does not replace national flags or existing systems (NORAD, transponders). It works alongside them, creating a shared semantic layer for space activities.

<p align="center">
  <img src="assets/logo.svg" alt="IPIS Logo" width="200" style="background-color: #0a1128; border-radius: 20px;">
</p>

---

## Key Features

- **Simple coding** – circle (human/base), hexagon (robot), numbers 01 (Earth), 02 (Moon), 03 (Mars), indices `'` (orbit), `E` (EVA), `00` (deep space).  
- **Snezhkov Stack** – horizontal row of touching small discs, each with a world number. First disc = birthplace, then work locations (>6 months). `E` disc after any world where EVAs were performed.  
- **Ship Thread** – straight line on the hull from start to end node (e.g. `01—03`). Intermediate manoeuvres are digital only.  
- **Two‑layer patch** – outer layer shows current code; under it hides a flat disc (future stack element). When you leave a base, the outer layer is peeled off and the disc is added to your stack. No need to print new patches in space.  
- **Ritual “Base Gulp”** – a glass of local water, a sip, the sound of Velcro – a symbolic admission into the new ecosystem.  
- **Technical integration** – RFID chips in patches for access control; `IPIS_CODE` field in NORAD / Space‑Track.org catalog. Stack verification is based on ship and base logbooks (digitally signed).  

---

## Quick Example

A person born on Earth (`01`), who worked on a lunar orbital station with EVAs (`02’E`), and is currently on Mars (`03`):

- **Main patch:** circle with `03`  
- **Stack:** `01` `02’` `E`  
- **Two‑layer mechanism:** when leaving the lunar station, the outer `02’` patch was peeled off and the inner disc `02’` (plus the `E` disc earned there) became part of the stack.

---

## Repository Structure

- `presentation/` – slides (PDF + source)  
- `docs/` – full specifications, stack guide, RFID spec, NORAD extension, verification via logbooks, future expansion notes, cultural examples  
- `assets/` – SVG logo, patch designs, stack layout, ship thread, two‑layer diagram  
- `LICENSE` – CC BY-SA 4.0  
- `CONTRIBUTING.md` – how to help  

---

## How to Use This

1. Read the [presentation](presentation/IPIS_Duranki.pdf)  
2. Check the [Stack Guide](docs/stack_guide.md) for detailed patch donning / updating  
3. See [technical integration](docs/rfid_spec.md) for RFID and NORAD  
4. Explore the [design kit](assets/) to make your own patches
5.[Quick Start for Beginners](docs/quickstart.md) – make your first IPIS patch in 5 minutes.

The system is **open** – you can adopt, modify, and pilot it. Feedback and contributions are welcome.

---

## Author

**Snezhkov D.**, 01 — EARTH  
Codename: **Duranki** (The Bond of Heaven and Earth)  
Version 15.0, April 2026

*“We build not a wall, but a bridge.”*
