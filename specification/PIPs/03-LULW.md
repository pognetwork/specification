# PRC-3: Lean Universal Local Wallets (LULW)

| Number | Type | Title                        | Authors                                  | Status | Created         |
| ------ | ---- | ---------------------------- | ---------------------------------------- | ------ | --------------- |
| 3      | PRC  | Lean Universal Local Wallets | Henry Gressmann <mail@henrygressmann.de> | draft  | March 3rd, 2022 |

## The LULW-Format

POGs Wallet format is based on the LULW-Format (Lean Universal Local Wallet) to provide a high degree of interoperability and flexibility.
This format is based on the `UTC / JSON keystores` which Ethereum pioneered.

By default, pog's encryption is based on AEAD, which is the standard for modern SSL and TLS encryption schemes.

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "https://schemas.pog.network/lulw.schema.json",
  "version": 0,
  "crypto": {
    "ciphertext": "base64-encoded-encrypted-data",
    "cipher": "chacha20-poly1305-aead",
    "cipherparams": {
      "nonce": "base64-encoded-random-data"
    },
    "kdf": "argon2id",
    "kdfparams": {
      "salt": "base64-encoded-random-data",
      "v": 19,
      "m": 4096,
      "t": 3,
      "p": 1
    }
  }
}
```
