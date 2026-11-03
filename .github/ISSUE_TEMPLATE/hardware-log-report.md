---
name: "📋 2012–2015 Mac Hardware & Log Report"
about: Submit verbose boot logs or crash dumps for Ivy Bridge, Haswell, and Broadwell Macs running macOS 27.
title: "[LOG] <MacModelIdentifier> - <CPU/GPU Model>"
labels: ["telemetry", "2012-2015-mac"]
assignees: ""
---

### 💻 Mac Hardware Profile
*   **Mac Model Identifier:** (e.g., MacPro6,1, MacBookPro11,3, iMac13,2)
*   **Processor / CPU:** (e.g., Intel Xeon E5-1650 v2, Core i7-4770HQ)
*   **Graphics / GPU:** (e.g., Dual AMD FirePro D300, NVIDIA GeForce GT 650M, Intel Iris Pro 5200)
*   **System Memory (RAM):** (e.g., 16GB DDR3)

### 🚀 Boot Behavior & Stage Reached
*Please select the furthest point your system successfully reached before stalling or crashing:*
- [ ] **Stage 1:** Immediate Kernel Panic (Never reaches the Apple logo)
- [ ] **Stage 2:** Apple Logo draws, but progress bar hangs/loops
- [ ] **Stage 3:** `WindowServer` attempts to initialize (Screen flickers, black screen, or verbose wall loops)
- [ ] **Stage 4:** `loginwindow` / Login screen draws (Can see wallpaper/UI, but password handoff or UI crashes)

### 📑 Captured Telemetry & Logs

#### OpenCore Boot Log
*Please paste or drag-and-drop the contents of your `opencore-YYYY-MM-DD-HHMMSS.txt` log below:*
```text
[Paste OpenCore log here]
```

#### Verbose/Panic Screen Capture
*If your system text-panicked or looped on a specific sub-system framework error, please paste the terminal excerpt or drag an image upload here:*
```text
[Paste panic trace or paste screen photo here]
```

### 🛠 Active Boot Arguments Used
*List any specific boot-args or experimental kext combinations you applied during this boot run:*
```text
-v debug=0x100 keepsyms=1 msgbuf=1048576
```
