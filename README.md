# attackshark-keyboard-firmware

Archive of the official firmware for the Attack Shark X65HE Hall Effect keyboard (Device ID 2268), preserved to help recover keyboards stuck in bootloader mode when the vendor's backend fails to serve firmware.

**Firmware Version:** v309  
**Device ID:** 2268  
**Firmware File:** `firmware/2268_v309.bin`

---

## Background

- Keyboard got stuck in bootloader mode after a firmware update attempt; the official updater couldn't find a firmware record on the vendor's backend.
- - After contacting technical support, the backend was restored and firmware v309 became downloadable again, which fixed the keyboard.
  - - This repo preserves that firmware so other users aren't stuck if the backend issue recurs.
   
- ## Symptoms
   
- - Keyboard unresponsive
- - Detected only as a bootloader device
- - Official updater can't find firmware
- - Update can't proceed
           
- ## How to Flash
           
- **Normal method (try this first):**
           
- 1. Download and launch the official Attack Shark firmware updater.
  2. When prompted for a device/firmware ID, enter **2268** (this is the X65HE's device ID, which isn't always obvious from the updater UI).
  3. If the updater finds firmware, let it download and flash normally.
  4. **If the official updater fails to find firmware:**
  5. There isn't yet a verified manual/alternative flashing procedure for this keyboard. If you've successfully flashed manually (e.g. via a bootloader tool) and can document the steps, please open an Issue or Pull Request — this section will be updated once a reliable method is confirmed.
  6. ## Device Information
  7. | Item | Value |
  8. |------|-------|
  9. | Keyboard | Attack Shark X65HE |
  10. | Device ID | 2268 |
  11. | Firmware | v309 |
                   
  12. ## Verify Firmware (SHA256)
                   
  13. It's recommended to verify the firmware before using it.
  14. Windows:
  15. ```
      Get-FileHash .\2268_v309.bin -Algorithm SHA256
      ```
      or
      ```
      certutil -hashfile 2268_v309.bin SHA256
      ```

      Compare the result against the value in `hashes.txt`.

      ## Firmware History

      | Version | Status |
      |---------|--------|
      | v308 | Factory firmware (observed in official software) |
      | v309 | Recovery firmware successfully downloaded and flashed |

  ## Repository Structure

  ```
  firmware/2268_v309.bin
  screenshots/
  README.md
  hashes.txt
  LICENSE
  ```

## Disclaimer

This repository is intended for archival, educational, and recovery purposes. The firmware was obtained through the official Attack Shark firmware update process, unmodified. Use at your own risk. I am not affiliated with Attack Shark or the keyboard manufacturer.

## Contributing
If you have older/newer firmware versions, firmware dumps, USB captures, update logs, documentation, or a working manual-flash method, please open an Issue or Pull Request.

## Acknowledgements

Thanks to the technical staff who restored the firmware on the vendor backend, making it possible to recover the keyboard. Hopefully this repository helps other users avoid losing access to their devices if the firmware becomes unavailable again.
                        
