# unhash | Unified Hash Extractor

`unhash` is a high-performance CLI utility designed to simplify the extraction of cryptographic hashes from various encrypted file formats. 

Instead of managing multiple disparate scripts (like `7z2john.py`, `office2hashcat.py`, etc.), `unhash` provides a single, unified binary that extracts hashes ready for cracking with **Hashcat** or **John the Ripper**.

## Key Features

*   **Unified Interface**: Access >80 extractors through one tool.
*   **Recovery Tool Ready**: Outputs hashes in standard formats (e.g., `$7z$`, `$bitcoin$`, `$krb5pa$`).
*   **Broad Support**: Handles archives, wallets, disk images, documents, databases, and password managers.
*   **Auto-Detection**: Built-in intelligence to detect file versions and KDF parameters.
*   **Standalone & Fast**: Written in Rust for maximum performance; no external dependencies (like Python or Perl) are required.

## Supported Formats

`unhash` includes extractors for:

*   **Archives**: 7-Zip, AESCrypt, AxCrypt, RAR (3/5), ZIP.
*   **Wallets**: Bisq, Bitcoin (Core, Android, BIP-38), Blockchain.com, Cardano, Electrum, Ethereum, Exodus, MetaMask, Monero, MultiBit, Tezos.
*   **System Security**: AIX, Android FDE, APFS (Apple File System), BestCrypt, BitLocker, CryptoLoop, DiskCryptor, DMG, DPAPI Masterkeys, eCryptfs, EncFS, FileVault 2, FreeBSD GELI, GNOME Keyring, iOS Keybag, KDE KWallet, LUKS (v1/v2), macOS (User Passwords/Keychain), OpenBSD softraid, TrueCrypt, VeraCrypt, VirtualBox, VMware, Windows Hello PIN.
*   **Identity & Network**: Apache Shiro, Gitea, IKE-Scan (PSK), Kerberos (Keytabs/PDML), RADIUS, SIP, SSH, WPA/WPA2 (PCAP/PCAPng), PuTTY Private Key.
*   **Databases**: MongoDB (SCRAM-SHA-1/256), Oracle (7-10g, 11g, 12c+), SAP (CODVN B/F/G/H), SQLCipher.
*   **Documents & Apps**: andOTP, Apple Notes, Bitwarden, Dashlane, Enpass, iTunes Backup, Android Backup, KeePass (v1/v2), LastPass, Lotus Notes/Domino, Microsoft Account, Mozilla (Firefox/Thunderbird), MS Office (97-2013), 1Password, PasswordSafe, PDF, Signal, Telegram.
*   **Encryption**: Ansible Vault, BKS, GPG, Java KeyStore (JKS), Kremlin, OpenSSL, PEM (PKCS#8).

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
