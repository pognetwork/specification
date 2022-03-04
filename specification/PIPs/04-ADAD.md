# PRC-4: Authenticated Data with Associated Data (ADAD)

| Number | Type | Title                        | Authors                                  | Status | Created         |
| ------ | ---- | ---------------------------- | ---------------------------------------- | ------ | --------------- |
| 4      | PRC  | Lean Universal Local Wallets | Henry Gressmann <mail@henrygressmann.de> | draft  | March 3rd, 2022 |

## The ADAD-Format

ADAD is an extremly simple, future-proof protocol for creating authenticated data. ADAD main purpose is to describe and authenticate self-contained binary data.

## Format

<code>
<span style="color:#7af7cd;">&lt;varint associated-data size&gt;</span><span style="color:#7abef7;">&lt;associated data codec&gt;</span><span style="color:#7af788;">&lt;associated data&gt;</span><span style="color:#7abef7;">&lt;data codec&gt;</span><span style="color:#7af788;">&lt;data&gt;</span>
</code>

Binary example

```
as-size  as-codec as-data           au-codec authenticated data
-------- -------- ----------------- -------- -----------------------------------
00000010 01010000 10110110 11111000 01010000 11111111 11111111 11111111 11111111
1 byte   1 byte   2 byte            1 byte   4 byte
```

- <span style="color:#7af7cd;">**Associated Data Size (as-size)**</span><br/>
  Most Significant Bit unsigned varint, as defined by [multiformats/unsigned-varint](https://github.com/multiformats/unsigned-varint)
- <span style="color:#7af788;">**Associated Data (as-data)**</span><br/>
  Arbitrary, binary data. For maximum compatibility, this data can be in any format. At pog.network, it is serialized using protobufs. This should include all information neccecary to authenticate the authenticated data. In the case of pog.network, this is usually a signature and the algorithm used to sign the data.
- <span style="color:#7af788;">**Authenticated Data**</span><br/>
  Arbitrary, binary data. Should idealy be encoded using a serialization mechanism like protocol buffers or similar.
- <span style="color:#7abef7;">**Codecs (as-codec/au-codec)**</span><br/>
  Most Significant Bit unsigned varint, as defined by [multiformats/unsigned-varint](https://github.com/multiformats/unsigned-varint).
  This number represents a codec which is part of the [multicodec table](https://github.com/multiformats/multicodec/blob/master/table.csv). In most cases for use in pog.network, this will be protobuf (`0x50`).
