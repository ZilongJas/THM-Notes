### Windows Editions

*Summary*:
- Windows suck
- This room is outdated
- Bitlocker can be enabled on Pro version which encrypts your disk drives.
- This question "Besides Clock and Network, what other icon is visible in the Notification Area?" is bugged inside this vm FYI (I looked at a walkthrough and it was different than the VM I connected to).

### The File System 

- NTFS (New Technology File System) is used in modern Windows. Compared to Linux which commonly uses ext4 (Check out my homelab-security repo) where I partitioned a virutal disk on linux systems.
- FAT = File Allocation Table, used in USB devices, MicroSD cards.

### NTFS vs. FAT:

- NTFS:
  - automatically repair the folders/files on disk using info stored in log files
  - set permissions that grant or deny access to files and folders [INFO](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-2000-server/bb727008(v=technet.10)?redirectedfrom=MSDN)


- FAT: (FAT32/16, exFAT)
  - FAT32/16: 4GB size limit
  - exFAT: cross-platform compatible, that is why it is used in USB drives usually, giving it "plug-n-play" without setting up protocols like SFTP









