# RFID Patch Specification – Technical Description

This document provides the technical details for manufacturing RFID‑enabled IPIS patches. The RFID chip allows automatic access control, presence logging, and digital identity verification without human intervention.

---

## 1. Overview

An IPIS patch is a fabric patch (embroidered or printed) with an embedded **passive UHF RFID transponder**. The chip stores a unique identifier (UID) and optionally the IPIS code itself. When the wearer presents the patch near a reader (e.g., at an airlock or base entrance), the reader identifies the person and logs the event.

**Key requirements:**
- Passive (no battery) – powered by the reader’s electromagnetic field.
- Read range: up to 1 metre (for convenient hand‑presenting).
- Durable: withstands vacuum, temperature extremes (-50°C to +80°C), radiation, and washing (if applicable).
- Flat and flexible – adds no more than 2 mm thickness to the patch.

---

## 2. RFID Standards

| Parameter | Specification |
|-----------|----------------|
| Frequency band | UHF 860–960 MHz (global, but preferably 865–868 MHz (EU) / 902–928 MHz (US)) |
| Protocol | ISO 18000‑6C (EPC Class 1 Gen 2) |
| Memory | Minimum 128 bits EPC (for unique ID) + 64 bits user memory (optional) |
| Read range | Up to 1 metre with a standard fixed reader (power dependent) |
| Write endurance | Minimum 100,000 cycles |
| Data retention | 10 years minimum |

---

## 3. Physical Integration into the Patch

The RFID chip and antenna are embedded between two fabric layers or within the patch’s backing.

**Construction:**

- **Top layer:** embroidered or printed design (monochrome: black/white/grey).
- **Middle layer (optional):** thin flexible plastic substrate with the RFID inlay.
- **Bottom layer:** fabric backing with Velcro loop (to attach to the suit) or adhesive.

**Antenna design:** printed silver or copper etched dipole. Size roughly 30×15 mm (fits inside a 40×40 mm patch). The antenna must be tuned for the fabric environment (dielectric constant of cloth).

**Thickness:** total patch thickness ≤ 3 mm, with the inlay ≤ 0.5 mm.

---

## 4. Data Encoding

Each patch stores at least:

- **Unique ID (UID)** – 64‑bit or 96‑bit read‑only serial number (factory‑programmed).
- **Optional:** The wearer’s IPIS code (e.g., `circle 03`) in user memory, but this can also be looked up from a central database by UID.

**Recommendation:** Store only the UID on the chip. The central registry maps UID to the person’s current IPIS code, stack, and access rights. This allows re‑issuing a patch without changing the chip and simplifies updates.

**Example EPC memory layout (128 bits):**
- Bits 0–95: UID (manufacturer assigned)
- Bits 96–127: checksum or version

---

## 5. Reader Requirements

- **Output power:** 0.5–2 W ERP (adjustable)
- **Antenna:** circular polarisation, gain ≤ 6 dBi
- **Mounting:** at entry points (airlocks, hatches, equipment lockers) at a height of 1–1.5 m, angled towards the wearer’s arm/chest.
- **Interface:** Wiegand, RS‑232, or Ethernet to the base access control system.

**Reading process:**
1. Wearer presents forearm (or chest) within 1 metre of the reader.
2. Reader detects the UID and sends it to the base computer.
3. Computer looks up the UID in the registry and checks access rights.
4. Door opens (or logs the attempt) and records time, location, and person ID.

---

## 6. Environmental Durability

| Condition | Requirement |
|-----------|-------------|
| Temperature | -50°C to +80°C (operational) |
| Humidity | 0–100% condensing (short term) |
| Vacuum | 10⁻⁶ Pa (space vacuum) – no outgassing |
| Radiation | Total ionising dose 50 krad (silicon) – use radiation‑hardened chip or shielding |
| Washing | Machine washable at 40°C (if patch is removable) |

**Recommendation:** For space suits, use chips rated for aerospace (e.g., Texas Instruments RF‑HDT series or NXP UCODE® 9 with extended temperature range). Encapsulate in epoxy or silicone for mechanical protection.

---

## 7. Two‑Layer Patch with RFID

The two‑layer mechanism (outer removable layer + inner hidden disc) can be combined with RFID:

- **Outer layer:** contains its own RFID chip with the current code (e.g., `circle 01`). When peeled off, the chip is deactivated (or the reader no longer recognises it because the outer layer is removed).
- **Inner disc:** optionally contains a separate RFID chip (or none – the inner disc is mainly a physical token). The digital stack record is independent.

**Simpler approach:** Only the outer layer has RFID. The inner disc is passive (no chip). Stack updates are done digitally via logbooks.

---

## 8. Example Manufacturing Steps

1. Print or embroider the patch design.
2. Place the RFID inlay between the top and backing layers.
3. Heat‑press or sew the layers together, leaving the antenna area free of metal threads.
4. Attach Velcro hook (or loop) to the back.
5. Test each patch with a reader to verify read range and UID.

---

## 9. Testing and Certification

- **Read range test:** at least 0.8 m in free air with a reference reader (2 W ERP).
- **Environmental test:** 10 cycles from -50°C to +80°C, then read test.
- **Flex test:** bend 1000 times around a 20 mm mandrel.
- **Radiation test:** for space‑grade chips, certify to NASA or ESA standards.

---

## 10. Cost Estimates (2026)

- RFID inlay (passive, UHF): $0.30–1.00 in volume (10k+).
- Patch manufacturing (embroidered with inlay): $2–5 per piece.
- Reader (fixed, industrial): $100–300 per unit.

For a pilot with 100 patches and 5 readers, total cost ~$1500–2500.

---

## 11. References

- ISO/IEC 18000‑6:2013 – Information technology — Radio frequency identification for item management.
- EPCglobal Tag Data Standard.
- NASA Technical Standard for RFID (NASA‑STD‑8739.4).

---

*This specification is part of IPIS / Duranki, version 15.0.*
