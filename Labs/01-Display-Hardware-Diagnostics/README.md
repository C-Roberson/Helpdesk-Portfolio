# Lab 01: Display Hardware Diagnostic & Internal Screen Troubleshooting

## Project Title & Objective
* **Title:** Troubleshooting Laptop Internal Display Failure
* **Objective:** Systematically diagnose and isolate a black laptop screen, determining whether the root cause stems from software/drivers or physical hardware failure.

---

## Tech Stack & Tools
* **Operating System:** Windows 11 Home
* **Hardware:** Razor Blade 17 Laptop (Internal Display Panel), External Monitor (HDMI/USB-C)
* **Diagnostics Utilities:** Windows Display Settings, Device Manager, BIOS/UEFI Environment, Graphics Driver Reset Shortcut (`Win + Ctrl + Shift + B`)

---

## Environment & Hardware Topology
```text

```

---

## Diagnostic Walkthrough
  ***1. Initial triage & external output verification***
* **Observation:** Laptop powered on successfully (power indicator active, cooling fans operational, keyboard backlights illuminated), but the internal display remained completely black.
* **Action:** Connected an external monitor via HDMI to test video output.
* **Result:** External monitor displayed the Windows desktop normally. This isolated the failure, proving that the CPU, mainboard, and graphics processor (GPU) were functional.
     
  ***3. Graphics Driver Subsystem Reset***
* **Action:** Attempted to force-reload the graphics driver using the Windows shortcut (`Win + Ctrl + Shift + B`).
* **Result:** No screen flicker or audio beep occurred, indicating that Windows was failing to establish a low-level hardware handshake with the internal panel.
     
  ***4. BIOS Level Hardware Isolation (POST Environment)***
* **Action:** Restarted the machine and entered the BIOS/UEFI setup utility.
* **Result:** Internal screen remained dead, and when external monitor was disconnected, unit remained on but no change to internal screen. Because graphics drivers do not load in the BIOS environment, this ruled out the Windows driver corruption or OS-level display configurations.
   
---

## Troubleshooting Log
| Symptom | Diagnostic Test Performed | Root Cause Identified | Resolution & Mitigation |
| :--- | :--- | :--- | :--- |
|Internal screen black; external monitor works fine | Tested external video output, attempted driver reset shortcut, and checked BIOS behavior. | Physical hardware failure (Loose eDP display cable, faulty panel backlight, or disconnected ribbon connector). | 1. Configured Windows power options for "Clamshell Mode" (do nothing when the lid is closed) to use the laptop as a desktop with the external monitor. 2. Scheduled physical chasis teardown to reseat the eDP ribbon cable or replace the panel assembly. |

---

## Key Takeaways
 * **Logical Elimination:** Always test non-invasive variables first (external displays, safe mode, BIOS) before opening hardware chasis.
 * **POST Verification:** Checking hardware behavior inside the BIOS is best for separating software driver issues from physical component failures.

---
