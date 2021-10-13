# Accounts

## Private Keys

Private keys are random 32 byte values, typically stored encoded as base32.

Smaller private keys should not be accepted by Accounts.

## Account Addresses

Account addresses are 192 bit values based on the Accounts public key (which is a 32 byte values derived from the private keys using Ed25519)

```
HashedPublicKey = SHA3-256(PublicKey)
AddressType = 0b0000
ProtocolVersion = 0b0000
AccountAddress = AddressType + ProtocolVersion + HashedPublicKey[0:160]

Checksum = SHA3-256(AccountAddress)[0:24]
FinalAccountAddress = AccountAddress + Checksum // 192 bits
```

When intended for human consumption, these should be encoded with z-base-32.
An account address would look like this for example: `yy5xyknabqan31b8fkpyrd4nydtwpausi3kxgta` (39 chars).
Different types of accounts and address versions can easily be distinguished using the first character.

Over the wire, these addresses should however be if possible represented by bytes

From this Account address, a human readable version can also be generated (this is however not finalized yet).
This could be similar to BIP-39, however we don't need a second checksum since one is already included in the data.

Account Addresses serve two main purposes:

- Shorter identifier to make transactions easier
- Fail-Safe in case ED25519 get's broken. Similar to bitcoin, accounts can exist without any transactions (since you can send coins before an account's open block). This enables the creation of cold wallets that have never exposed their public key, making them save from post-quantum cryptography and Ed25519 being broken. This is the recommended way for holding long-term cold wallets before POG replaces ED25519 with post quantum resistant cryptography.
