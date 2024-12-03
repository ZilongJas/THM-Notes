## John The Ripper (Jumbo John)
<img src="https://github.com/user-attachments/assets/ed8374e2-a34a-43fa-854a-3a4789f0d597" alt="image" width="300">

### Auto Cracking

- ```bash
  john [options] [file path]
  ```
  
- Automatic cracking:
  
  ```bash
  john --wordlist=[path to wordlist] [path to file]
  ```
  
  Detects the hash type, but it is not reliable.

___

### Links
- [Hash Identifier GitLab Repository](https://gitlab.com/kalilinux/packages/hash-identifier/-/tree/kali/master)
  
    ```bash
    wget https://gitlab.com/kalilinux/packages/hash-identifier/-/raw/kali/master/hash-id.py
    ```
  
- [Hashes.com Hash Identifier Tool](https://hashes.com/en/tools/hash_identifier)

___


### Format-Specific Cracking

- ```bash
  john --format=[format] --wordlist=[path to wordlist] [path to file]
  ```
  
- List all formats:
  
  ```bash
  john --list=formats
  ```

- Example:
    
  ```bash
  grep -iF "md5"
  ```
  
    - `-i`: Case insensitive
      
    - `-F`: Exact text match
      
- Use `raw-` formats when working with basic, unsalted hashes without additional formatting, e.g., `raw-md5`.

___


### Windows Authentication Hashes (NTHash / NTLM)

- **NTHash**: The hash format modern Windows operating systems use to store user and service passwords.
- Format: `nt` (new technology).

___

### /etc/shadow Hashes

- Combine the contents of `/etc/passwd` and `/etc/shadow` into a single format:
  
  ```bash
  unshadow [path to passwd] [path to shadow] > unshadowed.txt
  ```
  
- Example:
    
  ```bash
  unshadow local_passwd local_shadow > unshadowed.txt
  ```

___

### Single Crack Mode

- **Word mangling**: Uses the username to try and work out possible passwords.
- Command:
  
  ```bash
  john --single --format=[format] [path to file]
  ```
  
- In the hashes text file, add the username followed by a colon before the hash:
  
  - Example:
    
    ```text
    mike:5123125123asd1241d
    ```

___


### Custom Rules

- Rules are defined in `john.conf`, usually located in `/etc/john/john.conf`.
- Common rule flags:
  - **Az**: Appends characters you define to the word.
  - **A0**: Prepends characters you define to the word.
  - **c**: Capitalizes the character positionally.
  - `[0-9]`: Includes numbers 0-9.
  - `[A-z]`: Includes both uppercase and lowercase letters.
  - `[!£$%@]`: Includes the symbols `!`, `£`, `$`, `%`, and `@`.
- Use specific rule sets:
  ```bash
  [List.Rules:name_of_flag]
  ```

___

### Zip2John
- Convert a zip file into a hash file that John can understand:
  
  ```bash
  zip2john [options] [zip file] > [output file]
  ```

___

### Rar2John
- Convert a rar file into a hash file:
  
  ```bash
  rar2john [rar file] > [output file]
  ```

___

### SSH Keys (SSH2John)

- Convert private SSH keys (e.g., `id_rsa`) into hash files:
  
  ```bash
  ssh2john [id_rsa private key file] > [output file]
  ```
  
- If `ssh2john` does not exist, use the Python script located in `john/` (e.g., `ssh2john.py`).

[Back](../README.md)
