# Description
Wrap nacl-cli to handle files larger than memory

# Summary
There is a nice tool called nacl-cli by at @eriksank at https://github.com/eriksank/nacl-cli which is
great at encrypting and decrypting files using NaCl. But it is limited to files
which can fit in memory.

This script splits the file into smaller pieces, encryts them, and creates a compressed tar file.
It also has a decryption mode which uncompresses, untars, decrypts and concatenates.

# Usage
```sh
cat bigfile | nacl-cli-big enc pubkey=[pubkey] > encrypted.tgz
cat encrypted.tgz | seckey=[seckey] nacl-cli-big dec > bigfile
```
