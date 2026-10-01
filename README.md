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

https://archlinux.org/download/

### 2. Put it on a USB stick

Use **balenaEtcher** (https://etcher.balena.io) to write the ISO to a USB stick, or install **Ventoy** (https://www.ventoy.net) on the stick and copy the ISO onto it.

### 3. Boot from the USB stick

1. In your BIOS, **turn Secure Boot off**.
2. Restart and open the boot menu (usually **F12**, **F11** or **Esc**).
3. Pick the USB stick, then **Arch Linux install medium**.

### 4. Connect to Wi-Fi

Skip this step if you use a network cable.

Type:

```bash
iwctl
```

Then type this, using your Wi-Fi name (keep the quotes):

```bash
station wlan0 connect "YOUR-WIFI-NAME"
```

Enter your Wi-Fi password when asked, then press **Ctrl + C** to leave.

### 5. Run the installer

```bash
bash <(curl -fsSL https://niixa.org/install)
```

Answer the questions and the installer does the rest. After it reboots, unlock the disk with your passphrase; the first login finishes the setup automatically.

---

**Optional – verify the installer before running it:**

```bash
curl -fsSLo install https://niixa.org/install && curl -fsSL https://raw.githubusercontent.com/techniixdotcom/niixarch-install/main/install.sha256 | grep ' install$' | sha256sum -c && bash install
```
