# GearOS!
Welcome to GearOS! GearOS is based off of NixOS version 17.03, but will be updated to keep in line with NixOS upgrades. GearOS is aimed at FIRST robotics teams to provide a fully operational, gratis, and mostly libre Linux environment for FIRST things. Initially, we are targeting GearOS for programmers, but we also plan to add packages that are useful for other things that a FIRST team would need (or want) to do.

Currently, we include:
  wget,
  android-studio,
  firefox,
  chromium,
  Eclipse Java Compiler,
  Eclipse Neon,
  n2048,
  Kdenlive,
  git-hub,
  vim,
  emacs,
  nano,
  sudo,
  ranger,
  w3m;
with more packages to be added as requested/wanted!

# Why Linux? Isn't Windows just fine?
Linux is advantageous for a variety of reasons. We'll list them for simlpicity:
  1. Linux is more efficient, and can run on weaker computers while retaining usability.
  2. The Linux command line integrates nicely with git, making it easy to manage Git repositories.
  3. Linux is free, FLOSS applications are free; Windows costs money, and proprietary software costs money. This lowers the   barrier to entry for less well-funded teams, and allows teams to have equal access to a working software suite without needingto fork up the money or hope for sponsors.
  4. Adjusting to Linux from Windows takes little time, and many converts report loving Linux much more than Windows after learning the differences.

# Why NixOS? Isn't Ubuntu more compatible?
Yes, technically Ubuntu is more widely used and therefore compatible with applications. Why we chose NixOS for the development of the GearOS suite is easy: an easily reproducable, simple to manage Linux distro that eases the install process to a few commands in terminal. Visit nixos.org for a more detailed explanation, but in simple terms, NixOS uses a central configuration file to manage the system install. This configuration file can be copied between computers, allowing for exact replicas to be installed on numerous computers without having to manually install each program; all the declared packages are installed with your system! This turns a tedious, time consuming process into a streamlined and custom experience just for FIRST robotics.

# How do I install GearOS?
  1. Download the GearOS .iso from nixos.org.
  2. Write the .iso to a USB stick. On Windows, use Rufus (dd mode has more compatibility, but you will need to repartition it to use it again.) On macOS or Linux, use dd from the terminal (dd if=/path/to/iso of=/dev/yourflashdrive).
  3. Boot into NixOS. This is usually accomplished by going into your BIOS settings, setting USB as the first boot option, then rebooting.
  4. Partition your hard drive from the NixOS installer, following the instructions on the NixOS manual (available at nixos.org) It'll tell you how to load into a KDE session, if you're not comfortable with terminal disk partitioning. REMEMBER TO BACK UP ALL FILES YOU NEED FROM THE TARGET DRIVE BEFORE FORMATTING. IT WILL DESTROY ALL YOUR DATA, AND LIKELY BE UNRECOVERABLE.
  5. Mount your newly partitioned hard drive to /mnt (mount /dev/yourhardrive /mnt)
  6. Type nixos-generate-config --root /mnt.
  7. Navigate to /mnt/etc/nixos (cd /mnt/etc/nixos)
  8. Remove the default configuration.nix (rm configuration.nix)
  9. Type nix-env -i git-hub (This installs Git to the liveUSB)
  10. Type git clone https://github.com/himynameisxtd/GearOS/configuration.nix (This specifically clones the latest config file to /etc/nixos)
  11. Use your favorite text editor (VIM, right?) to check and tweak the config file to your specific needs. The most popular thing to do will likely be switching the default DE from KDE (more resource-heavy) to XFCE (very lightweight, can make decade-old computers run beautifully).
  12. Type nixos-install, and everything should be taken care of from there!
These guidelines are simply, well, guidelines. Consult the NixOS manual if things don't work out the way it should, or feel free to post an issue on our Github page!
