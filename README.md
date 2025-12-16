# ⚡ Adrenaline Hook Enhanced

![Version](https://img.shields.io/badge/version-1.0.3.0-blue.svg) ![Platform](https://img.shields.io/badge/platform-Windows-lightgrey.svg)

**An improved fork of Adrenaline Hook with Custom Path Scanning, RTSS Integration, and Silent Operation.**

### 📖 Why "Enhanced"?
This project builds upon the original Adrenaline Hook by adding critical features requested by power users. While the original tool successfully hooked UWP games, this version expands compatibility significantly:

* **📂 Custom Path Scanning:** No longer limited to just UWP/Store apps. **You can now recursively scan any folder** (e.g., `D:\Games`, `C:\Mods`) to find and hook executables anywhere.
* **📊 Native RTSS Support:** Directly integrates with **RivaTuner Statistics Server**. It injects the game profile into RTSS automatically, fixing overlay detection issues common with UWP titles.
* **👻 True Silent Mode:** Recompiled to ensure absolutely **no console window** appears during execution.
* **🛡️ Robust Elevation:** Improved auto-elevation logic ensures registry writes never fail silently.

---

### ✨ Feature Breakdown

| Feature | Enhanced Functionality |
| :--- | :--- |
| **Custom Path Scan** | **(New)** Recursively searches any user-selected folder to find games installed in non-standard locations. |
| **RTSS Injection** | **(New)** Automatically adds the targeted executable to the RivaTuner list for FPS limiting and OSD support. |
| **UWP / Game Pass** | Standard scanning for all installed Microsoft Store applications. |
| **Adrenalin Hook** | Forces the game into the AMD Driver to unlock **RSR**, **Boost**, **Anti-Lag**, and **Chill**. |
| **Clean Unhook** | Removes the game profile and scrubs registry entries to prevent driver conflicts. |

---

### 📥 Installation & Usage

1.  Download **`Adrenaline Hook.exe`** from the [**Releases**](../../releases) page.
2.  Run the application (Admin rights will be requested for registry access).

#### 🛠️ Workflow:
1.  **Scan:**
    * Click **Scan Games** for standard Game Pass titles.
    * **OR** Click **Custom Path** to browse any folder on your drives.
2.  **Select:** Click the game you wish to modify.
3.  **Action:**
    * Click **Hook** to enable AMD Driver features.
    * Click **Add to RTSS** if you need the performance overlay.

---

### 📝 Build Source (v1.0.3.0)

This version is compiled using **PS2EXE** with specific flags for silent, elevated operation:

```powershell
Invoke-PS2EXE -InputFile "Adrenaline Hook.ps1" `
              -OutputFile "Adrenaline Hook.exe" `
              -IconFile "image.ico" `
              -requireAdmin `
              -noConsole `
              -version "1.0.3.0"
