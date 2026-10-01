# NiiX Arch Installer

A fully automated Arch Linux installer that sets up a modern, gaming‑ready system with LUKS2 encryption, Btrfs snapshots, the CachyOS kernel, GNOME desktop, and a complete gaming toolchain – all with minimal user input.

> **Website:** https://niixa.org

---

## Features

- **Full-disk encryption** – LUKS2, unlocked once at boot
- **Btrfs + Snapper** – automatic snapshots before and after every update, plus a clean-state boot entry
- **CachyOS kernel** – performance-tuned kernel with automatic GPU driver detection (NVIDIA, AMD, Intel, hybrid laptops)
- **GNOME desktop** – Windows-style taskbar and start menu, window snapping (halves, quarters, full screen)
- **Gaming ready** – Steam, Lutris, Heroic, ProtonUp-Qt and GE-Proton out of the box
- **Single or dual boot** – wipe a drive, or install next to Windows in free space
- **NTFS + USB** – Windows drives usable straight away; USB sticks auto-mount and are repaired if dirty
- **Wi-Fi hotspot** – optional, kept up automatically from boot
- **`niix-update`** – one command for system, AUR, Flatpak and firmware updates, checking Arch news first
- **No nags** – donation pop-ups turned off

---

## Requirements

- 64-bit (x86_64) PC with **UEFI** (no legacy BIOS)
- **Secure Boot turned off** (Limine, the bootloader, doesn't support it)
- An **internet connection** (Ethernet or Wi-Fi)
- The **Arch Linux ISO** on a USB stick
- Disk space:
  - **Single boot:** a drive you're willing to completely wipe
  - **Dual boot:** unallocated space next to Windows
  - 64 GB or more is recommended; games need more

---

## How to run

### 1. Download the Arch Linux ISO

Get the latest ISO from the official site: **https://archlinux.org/download/**

### 2. Put it on a USB stick

Use one of these tools to write the ISO to a USB stick (this erases the stick):

- **Rufus** (Windows): https://rufus.ie
- **balenaEtcher** (Windows, macOS, Linux): https://etcher.balena.io

### 3. Boot from the USB stick

1. In your BIOS/UEFI settings, **turn Secure Boot off**.
2. Restart and open the boot menu (usually **F12**, **F11**, **F8** or **Esc** while the PC starts).
3. Choose the USB stick, then the first entry, **Arch Linux install medium**.
4. Wait for the text prompt: `root@archiso ~ #`

> **Not a US keyboard?** Some symbols are in different places until you switch. For example, `loadkeys de` (German), `loadkeys fr` (French) or `loadkeys uk` (UK).

### 4. Connect to the internet

**Ethernet:** just plug in the cable. You're already online, so skip to step 5.

**Wi-Fi:** type these commands one at a time.

Find your Wi-Fi card's name:

```bash
iwctl device list
```

It's usually `wlan0`; use whatever name is shown in the commands below.

Scan, then list the networks in range:

```bash
iwctl station wlan0 scan
iwctl station wlan0 get-networks
```

Connect, replacing `YOUR-NETWORK` and `YOUR-PASSWORD` (keep the quotes):

```bash
iwctl --passphrase "YOUR-PASSWORD" station wlan0 connect "YOUR-NETWORK"
```

Check it works. You should see replies, not errors:

```bash
ping -c 3 archlinux.org
```

> **Wi-Fi not found or "blocked"?** Run `rfkill unblock wifi` and try again.

### 5. Run the installer

```bash
bash <(curl -fsSL https://niixa.org/install)
```

The installer checks itself against the checksum in this repository before changing anything, then asks a few questions and does the rest.

**Recommended – verify before running:**

```bash
curl -fsSLo install https://niixa.org/install && curl -fsSL https://raw.githubusercontent.com/techniixdotcom/niixarch-install/main/install.sha256 | grep ' install$' | sha256sum -c && bash install
```

If you see `install: OK`, the installer starts. If you see `FAILED`, don't run it.

### 6. First login

After the install the PC reboots. Unlock the disk with your passphrase. On the first login a one-time setup finishes the system (kernel, drivers, apps) and reboots once more when it's done.
