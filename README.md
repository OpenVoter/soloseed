
# **SoloSeed**


**Carry Your Identity on a Hardware Protected Authenticator**


---

## Overview

**SoloSeed** is the next evolution of the SoloKey hardware token family, designed to provide:

- **FIDO2/WebAuthn-compatible authentication** for websites, devices, and services
- 
- **Deterministic, recoverable identities** stored as a human-memorizable seed (12–24 words, BIP39-style)
- 
- **Hardware-backed security** for daily use, while enabling full personal sovereignty over identity  

SoloSeed builds directly on the open-source SoloKeys platform:

- [SoloKeys GitHub – Solo1](https://github.com/solokeys/solo1) – the official SoloKey firmware and hardware reference  
- [SoloKeys EU Website](https://solokeys.eu/?lang=en) – European SoloKey official site  
- [Somu on Crowd Supply](https://www.crowdsupply.com/solokeys/somu) – Hacker/prototyping hardware for experimentation  

By extending the SoloKey ecosystem, SoloSeed introduces a new paradigm: devices where your identity can live in your head, while keys remain hardware-protected during regular authentication.

---

## Philosophy

In the digital age, identity is fragmented across services, devices, and accounts. Traditional authentication relies on:

- Passwords, often reused across platforms  
- Vendor-managed keys, with no user portability  
- Hardware tokens whose value is lost if the device is damaged or stolen  

SoloSeed changes this model. Inspired by Bitcoin wallets:

- **A 12-word seed is the root of your identity**  
- Memorized seed phrases allow full recovery of keys  
- Hardware devices enforce day-to-day security for authentication  
- Users retain true self-sovereignty, independent of vendors or infrastructure  

The system separates identity recovery from daily authentication:

- Hardware protects active keys  
- Memorized seed enables regeneration on a new device  
- Users can carry the essence of their identity in their minds

---

## Technology

SoloSeed v0.2 introduces a deterministic key derivation model based on a 12-word seed plus passphrase, enabling secure recovery and controlled duplication.

### Key Features

- **Seed Generation / Import**  
  - Device can generate a new 12-word mnemonic or accept a user-provided seed.
  -  
- **Passphrase (13th Word)**  
  - Adds additional entropy to prevent unauthorized duplication.  
  - Required along with the mnemonic to reproduce identity on new hardware.
  - 
- **Deterministic Key Derivation**
- 
  ```text
  master_secret = HKDF(seed || passphrase, salt=device_uid)
  fido_root_key = HMAC(master_secret, "FIDO2_ROOT")
  ```

master_secret → root for all FIDO2 per-site keys

device_uid → binds keys to hardware, preventing unnoticed cloning

fido_root_key → used to generate per-site FIDO2 keys

# Hardware Enforcement

Keys are stored in secure hardware flash

No private keys leave the device after secure lock



# Lifecycle

1. Provisioning / Hacker Mode

Device flashed with open-source firmware

Seed generated/imported

Optional passphrase entered

One-time export of seed (and optional passphrase)



2. Secure Lock / Solo Mode

Firmware locked, debug interfaces disabled

Keys stored securely and non-extractable

Device fully FIDO2/WebAuthn compatible



3. Daily Use

Hardware signs authentication requests

Keys never leave the device



4. Recovery

Identity can be regenerated on new hardware using seed + passphrase





---

# Security

SoloSeed v0.2 combines hardware-backed security with user-controlled deterministic identity.

# Threat	Mitigation

Malware on host	Keys never leave hardware
Phishing	FIDO2/WebAuthn standard protections apply
Factory or supply-chain compromise	Open-source firmware, public flashing ceremonies
Device loss	Recoverable using seed + passphrase
Unauthorized duplication	Requires both seed and passphrase
Accidental re-flashing	One-time export/import flags


# Residual Risks

Seed + passphrase compromise → attacker can clone identity

Coerced passphrase entry → human-dependent

Active malware during provisioning → mitigated by public flashing and auditability

Physical side-channel attacks → depends on MCU hardware


Identity Duplication and Recovery

Legitimate duplication is possible only if both seed and passphrase are known

Supports backup devices, geographic redundancy, and travel use

Hardware flags prevent repeated exports or stealth duplication



---

# SoloSeed in the SoloKeys Ecosystem

Product	Purpose

SoloKey / Solo	Standard FIDO2 authentication hardware token
SoloSeed	Seed-backed, passphrase-hardened, recoverable SoloKey — self-sovereign identity


SoloSeed extends the SoloKeys family while maintaining:

Full FIDO2/WebAuthn compatibility

Open-source transparency

Hardware-backed trust

Human-portable recovery roots



---

# Getting Started

> Note: SoloSeed v0.2 is currently a conceptual fork of SoloKey firmware. The repository provides high-level design, framework, and documentation for implementation and security auditing.



# Repository Contents (to be updated)

docs/ — design philosophy, technical and security overviews

firmware/ — SoloSeed firmware fork (work in progress)

examples/ — host software examples for seed export/import, passphrase handling, and key derivation




---

License

MIT License — see LICENSE
