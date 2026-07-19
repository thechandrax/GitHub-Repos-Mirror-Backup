# Git Repositories Mirror Backups

This repository contains compressed ZIP mirror backups of Git repositories, stored directly in the root directory.

## Repository Backups Catalog

| S.No | Backup Date | Repository Name | Source Remote URL | Archive File | Branches | Tags | Status |
| :--- | :--- | :--- | :--- | :--- | :---: | :---: | :---: |
| 01 | 2026-07-19 | shannon | `https://github.com/KeygraphHQ/shannon` | `01. shannon.git.zip` | 6 | 12 | ✅ Active |

---

## Restoring a Backup

To extract and restore a repository backup:
1. Download the `.git.zip` archive (e.g. `01. shannon.git.zip`).
2. Unzip the file to a folder. It will contain the bare Git database directory (e.g., `01. shannon.git`).
3. Open a terminal and run the standard clone command:
   ```bash
   git clone /path/to/extracted/01. shannon.git MyWorkingCopy
   ```
4. All branches, commit logs, history, and tags will be fully unpacked inside `MyWorkingCopy`.
