# 🦉 OCronAudit

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OForensics-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OCronAudit** — Scheduled-Task & Persistence Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

OCronAudit — Scheduled-Task & Persistence Auditor. It provides live-system or offline (--root DIR) collection of every Linux scheduled-execution / persistence point. Built-in demo/self-test paths and severity gates help validate detections without touching production when those flags are used.

---

## ✨ Features

- Live-system or offline (--root DIR) collection of every Linux scheduled-execution / persistence point
- Crontab parser — /etc/crontab, cron.d, cron.{hourly, daily,weekly,monthly}, /var/spool/cron, anacrontab, @reboot / @daily macros, field validation, next-run
- at / batch spool decoder (atjobs, /var/spool/at)
- systemd unit parser — .timer / .service, OnCalendar, OnBootSec, OnUnitActiveSec, ExecStart*, User=, PATH, drop-ins, enablement via *.wants symlinks, user units
- rc.local, init.d, rc?.d, profile / profile.d, shell rc autoload hooks (bashrc, zshrc, .profile ...)
- udev RUN+= / PROGRAM= extraction, XDG autostart, /etc/ld.so.preload + ld.so.conf.d review

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OCronAudit                                     # interactive menu
./OCronAudit --scan -r /path/to/root
./OCronAudit --demo
./OCronAudit --help
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
sudo strace -f -e trace=network ./OCronAudit --help   # watch every network call
firejail --net=none ./OCronAudit --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
