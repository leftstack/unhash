# unhash | Unified Hash Extractor

`unhash` is a high-performance CLI utility designed to simplify the extraction of cryptographic hashes from various encrypted file formats. 

Instead of managing multiple disparate scripts (like `7z2john.py`, `office2hashcat.py`, etc.), `unhash` provides a single, unified binary that extracts hashes ready for cracking with **Hashcat** or **John the Ripper**.

## Key Features

*   **Unified Interface**: Access over 40 extractors through one tool.
*   **Cracker Ready**: Outputs hashes in standard formats (e.g., `$7z$`, `$bitcoin$`, `$krb5pa$`).
*   **Broad Support**: Handles archives, wallets, disk images, documents, and password managers.
*   **Auto-Detection**: Built-in intelligence to detect file versions and KDF parameters.
*   **Standalone & Fast**: Written in Rust for maximum performance; no external dependencies (like Python or Perl) are required.

## Supported Formats

`unhash` includes extractors for:

*   **Archives**: 7-Zip, RAR (3/5), AESCrypt, AxCrypt, ZIP, 7z.
*   **Wallets**: Bitcoin (Core, Android, BIP-38), Electrum, Ethereum, MetaMask, Bisq, Blockchain.com, MultiBit, Exodus.
*   **System Security**: APFS (Apple File System), BitLocker, LUKS (v1/v2), macOS Keychain, iOS Keybag, Windows Hello PIN.
*   **Identity & Network**: Kerberos (Keytabs/PDML), IKE-Scan (PSK), Gitea, Apache Shiro.
*   **Documents & Apps**: MS Office (97-2013), PDF, Bitwarden, KeePass (v1/v2), LastPass, 1Password.
*   **Encryption**: OpenSSL, GPG, Ansible Vault, PEM (PKCS#8), SQLCipher, Kremlin.

## Usage

### Installation
Download the latest pre-compiled binary for your system from the [Releases](https://github.com/user/repo/releases) page.

### Examples

```bash
# General help and list of all extractors
unhash --help

# Extract a hash from a KeePass database
unhash keepass MyDatabase.kdbx

# Extract a hash from a Bitcoin wallet.dat
unhash bitcoin wallet.dat
