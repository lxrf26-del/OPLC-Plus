# OpenCore Patcher Fork: macOS 27 Golden Gate Support

A specialized fork of OpenCore dedicated to testing, optimizing, and gathering telemetry for running **macOS 27 Golden Gate on Intel hardware**. Inspired by the groundbreaking bare-metal milestones achieved by `null-moth`, this repository serves as a testing ground and log-collection hub to help expand hardware compatibility for the upcoming v3 release.

> ⚠️ **Disclaimer:** This project is in an active experimental phase. macOS 27 natively removes all x86_64 kernel structures. Running it on Intel silicon relies on highly advanced injection and translation methodologies. Expect instabilities, frequent crashes, and breaking changes.

---

## 🚀 Project Status & Target Milestones

- [x] **Fork Created:** Repository baseline established.
- [ ] **Pre-Release Alignment:** Preparing configuration structures for the upcoming v3 community stream.
- [ ] **Telemetry Gathering:** Collecting verbose boot logs from varying Intel architectures (Ivy Bridge through Comet Lake).
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

The primary goal of this fork right now is expanding hardware support beyond the 2013 Mac Pro baseline. If you are testing early builds, please open an Issue using our log template:

1. **Hardware Profile:** Specify your CPU, GPU, and motherboard/Mac Model identifier.
2. **Boot Log:** Attach the `opencore-YYYY-MM-DD-HHMMSS.txt` log generated on your EFI partition.
3. **Panic/Crash Capture:** If the system halts at the `WindowServer` or `loginwindow` phase, provide the exact stack trace or text readout.

---

## 🤝 Acknowledgments

An immense thank you to **`null-moth`** for refusing to accept the artificial hardware limits imposed on Intel silicon, bringing macOS 27 to bare metal at full speed, and keeping the ecosystem alive.
