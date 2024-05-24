# Arch Install Utils [luks -> lvm -> btrfs]
Utils to create an Full Disk Encryption installation easy.

## Utility Scripts
- make-iso: bundle everything as an easy to mount iso image
- make-user: creates new system user as sudoers

## Bundles
Each bundle contains a package list and a list of enabled systemd units that should be enabled with it.
- base: out of box working system with internet, contains a lot of cmd utils and dev tools
- plasma: kde plasma desktop with sddm, filemanager, browser, mail client.... - most things are already installed that are used regulary

## Filesystem Overwrites
overwrites following files on the newly installed base system
- /etc/kernel/cmdline: set sysfs partition, supress bootlog, show splashscreen
- /etc/initcpio/post/uki-sbctl: post hook to generate a signed unified kernel image
- /etc/mkinitcpio.d/linux.preset: defines a single kernel image as build target (fallback disabled)
- /etc/crypttab.initramfs: mapping from luks partlabel to unlocked volume
- /etc/locale.gen: language presets
- /etc/mkinitcpio.conf: defines hooks for required initramfs modules
- /etc/sudoers: minimal config with wheel group enabled


