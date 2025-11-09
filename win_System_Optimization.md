#  Windows Optimization Guide for Your System

**System:** HP Laptop 15-fc0xxx  
**Specs:** 8 GB RAM (7.4 GB usable), AMD CPU, Windows 11 Home SL (Build 26200)

---

##  1. Memory (RAM) Optimization

Your system shows:
- **Available Physical Memory:** 811 MB
- **Virtual Memory In Use:** 18 GB

That means the system is swapping heavily to disk (slow). Let's fix that.

###  Step-by-step:

#### (A) Identify High Memory Apps

1. Press `Ctrl + Shift + Esc` → opens Task Manager
2. Click **Memory** column to sort descending
3. Right-click & "End Task" for:
   - Microsoft Teams (if idle)
   - Edge/Chrome with many tabs
   - Adobe or other background-heavy apps

#### (B) Disable Unnecessary Startup Apps

1. In Task Manager → **Startup apps** tab
2. Disable everything not essential (e.g., Spotify, OneDrive, Zoom, etc.)
3. Keep only:
   - Windows Security
   - Graphics Driver (AMD)
   - HP Support Assistant (optional)

#### (C) Adjust Virtual Memory Manually

You can reduce pagefile dependency:

1. Press `Win + R` → type `sysdm.cpl` → Enter
2. **Advanced** tab → "Performance" → **Settings**
3. **Advanced** → "Virtual memory" → **Change**
4. Uncheck "Automatically manage paging file size"
5. Choose **C:** → Set:
   - **Initial size** = 4096 MB
   - **Maximum size** = 8192 MB
6. Click **Set** → **OK** → **Restart**

 This stops Windows from oversizing the swap file and improves performance.

---

##  2. Background Process Optimization

### Disable Visual Effects

1. Press `Win + R` → `sysdm.cpl` → **Advanced** → **Performance** → **Settings**
2. Choose **Adjust for best performance**
3. Optionally re-enable:
   - Smooth edges of screen fonts
   - Show thumbnails instead of icons

This can save 400–600 MB of RAM.

---

##  3. HP & Windows-Specific Optimizations

### (A) Turn off HP background services

1. Press `Win + R` → `services.msc`
2. Look for:
   - "HP Analytics Service"
   - "HP Touchpoint Analytics Client"
3. Right-click → **Properties** → Set **Startup type: Disabled**

HP ships with telemetry tools that use 200–400 MB.

### (B) Disable Unused Windows Features

1. Open **Windows Features** (search "Windows features on or off")
2. Uncheck:
   - Internet Explorer Mode
   - Windows Subsystem for Linux (if unused)
   - Microsoft XPS Document Writer
   - Print to PDF (if not needed)

---

##  4. Clean Temporary Files

### (A) Use Storage Sense

1. **Settings** → **System** → **Storage** → **Storage Sense**
2. Enable:
   - "Automatically clean temporary system files"
   - "Delete unused files in Recycle Bin after 1 day"

### (B) Manual Cleanup

1. Run `cleanmgr`
2. Select **Windows Update Cleanup**, **Temp Files**, **Thumbnails**

---

##  5. Disable VBS & Core Isolation (Optional, boosts performance 5–10%)

If you don't run Hyper-V or need advanced virtualization security:

1. Open **Windows Security** → **Device Security** → **Core Isolation**
2. Turn off **Memory Integrity**
3. Restart PC
4. Then run:
```cmd
   systeminfo | find "Virtualization-based security"
```

It should show **Not running** (performance improved).

---

##  6. AMD Processor Optimization

### (A) Enable Ultimate Performance Mode

Run in **PowerShell (Admin)**:
```powershell
powercfg -duplicatescheme e9a42b02-d5df-448d-aa00-03f14749eb61
```

Then go to:
- **Settings** → **Power & Sleep** → **Additional Power Settings** → **Ultimate Performance**

### (B) Update AMD Drivers

- Use official **AMD Auto-Detect tool**  
  👉 https://www.amd.com/en/support
- Select your CPU/GPU combo and update chipset + graphics drivers.

---

##  7. Reduce Background Services

Run:
```cmd
services.msc
```

Disable (set **Startup type: Manual** or **Disabled**) for:
- Xbox Services (GameSave, Networking)
- Connected User Experiences
- Windows Search (if not used often)
- Print Spooler (if no printer)

---

##  8. Optional Lightweight Alternatives

| Heavy App | Lightweight Alternative |
|-----------|------------------------|
| Chrome | Brave / Edge / Firefox |
| MS Teams | Web version |
| Adobe Reader | SumatraPDF |
| MS Office | LibreOffice / Office Web |

---

##  9. Advanced (Power Users)

If you're comfortable with PowerShell:
```powershell
Get-Service | Where-Object {$_.Status -eq "Running"} | Sort-Object -Property StartType
```

Identify services that aren't essential → disable as needed.

---

##  10. Hardware Upgrade (Final Option)

If you can:
- Upgrade RAM to **16 GB** (2×8 GB DDR5/DDR4 depending on model)
- Install **NVMe SSD** (if not already)

This will completely eliminate the lag and swap issue.

---
h |
