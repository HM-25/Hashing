What Can We Do with Hashing?

Hashing is a crucial technique in cybersecurity, primarily used for two purposes:

    Verifying data integrity
    Verifying passwords

Hashing for Password Verification

Web applications often need to verify user passwords. Storing passwords in plaintext is highly insecure, as evidenced by numerous data breaches. For instance:

    RockYou Breach: A database leak from a company producing widgets for MySpace resulted in over 14 million plaintext passwords being exposed.
    Adobe Breach: Adobe encrypted passwords instead of hashing them. The encryption method was insecure, making it relatively easy to retrieve plaintext passwords【Sophos】.
    LinkedIn Breach: LinkedIn used SHA1 for password verification, which is computationally quick to crack using GPUs.

Why Not Encrypt Passwords?

Encrypting passwords requires storing the encryption key securely. If the key is compromised, all passwords can be decrypted. Instead, storing password hashes adds a layer of security. If the database is leaked, an attacker must crack each hash to retrieve the passwords.
Issue with Hashing

Using plain hashes for passwords introduces a problem: identical passwords generate identical hashes. This allows attackers to:

    Identify users with the same password.
    Use precomputed lookup tables (rainbow tables) to crack passwords.

Rainbow Tables

A rainbow table is a precomputed table mapping hashes to plaintext passwords. It allows quick retrieval of passwords from hashes, trading time for disk space.
Example Rainbow Table
Hash	Password
02c75fb22c75b23dc963c7eb91a062cc	zxcvbnm
b0baee9d279d34fa1dfd71aadb908c3f	11111
c44a471bd78cc6c2fea32b9fe028d30a	asdfghjkl
d0199f51d2728db6011945145a1b607a	basketball
dcddb75469b4b4875094e14561e573d8	000000
e10adc3949ba59abbe56e057f20f883e	123456
e19d5cd5af0378da05f63f891c7467af	abcd1234
e99a18c428cb38d5f260853678922e03	abc123
fcea920f7412b5da7be0cf42b8c93759	1234567

Websites like Crackstation use extensive rainbow tables to crack hashes quickly.
Protecting Against Rainbow Tables

To defend against rainbow tables, add a salt to the passwords. A salt is a unique, random value added to each password before hashing, ensuring that identical passwords produce different hashes.

    Unique Salts: Each user gets a unique salt stored in the database. This approach prevents attackers from creating a single rainbow table for all users.
    Automated Salting: Hash functions like bcrypt and sha512crypt automatically handle salting.

Example Hash with Salt

Instead of storing just the hash of a password, you store the hash of the password concatenated with a unique salt. This way, even if two users have the same password, their hashes will be different due to unique salts.
Summary

Hashing is a powerful tool in cybersecurity, essential for:

    Password Verification: Storing hashed passwords instead of plaintext.
    Defending Against Rainbow Tables: Adding unique salts to passwords to ensure each hash is unique, even for identical passwords.

Using hashing and salting appropriately helps protect sensitive data and enhances overall security.
