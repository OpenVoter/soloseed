# SoloSeed


# Carry Your Identity on a Hardware-Protected Authenticator


# Overview

SoloSeed is the next evolution of the SoloKey hardware token family, designed to provide:

FIDO2/WebAuthn-compatible authentication for websites, devices, and services

Deterministic, recoverable identities stored as a human-memorizable seed (12–24 words, BIP39-style)

Hardware-backed security for daily use, while enabling full personal sovereignty over identity


SoloSeed builds directly on the open-source SoloKeys platform:

[SoloKeys GitHub – Solo1](https://github.com/solokeys/solo1)

[SoloKeys EU Website](https://solokeys.eu/?lang=en)

[Somu on Crowd Supply](https://www.crowdsupply.com/solokeys/somu)


By extending the SoloKey ecosystem, SoloSeed introduces a new paradigm: devices where your identity can live in your head, while keys remain hardware-protected during regular authentication.

---

# Philosophy

In the digital age, identity is fragmented across services, devices, and accounts. Traditional authentication relies on:

Passwords, often reused across platforms

Vendor-managed keys, with no user portability

Hardware tokens whose value is lost if the device is damaged or stolen


SoloSeed changes this model. Inspired by Bitcoin wallets:

A 12-word seed is the root of your identity

Memorized seed phrases allow full recovery of keys

Hardware devices enforce day-to-day security for authentication

Users retain true self-sovereignty, independent of vendors or infrastructure


The system separates identity recovery from daily authentication:

Hardware protects active keys

Memorized seed enables regeneration on a new device

Users can carry the essence of their identity in their minds



---

# Security Model

SoloSeed combines hardware security with seed-based recoverability, using a two-phase lifecycle:

Phase 1: Provisioning / Hacker Mode

Reprogrammable firmware allows:

New seed generation

One-time seed export

Seed import for recovery from existing backups


Public, auditable firmware ensures transparency

Optional PIN or physical presence confirmation enforces intentional actions


Phase 2: Secure / Solo Mode

Irreversible hardware hardening:

Firmware locked

Debug interfaces disabled

Private keys non-extractable

One-time seed export/import permanently disabled


Fully FIDO2/WebAuthn compatible

Imported or generated keys persist in hardware


Security trade-off:

Identity is now recoverable via memorized seed

Anyone with the seed can clone your identity

Hardware guarantees still protect keys during active use



---

# SoloSeed in the SoloKeys Ecosystem

Product	Purpose

SoloKey / Solo	Standard FIDO2 authentication hardware token
SoloSeed	Seed-backed, recoverable, hardened SoloKey — self-sovereign identity


SoloSeed extends the SoloKeys family by:

Maintaining full FIDO2/WebAuthn compatibility

Introducing deterministic key derivation from user-memorizable seeds

Preserving the core values of transparency, security, and hardware-backed trust



---

# Getting Started

> Note: SoloSeed is currently a conceptual fork of the SoloKey firmware. The current repo provides a high-level framework and documentation for implementation and security auditing.



# Repository Contents

docs/ — design philosophy, security model, lifecycle diagrams

firmware/ — SoloSeed firmware fork (work in progress)

examples/ — host-side examples for seed export/import and deterministic key derivation


#Reference Projects

SoloKeys Firmware

Somu Crowdsupply



---

# Lifecycle Overview

1. Provisioning

Device flashed with SoloSeed firmware

Seed generated or imported

One-time seed export occurs



2. Recovery / Export

User memorizes or engraves seed

Device export/import flags are set



3. Secure Lock

Device transitions to hardware-enforced Solo mode

Keys remain fully protected, FIDO2 compatible



4. Daily Use

Authentication with websites, OS, and devices

Keys never leave hardware



5. Recovery

Seed allows identity restoration on new devices





---

# Contributing

SoloSeed is fully open-source. Contributions are welcome:

Review or audit the firmware design

Test deterministic key derivation or recovery workflows

Improve documentation or lifecycle diagrams


Please follow standard GitHub workflows for pull requests and issues.


---

License

MIT License — see LICENSE


---

# Summary

SoloSeed enables a new class of hardware authentication token:

Hardware-backed, FIDO2-compliant keys for everyday use

Deterministic, seed-based recovery for lost or destroyed devices

True self-sovereign identity that can be carried in your head


SoloSeed builds on the SoloKeys legacy, extending the range of products while adhering to their core principles: transparency, security, and personal control.

