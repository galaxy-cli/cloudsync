# cloudsync

A simple Bash script to securely sync your KeePassXC database, Cryptomator vault, or any file/folder to multiple cloud storage services using **rclone**.

---

## Overview

This is a personal utility script designed to help automate syncing important files or folders — such as your KeePassXC password database or Cryptomator encrypted vaults — to remote cloud storage providers.

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

## Usage

Run the script:

`./cloudsync`

The script will:

1. Check if rclone is installed.
   - If not installed, prompt to install it automatically.

2. Prompt you to enter the **full path** to the file or directory you want to sync.

3. Detect if the path is a file or folder; exit if invalid.

4. Ask you to select one or multiple cloud remotes to sync to:
   - Choose from Box, Google Drive, Koofr, MEGA, pCloud.
   - Option to sync to all remotes in one go.

---

## License

This project is licensed under the MIT License. See the LICENSE file for details.

---

## Author & Contact

**galaxy-cli**

GitHub: [https://github.com/galaxy-cli/cloudsync](https://github.com/galaxy-cli/cloudsync)
