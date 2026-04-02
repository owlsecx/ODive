# 🦈 ODive

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux%20%2F%20Windows-informational?style=flat-square&logo=linux&logoColor=white&color=0a0c10"/>
  <img src="https://img.shields.io/badge/Category-OWeb%20%2F%20Server-Side%20Injection-cyan?style=flat-square"/>
  <img src="https://img.shields.io/badge/Dependencies-None%20(Standalone)-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-v1.0-cyan?style=flat-square"/>
</p>

> **ODive** is a powerful LFI / RFI / Path Traversal Scanner with built-in path library, multiple traversal encodings (7 variants), expanded PHP wrappers, log poisoning module, confidence scoring, and support for GET/POST/Cookie injection. Built as a standalone executable.

---

## 📌 Overview

ODive performs deep server-side file inclusion and path traversal testing against web applications. It supports full LFI scanning with advanced payload generation, RFI detection, log poisoning for potential RCE, quick probes, and a complete path browser. Results include real-time colored findings with severity and confidence levels. All reports are automatically saved to `odive_reports/`.

---

## 🖥️ Modules

| # | Module              | Description |
|---|---------------------|-------------|
| **[1]** | **Full LFI Scan**       | Complete multi-threaded scan with all paths, encodings, and PHP wrappers |
| **[2]** | **RFI Probe**           | Tests for Remote File Inclusion using metadata endpoints and reflection checks |
| **[3]** | **Log Poisoning**       | Injects PHP payload via headers then attempts to read logs via LFI |
| **[4]** | **Quick File Probe**    | Fast test for a single file path with content preview |
| **[5]** | **Path Browser**        | Browse and export the full built-in path library and PHP wrappers |

---

## 📊 Key Features

### Traversal Payload Generation
- **7 Encoding Variants** per depth (up to 12 levels):
  - Plain (`../`)
  - URL-encoded (`%2F`)
  - Double-encoded (`%2e%2e%2f`)
  - Null-byte (`%00`)
  - Dot-dot bypass (`....//`)
  - Windows backslash + `%5C`
  - Slash-encoded (`..%2F`)

### PHP Wrappers (14+)
- `php://filter/convert.base64-encode/resource=`
- `php://input`
- `data://text/plain;base64,...`
- `expect://id`
- `phar://` and `zip://`
- And many more

### Detection Engine
- **HIGH** confidence: Exact keyword match (`root:x:`, `DB_PASSWORD`, etc.)
- **MEDIUM** confidence: Base64 blobs or significant response size anomaly
- **LOW** confidence: Generic file signatures (`<?php`, `#!/bin/`)

### Injection Methods
- GET parameter
- POST body
- Cookie injection

---

## 🔍 Built-in Path Library

**Total Paths**: 60+ categorized paths covering:
- Linux system & configuration files
- Windows system files and logs
- Popular web frameworks configs (WordPress, Laravel, Joomla, Django...)
- Generic secrets (`.env`, `.git/config`, SSH keys, etc.)

---

## 📁 Output & Reporting

All outputs saved automatically to `odive_reports/` folder:

| File Type | Pattern                            | Description |
|-----------|------------------------------------|-----------|
| TXT       | `odive_report_YYYYMMDD_HHMMSS.txt` | Detailed report with findings and previews |
| JSON      | `odive_report_YYYYMMDD_HHMMSS.json`| Structured machine-readable report |

---

## ⚙️ Requirements

- **Linux or Windows**
- **No Python installation needed** — runs as a standalone executable
- **No external dependencies** — everything bundled via PyInstaller

---

## 🚀 Usage

```bash
./ODive


📦 Part of OwlSec Toolkit
This tool is part of the OwlSec suite — a collection of 300+ security and privacy tools.
🔗 owlsec.org

©️ License
Proprietary — © Khaled S. Haddad
Tools are distributed as pre-built executables. Source code is proprietary.

AUTHORISED SECURITY TESTING USE ONLY
