# 🦉 OCronAudit

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OForensics-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OCronAudit** — Scheduled-Task & Persistence Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

Linux scheduled-task & persistence auditor (cron, at, systemd timers, rc, udev, ld.so.preload)

---

## ✨ Features

- Live-system or offline (--root DIR) collection of every Linux scheduled-execution / persistence point
- Crontab parser — /etc/crontab, cron.d, cron.{hourly, daily,weekly,monthly}, /var/spool/cron, anacrontab, @reboot / @daily macros, field validation, next-run
- at / batch spool decoder (atjobs, /var/spool/at)
- systemd unit parser — .timer / .service, OnCalendar, OnBootSec, OnUnitActiveSec, ExecStart*, User=, PATH, drop-ins, enablement via *.wants symlinks, user units
- rc.local, init.d, rc?.d, profile / profile.d, shell rc autoload hooks (bashrc, zshrc, .profile ...)
- udev RUN+= / PROGRAM= extraction, XDG autostart, /etc/ld.so.preload + ld.so.conf.d review
- Command resolver — wrappers, sh -c, interpreters, PATH lookup inside the audited root, file metadata
- 40+ rule engine: pipe-to-shell, encoded payloads, reverse shells, /tmp & /dev/shm exec, hidden paths, writable root targets, PATH hijack, masquerading, miners, anti-forensics, recently modified units ...
- MITRE ATT&CK mapping (T1053.x, T1543.002, T1037.004, T1546.x, T1574.006, T1547.013) + remediation advice
- mtime timeline, severity filter, CI gate (--fail-on)
- Export TXT / Markdown / JSON / CSV / SARIF 2.1.0
- Self-test (--demo) with synthetic malicious tree
- Strictly read-only: never modifies or disables jobs

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OCronAudit
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
