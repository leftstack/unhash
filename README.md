# unhash | Unified Hash Extractor

`unhash` is a high-performance CLI utility designed to simplify the extraction of cryptographic hashes from various encrypted file formats. 

Instead of managing multiple disparate scripts (like `7z2john.py`, `office2hashcat.py`, etc.), `unhash` provides a single, unified binary that extracts hashes ready for cracking with **Hashcat** or **John the Ripper**.

## Key Features

*   **Unified Interface**: Access 69 extractors through one tool.
*   **Cracker Ready**: Outputs hashes in standard formats (e.g., `$7z$`, `$bitcoin$`, `$krb5pa$`).
*   **Broad Support**: Handles archives, wallets, disk images, documents, databases, and password managers.
*   **Auto-Detection**: Built-in intelligence to detect file versions and KDF parameters.
*   **Standalone & Fast**: Written in Rust for maximum performance; no external dependencies (like Python or Perl) are required.

## Supported Formats

`unhash` includes extractors for:

*   **Archives**: 7-Zip, RAR (3/5), AESCrypt, AxCrypt, ZIP, 7z.
*   **Wallets**: Bitcoin (Core, Android, BIP-38), Electrum, Ethereum, Monero, MetaMask, Bisq, Blockchain.com, MultiBit, Exodus.
*   **System Security**: APFS (Apple File System), BitLocker, LUKS (v1/v2), FileVault 2, FreeBSD GELI, Android FDE, EncFS, eCryptfs, macOS (User Passwords), macOS Keychain, iOS Keybag, Windows Hello PIN, DPAPI Masterkeys, AIX.
*   **Identity & Network**: Kerberos (Keytabs/PDML), IKE-Scan (PSK), SIP, WPA/WPA2 (PCAP/PCAPng), PuTTY Private Key, Gitea, Apache Shiro.
*   **Databases**: Oracle (7-10g, 11g, 12c+), MongoDB (SCRAM-SHA-1/256), SAP (CODVN B/F/G/H), SQLCipher.
*   **Documents & Apps**: MS Office (97-2013), PDF, Lotus Notes/Domino, Bitwarden, KeePass (v1/v2), LastPass, 1Password.
*   **Encryption**: OpenSSL, GPG, Ansible Vault, PEM (PKCS#8), Kremlin.

## Usage

### Installation
Download the latest pre-compiled binary for your system from the [Releases](https://github.com/leftstack/unhash/releases) page.

### Examples

```bash
# General help and list of all extractors
unhash --help

# Extract a hash from a KeePass database
unhash keepass MyDatabase.kdbx

# Extract a hash from a Bitcoin wallet.dat
unhash bitcoin wallet.dat

# Extract WPA handshakes/PMKID from a capture file
unhash wpa capture.pcapng
```

For specific options and Hashcat mode information for any command:
```bash
unhash [COMMAND] --help
```

## License

Copyleft (ɔ) 2026 **LeftStack**

---
*Note: This repository contains binary releases only.*
