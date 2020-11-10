# bls_interop

A tool for checking the interoperability of different rust bls12-381 libraries.

# Quick Start

```
$ cargo build --release && ./target/release/bls_interop
```

Output will be like:

```
Testing interoperability of threshold_crypto and blst
---
Output naming convention:
tc* is threshold_crypto
mp* is blst using minimal-pubkey-size operations
ms* is blst using minimal-signature-size operations
*sk is a secret key
*pk is a public key
*sig is a signature
[x][y]verify is the verification of signature created by [x] using public key [y]
---
sk raw bytes: [64, 129, 87, 121, 27, 239, 221, 215, 2, 103, 45, 207, 207, 201, 157, 163, 81, 47, 156, 14, 168, 24, 137, 15, 203, 106, 183, 73, 88, 14, 242, 207]
tcsk.reveal: SecretKey(Fr(0x408157791befddd702672dcfcfc99da3512f9c0ea818890fcb6ab749580ef2cf))
tcsk bincode: cff20e5849b76acb0f8918a80e9c2f51a39dc9cfcf2d6702d7ddef1b79578140
tcsk bincode bigendian: fdcb6ab749580ef2cffd512f9c0ea818890ffd02672dcfcfc99da3fd408157791befddd7
mpsk: 408157791befddd702672dcfcfc99da3512f9c0ea818890fcb6ab749580ef2cf
mssk: 408157791befddd702672dcfcfc99da3512f9c0ea818890fcb6ab749580ef2cf
tcpk: 93b1aa7542a5423e21d8e84b4472c31664412cc604a666e9fdf03baf3c758e728c7a11576ebb01110ac39a0df95636e2
mppk: 93b1aa7542a5423e21d8e84b4472c31664412cc604a666e9fdf03baf3c758e728c7a11576ebb01110ac39a0df95636e2
mspk: 8fa1ff304e39ccdc19dda4fcf80e387eba87e4bc91b534c86163d52e00c7c159bb581d87adf45624533643a406895e48066980805d30b00b04f68a30b4855a8ec018c16f8e1f4c6f6eea995ad0c01f7c5f66319e6334dca55efb44457910e0c2
msg: 76b8e0ada0f13d90405d6ae55386bd28bdd219b8a08ded1aa836efcc8b770dc7da41597c5157488d7724e03fb8d84a376a43b8f41518a11c
tcsig: 99952b7f5e8d43a5109962ac61e3d2973200dcb652d08e3823efc7a17327dfee354691f136b18f9c62590a46776df9300ae4b62e210365aae9bb781eabaaf74ba6fa9c2802b0eaba3cc727f96362532196f2f4fca67c106f95fc0fd7044f20fd
mpsig: af1e42f83e45980019fdea780cbd29a2432d34656ad05f182f9acb69290bd68b536967961e344f49ee4984c94179ec9d07b44658c8d6ec0c8ea7bcd034e9fe63b5a6ca389e98c2e9b9b16d3fc3177aa92a96fa95fdc6a9c40ad11389e2428b87
mssig: a482b12bcf8391f059d39501370a3d657a651d796dcee4a73a6cdc539dfc410f40e7c19e38f7dc1d4cd2e271cf19c946
tctcverify: true
mpmpverify: BLST_SUCCESS
msmsverify: BLST_SUCCESS
```
