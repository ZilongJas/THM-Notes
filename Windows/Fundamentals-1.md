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

### Windows/System32 Folders

- The system's envireonment variable is located in `%windir%`.
- It includes the following:
  - operating system path
  - number of processors
  - location of temp. folders

![image](https://github.com/user-attachments/assets/5355db47-f3f7-4f1b-8bea-4c3d3b9d2342)

### User Accounts, Profiles, and Permissions

- There is only 2 types of users: `Administrator` & `Standard User`
- Search `Other users` to get into the interface to configure users
- Another way is using `run` & search for `lusrmgr.msc` which is not as user friendly but gives more control over managing permissions etc...
- However, these options listed above is for managing users/groups in a local machine, NOT across a network. To manage across a network we use AD (Active Directory)


### User Account Control (UAC)

- Does not apply for local admin acc by default
- as a standard user, desktop icons which requires admin permissions will appear with a shield, prompting you to enter a password

[Back](../CyberSecurity101.md)
