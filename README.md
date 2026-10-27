# PCE Interface Specification

> *What a PCE needs from the operating system*

> **RFC v0.1 (draft)** — Request for Comments. Issues welcome.
> JadeAurum · Mirror Project · [mirrorpce.com](https://mirrorpce.com)

## What is a PCE?

**PCE — Personal Cognitive Exoskeleton**: an AI that belongs to you.
It thinks locally, remembers you long-term, protects your privacy at the
architecture level (not the promise level), works across ecosystems,
and runs on hardware you already own.

**Positioning**: We are not an OS. We are not another agent platform.
A PCE does not compete with the OS, with agents, or with the cloud —
it stands beside the user. Whatever you want to use, the PCE uses it
for you. **Strengthen everything, replace nothing.**
The only test: *sovereignty and memory belong to the user.*

## The Six Criteria

A system qualifies as a PCE only if it meets all six:

| # | Criterion | Meaning |
|---|-----------|---------|
| 1 | User-owned | The agent is yours; it exists without any vendor account |
| 2 | Thinks locally | Core reasoning runs on the user's own device |
| 3 | Long-term memory | It remembers you across days, months, years |
| 4 | Architecture-level privacy | Enforced by design, not by promise |
| 5 | Cross-ecosystem neutral | Not locked to any vendor's ecosystem |
| 6 | Runs on hardware you already own | No new phone required |

## Two Legitimate Forms

- **Unified form** — brain and window on the same user device (Android phone).
- **Window form** — the brain lives on another device *you own* (e.g. a
  retired PC brought back to life); your phone or iPhone is the window.
  Data never leaves your own hardware, so the criteria still hold.

## What this repository is

This spec defines **what a PCE needs from an operating system** — four
interface classes (screen semantic access, action injection, local model
runtime, memory storage isolation) — plus reference topologies, the
southbound/northbound API posture, a platform adaptation matrix, and
device-tier guidance. See [SPEC.md](SPEC.md).

It is published as an open RFC: we define the interfaces, the community
fills the platforms. Open an issue to comment on any section.

## Mirror-Origin (codename *Kawagebo*)

A reference implementation — **Mirror-Origin / 镜-始** — a runnable,
open-source teaching PCE for Android.
*Kawagebo* is the sacred peak of the Meili range that no one may summit;
we borrow the name in tribute — a guardian that exists
**only to carry you across into the AI era**（只为渡你入AI新时代）.

## License

Specification text: see [LICENSE.md](LICENSE.md).
Reference implementation: AGPL-3.0, with a separate commercial license
available.

---
*JadeAurum · Mirror Project · 2026*
