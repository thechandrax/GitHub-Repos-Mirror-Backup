# Git Repositories Mirror Backups

This repository contains compressed ZIP mirror backups of Git repositories, stored directly in the root directory.

## Repository Backups Catalog

| S.No | Backup Date | Repository Name | Source Remote URL | Archive File | Branches | Tags | Status |
| :--- | :--- | :--- | :--- | :--- | :---: | :---: | :---: |
| 01 | 2026-07-19 | shannon | [https://github.com/KeygraphHQ/shannon](https://github.com/KeygraphHQ/shannon) | `01. shannon.git.zip` | 6 | 12 | ✅ Active |
| 02 | 2026-07-19 | UI-TARS-desktop | [https://github.com/bytedance/UI-TARS-desktop](https://github.com/bytedance/UI-TARS-desktop) | `02. UI-TARS-desktop.git.zip.001` - `.003` *(Split)* | 275 | 547 | ✅ Active |

---

## How to Reassemble Split Archives

Some backup archives (like S.No 02) exceed the GitHub 100MB file size limit and are stored as split parts (`.zip.001`, `.zip.002`, etc.). You must combine them back into a single `.zip` file before extracting.

### Windows (PowerShell)
```powershell
Get-Content -Path "02. UI-TARS-desktop.git.zip.00*" -Encoding Byte -ReadCount 0 | Set-Content -Path "02. UI-TARS-desktop.git.zip" -Encoding Byte
```

### Windows (CMD)
```cmd
copy /b 02. UI-TARS-desktop.git.zip.00* 02. UI-TARS-desktop.git.zip
```

### Linux / macOS
```bash
cat 02. UI-TARS-desktop.git.zip.00* > 02. UI-TARS-desktop.git.zip
```

---

## Restoring a Backup

Once you have the single `.git.zip` archive file:
1. Unzip the `.git.zip` file to a folder. It will contain the bare Git database directory (e.g. `shannon.git`).
2. Open terminal/PowerShell and run:
   ```bash
   git clone /path/to/extracted/shannon.git MyWorkingCopy
   ```
3. All branches, commit logs, history, and tags will be fully unpacked inside `MyWorkingCopy` for normal viewing/editing.
