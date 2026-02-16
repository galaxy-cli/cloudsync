# cloudsync
A dynamic and flexible Bash-based cloud file manager that uses rclone to sync, copy, and manage files across multiple cloud storage providers simultaneously.

## Overview
cloudsync is a powerful CLI utility designed to automate the management of important files—such as KeePassXC databases or Cryptomator vaults—across various cloud remotes. Unlike standard sync tools, it allows you to target multiple cloud services in a single command and manage them without hardcoded directory restrictions.

### Key Features
 * Dynamic Remote Selection: Specify which cloud services to use at runtime with `-c` or `--cloud`.
 * Multiple Actions: Supports direct syncing, copying, directory creation, and deletion (files or entire folders).
 * No Hardcoded Paths: You define both the local source and the exact remote destination for every command.
 * Verbose Mode: Use `-v` or `--verbose` to see the exact rclone commands being executed for debugging.
 * Automated Setup: Checks for rclone and handles installation or updates if missing.
 * Colored Output: Uses formatted status messages to clearly indicate successes, skips, or errors.

<<<<<<< HEAD
### Prerequisites
 * Environment: Bash shell on Linux, macOS, or WSL.
 * rclone: Must be installed and configured with your desired cloud remotes (e.g., drive, mega, s3).

### Installation
 * Download the script and place it in your path (e.g., `~/scripts/cloudsync`).
 * Make the script executable:
   `chmod +x cloudsync`
=======
It supports syncing to multiple popular remotes configured in `rclone` (e.g., Google Drive, MEGA, pCloud) and can sync to one or all of them at once.

While this script was created mainly for personal use, it is shared here to showcase the approach and automation that can be useful for personal cloud backups.

---

## Features

- Checks for the presence of [rclone](https://rclone.org/) and optionally installs it automatically.
- Supports syncing either a single file or an entire folder.
- Syncs to one or multiple cloud storage remotes in a single run.
- Supports the following cloud providers configured in rclone:
  - Google Drive
  - MEGA
  - pCloud
- Uses colored output for status messages to improve readability.
- Shows transfer progress while syncing.

---

## Prerequisites

- Bash shell on a Unix-like system (Linux, macOS, WSL).
- [rclone](https://rclone.org/) installed and configured with at least one remote matching the remotes supported by the script.
- Internet connection.

---

## Setup & Installation

1. Ensure you have `rclone` configured with your desired cloud remotes.  
   Example: setting up Box remote named `Box`, Google Drive named `Google`, etc.

2. Place the script file somewhere on your system, e.g., `~/scripts/cloudsync`.

3. Make the script executable:

`chmod +x cloudsync`


4. Run the script directly, or create an alias or cron job to automate backups.

---
>>>>>>> 0f50fdc62f9eab2527f312df98bd95cc62b58a75

## Usage
The script now relies on flags for all operations. Running the script without arguments or with -h will display the help menu.

**Available Actions**
| Action | Description |
|---|---|
| `--sync` | Sync local to remote (Warning: Deletes files on remote not present locally) |
| `--copy` | Copy files/folders to remote without deleting anything |
| `--make-dir` | Create a new directory on the specified remotes |
| `--remove` | Delete a specific file from the specified remotes |
| `--remove-dir` | Purge an entire directory from the specified remotes |
| `-l`, `--list` | List files at the specified remote destination |

**Options**
| Flag | Description |
|---|---|
| `-c`, -`-cloud` | Comma-separated list of remotes (e.g., "Google,MEGA") |
| `-p`, `--path` | The local source path on your machine |
| `-d`, `--dest` | The remote destination path |
| `-v`, `--verbose` | Enable command logging to see what is happening under the hood |

## Examples
- Sync a local folder to multiple clouds:
`cloudsync --sync -c "Google Drive,MEGA" -p ~/Documents/Vault -d "Backups/Vault"`

- Copy a single file to a specific cloud folder:
`cloudsync --copy -c "pCloud" -p ~/backup.kdbx -d "Security/Databases"`

- Create a new directory across all your services:
`cloudsync --make-dir -c "Google Drive,MEGA,pCloud" -d "NewProjects/2024"`

<<<<<<< HEAD
- Remove a file and verify with Verbose mode:
`cloudsync --remove -v -c "MEGA" -d "NewProjects/2024/old_file.txt"`
=======
3. Detect if the path is a file or folder; exit if invalid.

4. Ask you to select one or multiple cloud remotes to sync to:
   - Choose from Box, Google Drive, Koofr, MEGA, pCloud.
   - Option to sync to all remotes in one go.

---
>>>>>>> 0f50fdc62f9eab2527f312df98bd95cc62b58a75

## License
This project is licensed under the MIT License.

## Author & Contact
**galaxy-cli**

GitHub: [https://github.com/galaxy-cli/cloudsync](https://github.com/galaxy-cli/cloudsync)