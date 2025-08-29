# 🚀 PARTITION-CLONER-FILLER 🚀

![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)
![Made with Bash Script](https://img.shields.io/badge/Made%20with-Bash%20Script-1f425f.svg)
![ShellCheck](https://img.shields.io/badge/shellcheck-passing-brightgreen.svg)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)
[![GitHub stars](https://img.shields.io/github/stars/LINUX-OASIS/PARTITION-CLONER-FILLER.svg?style=social&label=Star)](https://github.com/LINUX-OASIS/PARTITION-CLONER-FILLER/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/LINUX-OASIS/PARTITION-CLONER-FILLER.svg?style=social&label=Fork)](https://github.com/LINUX-OASIS/PARTITION-CLONER-FILLER/network/members)

An interactive TUI (Text-based User Interface) script for cloning, growing, and copying EXT4, BTRFS, and FAT32 partitions with ease and power.

---

## ✨ Features

*   **Interactive TUI:** Uses `whiptail` for a user-friendly, menu-driven experience.
*   **Multiple Cloning Methods:**
    *   **Block-Level Clone (`dd`):** A raw, bit-for-bit clone for any filesystem type. Perfect for creating an exact replica on a partition of the same or larger size.
    *   **Filesystem-Level Copy (`rsync` / `btrfs`):** An intelligent copy that only moves data, not empty space. This allows you to "clone" to a smaller partition, as long as the data fits!
*   **Filesystem Resizing:** Automatically expands EXT4 and BTRFS filesystems to fill the partition after a `dd` clone. Also includes a standalone resize tool.
*   **Safety First:** Multiple confirmations and clear warnings before any destructive action. Includes a countdown timer before `dd` operations.
*   **Dependency Check:** Verifies that all required tools are present before running.
*   **Robust Cleanup:** Safely handles temporary mount points and cleans up after itself, even if the operation is aborted.

## ⚠️ IMPORTANT WARNING ⚠️

> This script performs **DESTRUCTIVE** operations. All cloning and copying methods will **IRREVERSIBLY ERASE ALL DATA** on the selected destination partition.
>
> **PROCEED WITH EXTREME CAUTION.** The maintainer is not responsible for any data loss.

## 🖥️ Compatibility

This script is designed for Debian-based Linux distributions and should work on:

*   Debian
*   Ubuntu
*   Linux Mint
*   Other Debian/Ubuntu derivatives that use the `apt` package manager.

While it may work on other systems, it is only officially supported on these platforms.

## ⚙️ Dependencies

The script requires several common command-line utilities to function. It will automatically check for them when you run it.

**Required commands:**
`whiptail`, `lsblk`, `awk`, `grep`, `dd`, `btrfs`, `resize2fs`, `sync`, `fsck.vfat`, `mktemp`, `df`, `rsync`, `mkfs.ext4`, `mkfs.vfat`

If any dependencies are missing, the script will notify you and exit. You can typically install the packages that provide these tools on a Debian-based system with:

```bash
sudo apt-get update
sudo apt-get install whiptail coreutils util-linux awk grep btrfs-progs e2fsprogs dosfstools rsync
```

## 🚀 Getting Started

### Installation

1.  Clone the repository:
    ```bash
    git clone https://github.com/LINUX-OASIS/PARTITION-CLONER-FILLER.git
    ```
2.  Navigate to the directory:
    ```bash
    cd PARTITION-CLONER-FILLER
    ```

### Usage

The script must be run with root privileges.

```bash
sudo ./custom-PARTITION-CLONER-FILLER.sh
```

You will be guided through the process by an interactive menu.

---

## 💬 Contributing

Pull requests, issues, and suggestions are warmly welcomed!

## 🧙‍♂️ Maintainer

*   **LINUX-OASIS** - https://github.com/LINUX-OASIS

## 📜 License

This project is licensed under the GNU General Public License v3.0. You should have received a copy of the GNU General Public License along with this program. If not, see https://www.gnu.org/licenses/.
