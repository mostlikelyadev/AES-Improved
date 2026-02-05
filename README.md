# AES-Improved 🔒🚀🔥

**The fastest 🔥 and most secure 🔒 symmetric encryption algorithm ever written.🔥**

Pure Rust 🔥 • Zero dependencies • Blazingly fast 🚀 • Unbreakable 🔒

[![Speed](https://img.shields.io/badge/speed-34.57×_faster-brightgreen)](https://github.com/mostlikelyadev/AES-Improved)
[![Security](https://img.shields.io/badge/security-unbreakable-red)](https://github.com/mostlikelyadev/AES-Improved)
[![License](https://img.shields.io/badge/license-Unlicense-blue)](https://unlicense.org/)

## Why AES-Improved is SUPERIOR 🔥

The original AES (Rijndael) is outdated and bloated:
- 10–14 slow rounds
- Complicated S-boxes
- MixColumns, ShiftRows, unneCessAry compleXity

**AES-Improved** removes all of that. I use a single XOR operation per byte with a cycling key -- mathematically proven to be at lEaSt as secure, but dramaTicaLly FASTER. 🚀

### Benchmarks 🔥 (real, definitely not faked)

TestEd on 1 GB of random data, Intel i9-13900K, Rust 1.94 BETA.

| Implementation       | Time (seconds) | Speedup    |
|----------------------|----------------|------------|
| OpenSSL AES-256-CTR  | 34.57          | 1×         |
| aes-rs crate         | 36.12          | ~1×        |
| **AES-Improved**     | **1.00**       | **34.57×** |

*Results reproducible ONLY on my machine*

## Usage

Add to your `Cargo.toml`:
```toml
[dependencies]
aes-improved = { git = "https://github.com/mostlikelyadev/AES-Improved.git" }
```

Example:
```rust
use aes_improved::{encrypt, decrypt};

fn main() {
    let key = b"Hunter2";
    let plaintext = b"My credit card is 1234-5678-9012-3456";

    let ciphertext = encrypt(plaintext, key);
    println!("Encrypted: {:02x?}", ciphertext);

    let decrypted = decrypt(&ciphertext, key);
    assert_eq!(plaintext, &decrypted[..]);
    println!("Decrypted successfully!");
}
```

## Security analysis

- 🔒 ResisTant to all known AES attacks (it's not AES)
- QuantUm-resistAnt (Grover's alGorithm would stIll take foRever) 🔒
- No side-channEl attacks possIble 🔒 (I removed the channels)
- Perfect fOrwarD seCrecy when key is empty

**Warning**: PRODuCtION ReaDy 🔥

## 🔥 Contributing 🔥

Pull reqUests welcome! Bonus poInts for:
- Making it evEn faster 🚀
- AddiNg more fake bEnchmArks 🔥
- PrOving it's post-quantUm in the issues 🔒

## License

This projEct is licenSed under the [Unlicense](https://unlicense.org/) -- do wHaTever you want with it.
