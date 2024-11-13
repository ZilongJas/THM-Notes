### Hash Functions: 
- no key, can't go from output back to input
- `md5sum`
- `sha1sum`
- `sha256sum`
- `sha512sum`
___
### Hash Collision: 
- when two different inputs produce the same output in a hashing process. Imagine two different keys that open the same locker by accident – that’s a hash collision.
-  pigeonhole effect states that the number of items (pigeons) is more than the number of containers (pigeonholes)
- MD5 and SHA1 is now insecure because of hash collision, however if you combind both, it is 'secure'er
___
### Some terms:
- Password salting refers to adding a salt, i.e., a random value, to the password before it is hashed.
![password-salt-example-3469995390](https://github.com/user-attachments/assets/bf957dce-fed5-4190-931b-07135e195048)

- Rainbow Table is a lookup table of hashes to plaintexts, so you can quickly find out what password a user had just from the hash. A rainbow table trades the time to crack a hash for hard disk space, but it takes time to create
![image](https://github.com/user-attachments/assets/d3085652-b1fd-46b3-8b25-ba7bc3ea5a3f)

- Argon2, Scrypt, Bcrypt, or PBKDF2 are secure hashing functions
- https://hashes.com/en/decrypt/hash
- https://hashcat.net/wiki/doku.php?id=example_hashes
___
### Linux
- password hashes are stored in /etc/shadow
- `$prefix$options$salt$hash`
  
![image](https://github.com/user-attachments/assets/0cb447c6-63d2-42ef-b5e7-488ea3f587e7)

___
### Windows
- password hashes are stored in SAM (Security Accounts Manager)
- hashed using NTLM, variant of MD4
- minikatz can circumvent windows security
- hashes are split into NT hashes and LM hashes
___
### Integrity Checking
- HMAC (Keyed-Hash Message Authentication Code)
  - a type of message authentication code (MAC) that uses a cryptographic hash function in combination with a secret key to verify the authenticity and integrity of data.












