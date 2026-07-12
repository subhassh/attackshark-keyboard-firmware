# attackshark-keyboard-firmware
This repository archives firmware for an Attack Shark Hall Effect keyboard using firmware device ID 2268.  The purpose is to help users recover keyboards that become stuck in bootloader mode because the official updater cannot retrieve firmware from the vendor's backend.

# Attack Shark X65HE Firmware Archive (Device ID 2268)

> Community archive of the official firmware for the **Attack Shark X65HE** Hall Effect keyboard (Firmware Device ID **2268**).

> **Firmware Version:** v309  
> **Device ID:** 2268  
> **Firmware File:** `2268_v309.bin`

---

## Purpose

This repository exists to preserve the official firmware for the **Attack Shark X65HE** and to document an issue that may leave the keyboard stuck in bootloader mode if the firmware cannot be retrieved from the vendor's backend.

The firmware included in this repository was obtained through the **official Attack Shark web updater** after the manufacturer's backend was updated to provide the missing firmware.

The goal is to help users understand the issue and preserve the firmware in case it becomes unavailable again.

---

# Background

My keyboard unexpectedly became stuck in bootloader mode during a firmware update.

Initially, the official web updater was unable to recover the keyboard because no firmware record was returned by the backend.

After extensive troubleshooting and communication with technical contacts in China, the firmware became available on the server and the update completed successfully.

The keyboard immediately recovered after flashing the firmware.

---

# Symptoms

Typical symptoms include:

- Keyboard not functioning
- Keyboard detected only as a bootloader device
- Official updater unable to continue
- Firmware lookup fails
- Update cannot proceed

---

# Root Cause (Observed)

From investigating the web updater and its API requests, the problem appeared to be related to the firmware backend rather than the keyboard hardware.

Initially:

- firmware lookup returned no valid firmware
- no firmware download occurred
- update process could not continue

Later:

- firmware version **v309** became available
- firmware metadata was successfully returned
- official updater downloaded the firmware
- flashing completed successfully
- keyboard recovered

---

# Device Information

| Item | Value |
|------|------|
| Keyboard | Attack Shark X65HE |
| Device ID | 2268 |
| Firmware | v309 |
| Firmware File | `2268_v309.bin` |

---

# Firmware

Current archived firmware:

```
firmware/2268_v309.bin
```

This firmware was downloaded through the official updater.

No modifications have been made.

---

# SHA256

It is recommended to verify the firmware before using it.

Windows:

```powershell
Get-FileHash .\2268_v309.bin -Algorithm SHA256
```

or

```cmd
certutil -hashfile 2268_v309.bin SHA256
```

Replace the value below after computing the hash:

```
SHA256:

<insert hash here>
```

---

# Recovery Notes

The official updater successfully recovered the keyboard after the firmware became available.

If your keyboard enters bootloader mode:

1. Launch the official updater.
2. Check whether firmware is available.
3. If the updater reports that no firmware exists, the issue may be related to the vendor backend rather than the keyboard itself.
4. If firmware is available, perform the update normally.

---

# Firmware History

| Version | Status |
|----------|--------|
| v308 | Factory firmware (observed in official software) |
| v309 | Recovery firmware successfully downloaded and flashed |

---

# Repository Structure

```
AttackShark-X65HE-Firmware/

README.md

firmware/
    2268_v309.bin

screenshots/

docs/

hashes.txt
```

---

# Known Information

- Keyboard model: Attack Shark X65HE
- Device ID: 2268
- Firmware version archived: v309
- Firmware obtained through official updater
- Successfully restored keyboard from bootloader mode

---

# Disclaimer

This repository is intended for archival, educational, and recovery purposes.

The firmware was obtained through the official Attack Shark firmware update process.

Use this firmware at your own risk.

I am not affiliated with Attack Shark or the keyboard manufacturer.

---

# Contributing

If you own an Attack Shark X65HE and have:

- older firmware versions
- newer firmware versions
- firmware dumps
- USB captures
- update logs
- documentation

please open an Issue or Pull Request.

The goal is to preserve firmware and improve recovery information for the community.

---

# Acknowledgements

Thanks to the technical staff who restored the firmware on the vendor backend, making it possible to recover the keyboard.

Hopefully this repository helps other users avoid losing access to their devices if the firmware becomes unavailable again.
