============================================================
  
  Arch Linux Dual Boot Installer
  Works on any UEFI PC with Windows pre-installed

  Requirements:
    - UEFI system (not legacy BIOS)
    - Secure Boot OFF in BIOS (Limine doesn't support it)
    - Free/unallocated space on any internal drive, OR an
      existing partition to delete (script will offer both)
    - Internet connection on the Arch live ISO

  Hardcoded preferences:
    Keyboard   : us
    
    Locale     : en_GB.UTF-8
    
    Mirrors    : Switzerland
    
    Desktop    : GNOME
    
    Bootloader : Limine (UEFI)
    
    Encryption : LUKS2
    
    Filesystem : Btrfs with subvolumes
    
    Swap       : none

  HOW TO RUN from the Arch ISO:
============================================================
    bash <(curl -s https://arch.niiix.net/install | tr -d '\r')
============================================================
