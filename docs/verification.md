# Stack Verification – How IPIS Records Are Trusted

The Snezhkov Stack is not just a set of physical discs – it must be backed by verifiable records. This document explains how IPIS ensures that a person’s stack reflects real work history.

---

## 1. Principle

No central authority issues stacks. Instead, **each stack entry is derived from digitally signed logbook entries** from recognised spacecraft or bases.

Trust flows from:
- **Logbook integrity** – entries are signed by the commander or authorised officer.
- **Immutable audit trail** – logbooks are hashed and stored (centralised registry or distributed, but not blockchain by default).
- **Physical disc as a token** – the disc itself is a souvenir; the truth is in the digital record.

---

## 2. What Generates a Stack Entry

A stack entry (a world disc or an `E` disc) is created when a person **leaves** a base or ship after a qualifying stay (>6 months) or after performing an EVA.

The following events trigger a digital record:

| Event | Required Logbook Entry | Stack Addition |
|-------|------------------------|----------------|
| Arrival at base | Arrival time, person’s ID, commander’s signature | None (only starts the stay) |
| Departure from base | Departure time, confirmation of stay duration | World disc (e.g. `02’`) |
| Performance of an EVA | EVA log: date, duration, participants, commander’s signature | `E` disc (added after the world disc) |
| Transfer between vessels | Handover record signed by both commanders | World disc of the vessel’s home base (if applicable) |

All entries are stored in the **base/ship logbook** – an electronic document with digital signatures.

---

## 3. Digital Stack Registry

A **centralised registry** (operated by a trusted body, e.g. an international space agency consortium) stores:

- Person’s unique ID (e.g. UUID or astronaut number)
- Current stack (list of world codes and `E` flags)
- References to logbook entries that prove each stack element

The registry is **append‑only** – old entries cannot be deleted or altered. New entries are added only when a new logbook excerpt is submitted and verified.

Verification process:
1. Person (or their commander) submits a digitally signed logbook excerpt.
2. The registry checks the signature against known public keys of authorised signers (e.g., NASA, ESA, SpaceX, Roscosmos).
3. If valid, the stack is updated and a new hash is recorded.

The registry does **not** store the full logbook – only the hash and the reference.

---

## 4. Physical Patch vs. Digital Record

The physical discs on your suit are **symbolic** and **optional**. The official stack is the digital one.

- You can wear any discs you like – but if you lose them, you can re‑order new ones based on your digital record.
- When you earn a new disc, the registry issues a **verifiable credential** (a QR code or NFC tag) that you can use to prove your stack to any base.
- The two‑layer patch mechanism (inner disc hidden under outer) ensures that you physically receive a disc only when you actually leave a base – but that disc is still just a token. The digital registry is the source of truth.

---

## 5. What About Long‑Term Storage and Backups?

Logbooks are stored by each operator (NASA, SpaceX, etc.). The registry stores only references and hashes.

For redundancy, the registry can be mirrored across multiple locations. In the future, a distributed ledger (blockchain) could be added, but the current design uses **centralised + cryptographic signatures** for simplicity and legal acceptance.

---

## 6. Example: Proving Your Stack for a New Job

You arrive at a lunar base and claim to have worked on Mars with EVAs. The base administrator:

1. Asks for your digital ID (e.g., a signed token from the registry).
2. Queries the registry API – it returns your stack: `01` `02’` `E` `03`.
3. Checks the cryptographic proof linking each stack element to a specific logbook entry (commander’s signature, date, mission ID).
4. Accepts your stack as valid.

No need to trust your word or your physical patches.

---

## 7. Privacy Considerations

- The registry stores **only work history**, not personal data (birth date, medical records, etc.).
- Access to the registry can be restricted (e.g., read‑only for most users, write access only for authorised commanders).
- Individuals can request a **read‑only export** of their own stack to show to third parties.

---

## 8. Future Enhancements

- **Self‑sovereign identity** – let individuals hold their own verifiable credentials without a central registry.
- **Blockchain anchoring** – publish registry hashes to a public blockchain for extra immutability.
- **Automated EVA logging** – suit sensors automatically sign an EVA record when the airlock cycles.

These are not required for initial deployment.

---

*This verification model is part of IPIS / Duranki, version 15.0.*
