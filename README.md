# NiiX Arch Installer

A fully automated Arch Linux installer that sets up a modern, gaming‑ready system with LUKS2 encryption, Btrfs snapshots, the CachyOS kernel, GNOME desktop, and a complete gaming toolchain – all with minimal user input.

> **Website:** 
https://arch.niiix.net

---

## ✨ Features

- **Dual‑boot or single‑boot** – Detects Windows automatically, preserves existing OS in dual‑boot mode.
- **Full disk encryption** – LUKS2 with a custom passphrase.
- **Btrfs subvolumes** – `@`, `@home`, `@snapshots`, `@var_log` – ready for Snapper snapshots.
- **Limine bootloader** – Clean, fast, and secure (UEFI only).
- **CachyOS kernel** – BORE scheduler, installed automatically on first boot.
- **GPU auto‑detection** – Installs the right drivers for AMD, NVIDIA, or Intel (including open kernel modules for Turing+).
- **Gaming optimisations** – GameMode, MangoHud, GE‑Proton, DXVK, ntsync, and AUR helpers (yay) out of the box.
- **Security & performance** – UFW firewall, DNS‑over‑TLS, MAC randomisation for WiFi, ZRAM swap, and optional CPU mitigations.
- **First‑boot automation** – Installs CachyOS kernel, AUR packages, flatpaks, sets GNOME preferences, and downloads the NiiX wallpaper – all without further user interaction.

---

## 📋 Requirements

- **UEFI system** (Legacy BIOS is not supported)
- **Secure Boot disabled** – Limine does not support it
- **Internet connection** while running the Arch Linux live ISO
- **At least 10 GiB** of free disk space (or an entire drive to wipe)

---
## Stargazers over time
[![Stargazers over time](https://starchart.cc/JaKooLit/Arch-Hyprland.svg?variant=adaptive)](https://starchart.cc/JaKooLit/Arch-Hyprland)

## 🚀 How to run

1. Boot the [Arch Linux live ISO](https://archlinux.org/download/).
2. Connect to the internet (use `iwctl` if you need WiFi).
3. Run the installer with this **single command**:

```bash
bash <(curl -s https://arch.niiix.net/install | tr -d '\r')


## Stargazers over time
[![Stargazers over time](https://starchart.cc/JaKooLit/Arch-Hyprland.svg?variant=adaptive)](https://starchart.cc/JaKooLit/Arch-Hyprland)
