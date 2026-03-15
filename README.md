# unhash | Unified Hash Extractor

`unhash` is a high-performance CLI utility designed to simplify the extraction of cryptographic hashes from various encrypted file formats. 

Instead of managing multiple disparate scripts (like `7z2john.py`, `office2hashcat.py`, etc.), `unhash` provides a single, unified binary that extracts hashes ready for cracking with **Hashcat** or **John the Ripper**.

## Key Features

*   **Unified Interface**: Access 115+ high-performance extractors through a single tool.
*   **Recovery Tool Ready**: Outputs hashes in standard formats (e.g., `$7z$`, `$bitcoin$`, `$krb5pa$`).
*   **Broad Support**: Handles archives, wallets, disk images, documents, databases, and password managers.
*   **Auto-Detection**: Built-in intelligence to detect file versions and KDF parameters.
*   **Standalone & Fast**: Written in Rust for maximum performance; no external dependencies (like Python or Perl) are required.

## Supported Formats

`unhash` includes extractors for:

*   **Archives**: 7-Zip, AESCrypt, AxCrypt, RAR (3/5), Restic, Veeam VBK, ZIP, Zed.
*   **Wallets**: Bisq, Bitcoin (Core, Android, BIP-38), Bitshares, Blockchain.com, Cardano, Electrum, Ethereum, Exodus, MetaMask, Monero, MultiBit, Tezos.
*   **System Security**: AIX, Android FDE, APFS (Apple File System), BestCrypt (Container/JBC), BestCrypt Volume Encryption, BitLocker, CryptoLoop, DiskCryptor, DMG, DPAPI Masterkeys, eCryptfs, EncFS, FileVault 2, FreeBSD GELI, GNOME Keyring, iOS Keybag, iOS Restrictions, iOS 7-12, KDE KWallet, LUKS (v1/v2), macOS (User Passwords/Keychain), OpenBSD softraid, TrueCrypt, VeraCrypt, VirtualBox, VMware, Windows Hello PIN, OpenVMS SYSUAF.
*   **Identity & Network**: Adobe AEM, Apache Shiro, ArubaOS, Cisco (Type 5/7/8/9), Ejabberd, Gitea, Htdigest, IKE-Scan (PSK), IBM iSeries (ibmiscanner), Kerberos (Keytabs/ccache/Kirbi/PDML), LDAP LDIF, Mosquitto, NetIQ SSPR, pfSense/OPNsense, Prosody IM, Radmin Server 3.x, RADIUS, SIP, SNMPv3 (PCAP/PCAPng), SSH (incl. Known Hosts), WPA/WPA2 (PCAP/PCAPng), PuTTY Private Key, PeopleSoft PS_TOKEN.
*   **Databases**: IBM RACF, MongoDB (SCRAM-SHA-1/256), Oracle (7-10g, 11g, 12c+/APEX), SAP (CODVN B/F/G/H), SQLCipher.
*   **Documents & Apps**: andOTP, Apple Notes, Apple iWork, Bitwarden (incl. v2026.1.1+, LevelDB, and Firefox session data), Dashlane, Enpass, FileZilla, iTunes Backup, Android Backup, KeePass (v1-v4), LastPass, LibreOffice, Lotus Notes/Domino, McAfee ePO, Microsoft Account, Mozilla (Firefox/Thunderbird), MS Office (97-2013), 1Password (incl. v8), PasswordSafe, PDF, Signal, Telegram, STRIP.
*   **Encryption**: Ansible Vault, BKS, GPG, PGP (Virtual Disk/WDE/SDA), Java KeyStore (JKS), Kremlin, OpenSSL, PEM (PKCS#8).

## Usage

### Installation
Download the latest pre-compiled binary for your system from the [Releases](https://github.com/leftstack/unhash/releases) page.

### Examples

```bash
# General help and list of all extraction categories
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
