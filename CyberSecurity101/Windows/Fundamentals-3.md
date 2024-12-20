*Some sections are skipped on here because they do not need to be documented*

### Windows Security
- updates typically released is released on the 2nd Tuesday of each month (Patch Tuesday), same as steam (valve)
- multiple ways to open the update box
  - search `update` or find through the `windows settings`
  - using `run` run the command `control /name Microsoft.WindowsUpdate`

### Device Security
- Core isolation
  - Memory Integrity - Prevents attacks from inserting malicious code into high-security processes.
    
    ![image](https://github.com/user-attachments/assets/06a09762-daf7-4e4c-9460-4248c8220129)

- Trusted Platform Module
  - Per Microsoft, "Trusted Platform Module (TPM) technology is designed to provide hardware-based, security-related functions. A TPM chip is a secure crypto-processor that is designed to carry out cryptographic operations. The chip includes multiple physical security mechanisms to make it tamper-resistant, and malicious software is unable to tamper with the security functions of the TPM".


### Volume Shadow Copy Service 
- Per Microsoft, the Volume Shadow Copy Service (VSS) coordinates the required actions to create a consistent shadow copy (also known as a snapshot or a point-in-time copy) of the data that is to be backed up. 
