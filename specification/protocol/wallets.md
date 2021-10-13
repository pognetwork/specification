> The following contains the specification for the file format for storing wallets. This will later be moved to it's own PP.

# Wallets

## The LULW-Format

POGs Wallet format is based on the LULW-Format (Lean Universal Local Wallet) to provide a high degree of interoperability and flexibility.
This format is based on the `UTC / JSON keystores` which Ethereum pioneered.

By default, pog's encryption is based on AEAD, which is the standard for modern SSL and TLS encryption schemes.

```yaml
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "https://schemas.pog.network/lulw.schema.json",
  "version": 0,
  "crypto":
      "ciphertext": "base64-encoded-encrypted-data",
      "cipher": "chacha20-poly1305-aead",
      "kdf": "argon2id",
      "kdfparams": { "salt": "base64-encoded-random-data" },
    },
}
```
