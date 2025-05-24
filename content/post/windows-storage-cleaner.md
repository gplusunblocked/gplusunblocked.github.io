+++
title = "Windows CleanUp"
date = "2025-04-18"

author = "revWhiteShadow"
description = "Boost system performance and free up storage using two powerful Windows batch scripts that clean temp files, logs, update cache, and compress binaries."
category = "System Optimization"
tags = ["windows", "batch script", "cleanup", "optimization", "storage", "performance"]
keywords = ["Windows cleanup", "batch script cleaner", "optimize Windows", "free up space", "delete temp files", "compact OS", "dism cleanup"]
cover = "/img/windows-cleanup.png"
+++

# **Windows CleanUp**  
*Automated System Maintenance with Powerful Batch Scripts*

In the digital world, system performance and free disk space are two things that can make or break your computing experience. Over time, Windows accumulates temporary files, logs, update caches, and other clutter that slows down your PC. While many rely on third-party software for cleanup, batch scripting offers a **fast, lightweight, and customizable** alternative.

In this article, we introduce **two powerful batch scripts**—`cleanup.bat` and `windows clean.bat`—that are designed to **safely remove unnecessary files**, **boost system performance**, and **free up valuable disk space**.

## 🧹 `cleanup.bat`: The All-Rounder Script

This script is a **general-purpose cleaner** that focuses on user and system temp files, Windows Update cache, hibernation files, and even recycle bin contents.

### 🔧 Key Features:
- Cleans:
  - `C:\Windows\Temp`
  - `%TEMP%` (User's temporary folder)
  - `C:\Windows\Prefetch`
  - `C:\Windows\SoftwareDistribution\Download`
  - `C:\$Recycle.Bin`
- Disables hibernation to remove `hiberfil.sys`
- Deletes all System Restore points
- Restarts **Explorer** to ensure all UI elements are refreshed

### ✅ Best For:
- Users who want a **simple one-click cleanup** with wide coverage.
- Anyone looking to reclaim space from **temporary files and unused system components**.

## 🧼 `windows clean.bat`: The Deep System Cleaner

A more **aggressive and system-focused script**, `windows clean.bat` is great for tackling locked files and update leftovers by stopping key services temporarily during cleanup.

### 🛠️ What It Cleans:
- Windows Temp folder
- Windows Update cache
- Old update backup files using `DISM`
- Windows Prefetch
- Log files from `C:\Windows\Logs`
- Windows Error Reporting dumps from `C:\ProgramData\Microsoft\Windows\WER`

### 🔐 Safety Features:
- Stops and restarts:
  - `wuauserv` (Windows Update)
  - `BITS` (Background Intelligent Transfer Service)
  - `CryptSvc` (Cryptographic Services)

This ensures **locked files are safely removed**, and all services are restarted cleanly after the process.

### 🔄 DISM Cleanup:
```cmd
dism /online /cleanup-image /startcomponentcleanup /resetbase
```
This command removes superseded updates and significantly reduces **WinSxS folder bloat**.

## 📦 Extra: Compress Windows Binaries to Save More Space

Want to squeeze out even more space from your Windows installation? Add this powerful line at the end of your script:

```cmd
compact /compactos:always
```

### 🔹 What it does:
This command **compresses system binaries** using the Windows Compact OS feature. It's especially useful on systems with limited storage (like older laptops or tablets).

- Reduces the size of the Windows folder
- No impact on performance for modern systems
- Completely safe—Windows handles decompression on the fly

> ✅ *Note: This feature is natively supported on Windows 10/11 and works best on SSDs.*

## ⚠️ Important Notes Before Use

- **Run as Administrator**: These scripts require admin rights to access and delete protected files.
- **Data Caution**: Make sure you don’t store anything important in `Temp` or `Recycle Bin`, as these will be deleted without warning.
- **No UI**: These are command-line tools—there’s no “Undo” button. Use wisely!

## 📥 Download or Create Your Own

You can easily create these scripts using **Notepad**:

1. Copy the script content.
2. Paste it into a new `.txt` file.
3. Save the file as `cleanup.bat` or `windows clean.bat`.
4. Right-click and select **Run as administrator**.

[**Download the Scripts Here**](https://www.pling.com/p/2281376/)

For the full source code and more details, visit the official GitHub repository: [Windows Storage Cleaner GitHub](https://github.com/White9shadow/windows-storage-cleaner).

## 🚀 Final Thoughts

Using batch files like `cleanup.bat` and `windows clean.bat` provides a **lightweight, no-nonsense** approach to maintaining your Windows system. Add the binary compression command, and you’ve got a **powerful one-stop script** to clean, optimize, and compress your system all at once.

Whether you're a tech-savvy user or just looking for a way to clean up your PC without installing extra software, these scripts are powerful tools to keep in your utility kit.

Stay clean, stay fast! 💻🧼
