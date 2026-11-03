# OpenCore Patcher Fork: macOS 27 Golden Gate Support

A specialized fork of OpenCore dedicated to testing, optimizing, and gathering telemetry for running **macOS 27 Golden Gate on Intel hardware**. Inspired by the groundbreaking bare-metal milestones achieved by `null-moth`, this repository serves as a testing ground and log-collection hub to help expand hardware compatibility for the upcoming v3 release.

> ⚠️ **Disclaimer:** This project is in an active experimental phase. macOS 27 natively removes all x86_64 kernel structures. Running it on Intel silicon relies on highly advanced injection and translation methodologies. Expect instabilities, frequent crashes, and breaking changes.

---

## 🎯 Target Hardware Focus: Phase 1 (2012–2015)

Our initial testing phase strictly targets **2012 to 2015 vintage Intel Macs**. Because the foundational breakthrough was achieved on the 2013 Mac Pro hardware, stabilizing machines from this specific era (Ivy Bridge, Haswell, and Broadwell architectures) is our top priority before attempting broader PC/Hackintosh compatibility.

### Priority Models for Log Collection:
* **Mac Pro:** 2013 "Trash Can" (MacPro6,1) — *Primary Validation Target*
* **MacBook Pro:** Retina 13" and 15" models (2012–2015)
* **iMac:** Slim unibody models (2012–2015)
* **Mac mini & MacBook Air:** Intel Haswell/Broadwell configurations (2013–2015)

---

## 🚀 Project Status & Target Milestones

- [x] **Fork Created:** Repository baseline established.
- [x] **Hardware Scope Defined:** Focusing testing infrastructure on 2012–2015 Apple hardware configurations.
- [ ] **Pre-Release Alignment:** Preparing configuration structures for the upcoming v3 community stream.
- [ ] **Telemetry Gathering:** Collecting verbose boot logs from the targeted 2012–2015 model spectrum.
- [ ] **Driver Integration:** Testing the stabilization of legacy DriverKit structures and macOS 26 kext injection layers.

---

## 🛠 Working Environment Setup

To ensure you can capture the precise telemetry required to troubleshoot the userland/kernel interface, your `config.plist` should be configured for exhaustive debugging.

### Recommended Boot Arguments
Add the following to your `NVRAM -> Add -> 7C436110-AB2A-4BBB-A880-FE41995C9F82 -> boot-args`:
```text
-v debug=0x100 keepsyms=1 msgbuf=1048576
```
* `-v`: Enables verbose booting to see exactly where the initialization sequence halts.
* `debug=0x100`: Prevents the system from instantly rebooting on a kernel panic so you can capture a photo or log.
* `keepsyms=1`: Retains symbols in the panic log to make the call stack readable.

---

## 📋 How to Contribute (Log Collection)

If you have a machine within the **2012–2015** range and want to submit logs, please open an Issue using our log template:

1. **Mac Hardware Profile:** Specify your precise Mac Model Identifier (e.g., `MacPro6,1`, `MacBookPro11,3`), CPU, and GPU.
2. **Boot Log:** Attach the `opencore-YYYY-MM-DD-HHMMSS.txt` log generated on your EFI partition.
3. **Panic/Crash Capture:** If the system halts at the `WindowServer` or `loginwindow` phase, provide the exact stack trace or text readout.

---

## 🤝 Acknowledgments

An immense thank you to **`null-moth`** for refusing to accept the artificial hardware limits imposed on Intel silicon, bringing macOS 27 to bare metal at full speed, and keeping the ecosystem alive.
