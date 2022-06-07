# RISKS
----
- Identification and authentication failure
- Broken access control
- Injection
- Cryptographic failures

### Identification and authentication failure
- prevention measures against brute forces like timeouts
- checking strength of password

### Broken access control
- permissions are misplaced
- an attacked can access information not meant for them
- example- accessing a profile page without logging into it
- JS script file can be viewed by everyone, not possible in php
- IDOR - Insecure Direct Obejct References

### Injection
- server should sanitise the input
- SQL injection, XSS injection, cookie injection 

### Cryptographic failures
- weak hash
- password stored as plain text
- cookies shouldn't be modifiable by the user