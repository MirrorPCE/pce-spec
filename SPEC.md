# PCE Interface Specification — RFC v0.1 (draft)

> *What a PCE needs from the operating system*

> Status: draft for public comment · Mirror Project · mirrorpce.com · 2026-07
> Change requests: open a GitHub issue referencing the section number.

## 1. Purpose and Audience

This document specifies what a Personal Cognitive Exoskeleton (PCE)
requires from an operating system.

This document describes what a personal AI needs from the phone, so that anyone can comment on it.

## 2. The Four Interface Classes

A PCE needs exactly four things from the OS. Nothing more.

### 2.1 Screen Semantic Access
Optional, only with the user's consent: while doing something the user
asked for, the app may look at the current screen; off by default;
nothing is kept.

### 2.2 Action Injection
Acts only from a fixed list, on the user's request; money, sending and
deleting stop at the last step for the user to press.
Must be user-initiated and user-visible — a PCE acts *for* the user,
never behind the user's back.

### 2.3 Local Model Runtime
Permission to run a small model on the device.

### 2.4 Memory Storage Isolation
Memory stays on the user's own device, can be exported and restored;
cloud backup is off.
The user's memory must be exportable by the user (device migration is a
right, not a feature).

## 3. Form

Android phone.

## 4. External Tools

A PCE connects to external tools the user adds one by one; every call
needs the user's OK.

## 5. Platform

| Platform | Status |
|---|---|
| Android | In development |

## 6. Device Requirements

Android 12 or newer, a phone you already own.

## 7. RFC Process

- Comment: open an issue titled `[RFC] §<section> <topic>`.
- Changes land as PRs to this file; merge authority: Mirror Project.
- Substantial contributions require signing the CLA (see CONTRIBUTING).

---
*Mirror Project · mirrorpce.com — RFC v0.1 draft, 2026-07*
