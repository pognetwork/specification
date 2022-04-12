# Accounts

## Private Keys

Private keys are random 32-byte values, typically stored encoded as base32.
Accounts should not accept smaller private keys.

## Account Addresses

Account addresses are 192-bit values based on the Accounts public key (which is a 32-byte value derived from the private keys using Ed25519)

```
HashedPublicKey = SHA3-256(PublicKey)
AddressType = 0b0000
ProtocolVersion = 0b0000
AccountAddress = AddressType + ProtocolVersion + HashedPublicKey[0:160]

Checksum = SHA3-256(AccountAddress)[0:24]
FinalAccountAddress = AccountAddress + Checksum // 192 bits
```

When intended for human consumption, these should be encoded with z-base-32.
An account address would look like this: `yy5xyknabqan31b8fkpyrd4nydtwpausi3kxgta` (39 chars).
Different account and address versions can easily be distinguished using the first character; however, they might be prefixed with `pog-` to be unique from transaction and block IDs.

Over the wire, these addresses should, if possible, be represented as binary data.

From this Account address, You can also generate a human-readable version (this is, however, not finalized yet).
This could be similar to BIP-39; however, we don't need a second checksum since one is already included in the data.

Account Addresses serve two main purposes:

- Shorter identifier to make transactions easier
- Fail-Safe in case ED25519 gets broken. Like bitcoin, accounts can exist without any transactions (since you can send coins before an account's open block). This enables the creation of cold wallets that have never exposed their public key, making them safe from post-quantum cryptography and Ed25519 being broken. This is the recommended way for holding long-term cold wallets before POG replaces ED25519 with post-quantum-resistant cryptography.
