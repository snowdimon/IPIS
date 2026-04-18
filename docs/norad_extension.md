# NORAD Extension – Adding IPIS_CODE to Space‑Track.org

This document proposes an optional field `IPIS_CODE` in the standard NORAD Two‑Line Element (TLE) and satellite catalog entries. The goal is to make objects in space instantly recognisable to human operators and automated systems.

---

## 1. Problem

Today, objects in the NORAD catalog are identified by a 5‑digit number (NORAD ID) and a name (e.g., “ISS (ZARYA)”). While precise, these identifiers are not **semantic** – they don’t tell you whether the object is a crewed station, a robotic lander, or a debris piece. Dispatchers must look up additional information.

IPIS provides a human‑readable, standardised code that can be attached to any object.

---

## 2. Proposed Field

Add an optional `IPIS_CODE` field to the Space‑Track.org JSON and XML responses for each object.

Example JSON snippet:

```json
{
  "NORAD_ID": 25544,
  "OBJECT_NAME": "ISS (ZARYA)",
  "IPIS_CODE": "circle 02’",
  "ORBIT_TYPE": "LEO",
  "COUNTRY": "USA/RUSSIA/ESA/JAPAN/CANADA"
}
