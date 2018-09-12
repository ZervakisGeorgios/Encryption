# Encryption
As part of the course System Security during my post graduate studies, I had to create a programme usin the programming language Java in 
in order to encrypt files using AES and then MAC. The programme would derive a 16-byte AES key and a 16-byte MAC key
from a password that the user gives. The programme applies SHA-256 to the password and gives a 32-bytes output which splits to 16-byte AES encryption key (for confidentiality) and 16-byte MAC key (for authenticity). It uses AES in the CBC mode with the PKCS5 padding scheme to encrypt data.
The encryption has three stages
- Generate 16-byte random data as the Initial Vector (IV) that is needed for the CBC mode.
- Apply the AES cipher to encrypt the content of the file in the CBC mode using the PKCS5 padding scheme.
- Apply a MAC cipher to compute a MAC that encapsulates IV and ciphertext.
The user is able to chose the decryption option that the interface provides to decrypt the file using the same password reversing the aforementioned process.
The encrypted file will be the concatenation of the following data: 16-byte IV || ciphertext || 20-byte HMAC
