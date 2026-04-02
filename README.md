# 🦈 ODive

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux%20%2F%20Windows-informational?style=flat-square&logo=linux&logoColor=white&color=0a0c10"/>
  <img src="https://img.shields.io/badge/Category-OWeb%20%2F%20Server-Side%20Injection-cyan?style=flat-square"/>
  <img src="https://img.shields.io/badge/Dependencies-requests-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-v1.0-cyan?style=flat-square"/>
</p>

> **ODive** is a powerful LFI / RFI / Path Traversal Scanner with built-in path library, multiple traversal encodings, PHP wrappers, log poisoning, confidence-based detection, and support for GET/POST/Cookie injection. Features real-time findings, progress tracking, and detailed TXT + JSON reporting.

---

## 📌 Overview

ODive performs deep server-side file inclusion and path traversal testing against web applications. It supports inline URL scanning, multiple injection methods, advanced payload generation (7 encodings + PHP wrappers), confidence scoring, and specialized modules for RFI and log poisoning. All findings are color-coded with severity and confidence levels and saved automatically to `odive_reports/`.

---

## 🖥️ Modules

| # | Module              | Description |
|---|---------------------|-------------|
| **[1]** | **Full LFI Scan**       | Complete scan with all paths, encodings, wrappers, and multi-threading |
| **[2]** | **RFI Probe**           | Tests for Remote File Inclusion using metadata endpoints and reflection |
| **[3]** | **Log Poisoning**       | Injects PHP payload via headers then reads logs via LFI (potential RCE) |
| **[4]** | **Quick File Probe**    | Fast test for a single file path with content preview |
| **[5]** | **Path Browser**        | Browse and export the full built-in path library + PHP wrappers |

---

## 📊 Key Features

### Traversal Payloads
- **7 Encoding Variants** per depth (up to 12 levels):
  - Plain (`../`)
  - URL-encoded (`%2F`)
  - Double-encoded (`%2e%2e%2f`)
  - Null-byte (`%00`)
  - Dot-dot bypass (`....//`)
  - Windows backslash + `%5C`
  - Slash-encoded (`..%2F`)

### PHP Wrappers Support
- 14+ wrappers including:
  - `php://filter/convert.base64-encode`
  - `php://input`
  - `data://`
  - `expect://`
  - `phar://` and `zip://`

### Detection & Scoring
- **High Confidence**: Exact keyword match (e.g. `root:x:`, `DB_PASSWORD`)
- **Medium Confidence**: Base64 blobs or significant size increase
- **Low Confidence**: Generic markers (`<?php`, `#!/bin/`)

### Injection Methods
- GET parameter
- POST body
- Cookie injection

---

## 🔍 Built-in Path Library

**Total Paths**: 60+  
**Categories**:
- Linux system files (`/etc/passwd`, `/proc/self/environ`, logs, SSH keys…)
- Windows system files (`win.ini`, SAM, IIS config…)
- Web framework configs (WordPress, Laravel, Joomla, Django…)
- Generic secrets (`.env`, `.git/config`, `.htpasswd`…)

---

## 📁 Output & Reporting

All reports saved to `odive_reports/`:

| Format | File Name Pattern                  | Content |
|--------|------------------------------------|--------|
| TXT    | `odive_report_YYYYMMDD_HHMMSS.txt` | Full colored-style report with previews |
| JSON   | `odive_report_YYYYMMDD_HHMMSS.json`| Structured data (tool info + findings) |

**Finding Fields**: timestamp, URL, method, param, payload, path, keyword, severity, confidence, snippet.

---

## ⚙️ Requirements

- Python 3
- `pip install requests`
- Authorized security testing use only

---

## 🚀 Usage

```bash
./ODive.py
