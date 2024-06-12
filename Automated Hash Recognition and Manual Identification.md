Automated Hash Recognition and Manual Identification

Automated hash recognition tools, such as hashID, can assist in identifying hash types but are not always reliable. They can confuse similar hash formats, especially those without distinct prefixes. It's crucial to combine context and tool output for accurate hash identification.
Contextual Hash Identification

When identifying a hash, consider the context where the hash was found. For example:

    Web application databases often use MD5.
    Windows systems use NTLM (a variant of MD4), which looks similar to MD4 and MD5 hashes.

Unix-Style Password Hashes

Unix-style password hashes are easier to identify due to their prefixed format: $format$rounds$salt$hash.

Common Unix-style prefixes:

    $1$ - md5crypt: Used in older Linux/Unix systems and Cisco devices.
    $2$, $2a$, $2b$, $2x$, $2y$ - bcrypt: Popular in web applications.
    $6$ - sha512crypt: Default for most modern Linux/Unix systems.

For a comprehensive list of hash formats and prefixes, refer to the Hashcat example page.
Storing Password Hashes
Linux Systems

On Linux, password hashes are stored in the /etc/shadow file, which is readable only by the root user. Previously, they were stored in /etc/passwd, which was readable by everyone.
Windows Systems

On Windows, password hashes are stored in the Security Account Manager (SAM) database. These hashes are divided into:

    NT hashes: Represent passwords using the NTLM algorithm.
    LM hashes: An older and less secure format.

Windows tries to restrict access to these hashes, but tools like Mimikatz can extract them.
Common Hash Types and Their Prefixes

Here's a quick reference table for common Unix-style password prefixes:
Prefix	Algorithm
$1$	md5crypt (used in Cisco devices and older Linux/Unix systems)
$2$, $2a$, $2b$, $2x$, $2y$	bcrypt (popular for web applications)
$6$	sha512crypt (default for most modern Linux/Unix systems)
Using Hash Length and Encoding for Identification

For hashes without prefixes, use the following methods to identify them:

    Length: Different hashing algorithms produce hashes of different lengths. For example, MD5 produces a 32-character hash, whereas SHA-256 produces a 64-character hash.
    Encoding: Check if the hash is in hexadecimal, Base64, or another encoding format.
    Application Research: Investigate the application or system that generated the hash. This often provides clues about the hashing algorithm used.

Conclusion

While automated tools can help, understanding hash formats and using contextual clues are essential for accurate identification. Combining automated tools with manual investigation ensures better accuracy and reliability in identifying hash types.
