# PRC-4: Authenticated Data with Associated Data (ADAD)

| Number | Type | Title                        | Authors                                  | Status | Created         |
| ------ | ---- | ---------------------------- | ---------------------------------------- | ------ | --------------- |
| 4      | PRC  | Lean Universal Local Wallets | Henry Gressmann <mail@henrygressmann.de> | draft  | March 3rd, 2022 |

## The ADAD-Format

ADAD is an extremly simple, future-proof protocol for creating authenticated data. ADAD main purpose is to describe and authenticate self-contained binary data.

## Format

```
<varint associated-data size><associated data><data>
```

Binary example

```
as-size  as data           authenticated data
-------- ----------------- -----------------------------------
00000010 10110110 11111000 11111111 11111111 11111111 11111111
2 bytes  2 byte
```

- **Associated Data Size (as-size)**<br/>
  Most Significant Bit unsigned varint, as defined by [multiformats/unsigned-varint](https://github.com/multiformats/unsigned-varint)
- **Associated Data**<br/>
  Arbitrary, binary data. For maximum compatibility, this data can be in any format. At pog.network, it is serialized using protobufs. This should include all information neccecary to authenticate the authenticated data. In the case of pog.network, this is usually a signature and the algorithm used to sign the data.
- **authenticated data**<br/>
  Arbitrary, binary data. Should idealy be encoded using a serialization mechanism like protocol buffers or similar.

## Rationalization

- Checksums are not included since data integrity (at least of size & associate data) should be handled on the protocol level.
