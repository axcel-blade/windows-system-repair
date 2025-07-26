# 🧰 Windows OS Error Check & Repair via Command Line
This guide explains how to check and fix system errors on Windows using the command line tools. We'll cover the necessary commands and steps to identify and resolve common issues.

## 🛠 1. System File Checker (SFC)
### 🔧 Steps

1. Open Command Prompt as Administrator: Press Windows + X → select Command Prompt (Admin) or Windows Terminal (Admin).
2. Run the following.
```
sfc /scannow
```

3. Wait until the scan completes. Do not close the window during the process.

## 🛠 2. Deployment Imaging Service and Management Tool (DISM)
The DISM tool repairs the Windows system image and component store.
### ✅ Commands to Run in Sequence
```
DISM /Online /Cleanup-Image /CheckHealth
```
```
DISM /Online /Cleanup-Image /ScanHealth
```
```
DISM /Online /Cleanup-Image /RestoreHealth
```

### 🔍 Description
- /CheckHealth – Quickly checks for known corruption.

- /ScanHealth – Performs a deeper scan for problems.

- /RestoreHealth – Repairs the image using Windows Update or a specified source.

### ✅ Recommended Full Repair Sequence
1. Open terminal as Administrator.
2. Run the following
```
DISM /Online /Cleanup-Image /RestoreHealth
```
3. Then run
```
sfc /scannow
```

## ⚙️ Automate with a Batch File
Instead of running each command manually, you can use a batch file to automate the process.

### ▶️ How to Run
- Right-click the file repair-windows.bat and choose Run as Administrator.

## ℹ️ Notes
- These tools are built into Windows and safe to use.

- Requires an internet connection for DISM if using Windows Update as the repair source.

- You can use these commands to fix issues like:
    - Missing/corrupt system files
    - Random crashes or BSODs
    - Windows Update problems