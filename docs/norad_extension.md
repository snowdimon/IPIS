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

For a robotic Mars lander:
{
  "NORAD_ID": 12345,
  "OBJECT_NAME": "MARS ROVER X",
  "IPIS_CODE": "hex 03",
  "ORBIT_TYPE": "SURFACE"
}

For a deep‑space probe:
{
  "NORAD_ID": 98765,
  "OBJECT_NAME": "VOYAGER 1",
  "IPIS_CODE": "circle 00"
}
```
---

## 3. Automatic Assignment Rules

When an object is first catalogued, the system can **suggest** an `IPIS_CODE` based on its orbit and function:

| Object type | Suggested IPIS_CODE |
|-------------|----------------------|
| Crewed station in LEO | `circle 01'` |
| Uncrewed cargo ship in LEO | `hex 01'` |
| Satellite in GEO | `circle 01'` (or `hex 01'` if uncrewed) |
| Lunar orbiter | `circle 02'` (or `hex 02'`) |
| Lunar surface lander | `hex 02` |
| Mars orbiter | `circle 03'` (or `hex 03'`) |
| Mars rover | `hex 03` |
| Interplanetary probe beyond Mars | `circle 00` (or `hex 00`) |

The operator can **override** the suggestion (e.g., a crewed Mars ship would be `circle 00` while in transit, then change to `circle 03` after landing).

## 4. Updating IPIS_CODE

The code can change over time (e.g., a ship in transit from Earth to Mars: circle 00 → circle 03 after landing). Operators should submit updates via the standard Space‑Track.org update interface.

Changes are logged, preserving the history.

## 5. Benefits

    Instant situational awareness – a dispatcher sees circle 02’ and knows it’s a crewed lunar orbital object.

    Better filtering – search for all hex 03 objects (Mars robots).

    Interoperability – any system that reads NORAD data can display the IPIS code without additional databases.

    Public engagement – amateur observers can easily identify objects by type and location.

## 6. Implementation Path

    Pilot with a few objects – e.g., ISS (circle 01’), Tiangong (circle 01’), Mars rovers (hex 03).

    Add field to API – Space‑Track.org team can add IPIS_CODE as an optional JSON field without breaking existing clients.

    Encourage operators to start populating the field for new launches.

    Over time become a de facto standard.

The field is optional – objects without it will still be tracked as before.

## 7. Relation to RFID and Patches

    The IPIS_CODE in NORAD is for objects (spacecraft, stations).

    The RFID patch is for people (and optionally for uncrewed objects if they carry a tag).

    Both use the same coding syntax (circle, hex, numbers, indices).

## 8. Example API Query

Request:
GET https://www.space-track.org/basicspacedata/query/class/gp/NORAD_ID/25544/format/json

Response (with IPIS_CODE added):
json

[{
  "NORAD_ID": "25544",
  "OBJECT_NAME": "ISS (ZARYA)",
  "IPIS_CODE": "circle 01’",
  "EPOCH": "2025-01-01T12:00:00",
  ...
}]

## 9. Next Steps

    Submit a formal proposal to the Space‑Track.org maintainers (U.S. Space Command / Space-Track.org team).

    Provide a reference implementation for validating IPIS_CODE syntax.

    Offer to help with pilot integration.

*This extension is part of IPIS / Duranki, version 15.0.*
