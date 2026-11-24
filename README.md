# 🦉 ODive

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OWeb-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-2.0-cyan?style=flat-square"/>
</p>

> **ODive** — LFI / RFI / Path Traversal Scanner

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

ODive detects Local/Remote File Inclusion and path traversal issues on authorised web targets. It ships built-in paths, PHP wrapper coverage, encoding variants, multi-parameter scanning, and confidence scoring, plus an offline sandbox self-test that needs no network. Designed for defensive application security testing.

---

## ✨ Features

- Full LFI scan, quick single-path probe, and optional RFI module
- Multi-parameter auto-scan across query inputs
- Encoding and PHP wrapper coverage with OS profile controls
- Offline --sandbox self-test with no network required
- Confidence scoring and optional cloud-metadata RFI probes (opt-in)
- TXT reporting with thread, delay, and timeout tuning

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./ODive --url 'https://app.example/view' --param page --scan
./ODive --url 'https://app.example/view?page=1' --quick
./ODive --sandbox --os linux
./ODive --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 275+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

Proprietary — © 2026 Owlsec LLC. All rights reserved.

*Tools are distributed as pre-built executables. Source code is proprietary.*

---

## 🔍 Verification & Transparency

This tool is closed-source. These files let you see exactly what is inside it,
without the source:

- [`SBOM.cdx.json`](SBOM.cdx.json) — CycloneDX inventory: SHA-256 of this
  binary, bundled CPython version, and every bundled library with its exact
  version and license. Feed it to Grype, Trivy or Dependency-Track to audit
  our dependencies for CVEs yourself.
- [`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md) — the full license text
  of every third-party component, extracted from this binary.

**No telemetry, no analytics, no licence check-in.** This tool does not phone
home. Verify that claim yourself:

```bash
sudo strace -f -e trace=network ./ODive --help   # watch every network call
firejail --net=none ./ODive --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
