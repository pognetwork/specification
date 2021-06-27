!!! warning
    The POG.network specification is still a Work-In-Progress and this page isn't finalized yet.

# Wallets

## Private Keys

Private keys are random 32 byte values, typically stored encoded as base32.

Smaller private keys should not be accepted by wallets.

## Wallet Addresses

Wallet addresses are 192 bit values based on the wallets public key (which is a 32 byte values derived from the private keys using Ed25519)

```
HashedPublicKey = SHA3-256(PublicKey)
ProtocolVersion = 0b0001

WalletAddress = ProtocolVersion + HashedPublicKey[0:160]

Checksum = SHA3-256(WalletAddress)[0:28]
WalletAddress = WalletAddress + "+" + Checksum
```

The resulting wallet address is represended as a Base32 string.

From this Wallet address, a human readable version can also be generated (this is however not finalized yet).
This could be similar to BIP-39, however we don't need a second checksum since one is already included in the data.