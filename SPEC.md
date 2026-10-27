# PCE Interface Specification — RFC v0.1 (draft)

> *What a PCE needs from the operating system*

> Status: draft for public comment · JadeAurum · Mirror Project · 2026-07
> Change requests: open a GitHub issue referencing the section number.

## 1. Purpose and Audience

This document specifies what a Personal Cognitive Exoskeleton (PCE)
requires from an operating system, so that:
- **OS vendors** know which four interface classes unlock user-owned AI;
- **Agent developers** can target one interface surface across platforms;
- **Community porters** can bring PCE to platforms we don't build for.

We define the interfaces. The community fills the platforms.

## 2. The Four Interface Classes

A PCE needs exactly four things from the OS. Nothing more.

### 2.1 Screen Semantic Access
Read what is on screen as *structure*, not pixels: view trees,
accessibility nodes, text content, actionable elements. Required for
"understand what the user is looking at." On Android this exists today
via the AccessibilityService API.

### 2.2 Action Injection
Perform user-intent actions: tap, swipe, type, launch an app.
Must be user-initiated and user-visible — a PCE acts *for* the user,
never behind the user's back.

### 2.3 Local Model Runtime
Permission to run inference on-device without throttling or store-policy
penalties: CPU/GPU/NPU access, memory headroom, background execution
for scheduled tasks (e.g. a nightly memory pass).

### 2.4 Memory Storage Isolation
An app-private, encryptable storage area for long-term memory that no
other app — and no cloud sync the user didn't ask for — can read.
The user's memory must be exportable by the user (device migration is a
right, not a feature).

## 3. Reference Topologies

**Unified form**: brain + window on one device.
```
[ User device: local model ⇄ PCE core ⇄ screen access / actions ]
```
**Window form**: brain on another user-owned device; phone as window.
```
[ Old PC: local model + PCE core ] ⇄ LAN/private link ⇄ [ Phone: window ]
```
Both forms keep all data on user-owned hardware. A topology where the
"brain" is a vendor cloud is *not* a PCE (fails criteria 1, 2, 4).

## 4. Southbound and Northbound Surfaces

**Southbound — server mode**: a PCE exposes an OpenAI-compatible HTTP
API on the user's own network, so any existing chat client can use the
PCE as its brain. Endpoint shapes follow the de-facto
`/v1/chat/completions` convention; details in the reference implementation.

**Northbound — MCP client**: a PCE consumes the user's tools and
services as an MCP (Model Context Protocol) client, and treats vendor
agents (via A2A/MCP) as *resources it can call on the user's behalf* —
not as competitors. This is "strengthen everything, replace nothing"
made concrete.

## 5. Platform Adaptation Matrix

| Platform | Form | Status |
|---|---|---|
| Android | Unified | ✅ Mirror-Origin reference implementation |
| iOS | Window (existing clients → PCE server mode) | ✅ Path proven by community clients; first adapter = bounty issue |
| HarmonyOS | Pending third-party access to the intent framework | ⏳ Watchpost — we adapt the day it opens |
| Linux desktop / old PCs | Unified, or as the brain in window form | 🤝 Reserved chapter — community implementation invited |
| Vendor agent phones | Callable resources via A2A/MCP | 🤝 Posture statement |

## 6. Device Tier Guidance

| Tier | Hardware | Local brain class |
|---|---|---|
| Entry | 12GB RAM, older flagship SoC (e.g. Galaxy Z Fold 3) | ~4B models |
| Standard | 16GB recent flagship | 8–9B models |
| Full | 24GB top-tier | larger multi-model setups |

The entry tier is the point of the sixth criterion: a phone you already
own, possibly retired, is enough to own an AI. Community benchmark
reports on more devices are a standing bounty issue.

## 7. RFC Process

- Comment: open an issue titled `[RFC] §<section> <topic>`.
- Response cadence: daily in the first two weeks after each release,
  weekly batches thereafter.
- Changes land as PRs to this file; merge authority: JadeAurum.
- Substantial contributions require signing the CLA (see CONTRIBUTING).

---
*JadeAurum · Mirror Project — RFC v0.1 draft, 2026-07*
