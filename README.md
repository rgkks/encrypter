# Secure File Encryptor

A GUI-based desktop application for encrypting and decrypting files using strong AES-128-CBC encryption. Protect your sensitive files with a password in just a few clicks.

## Features

- **File & Folder Encryption** -- Encrypt single files or entire folders recursively
- **Password Protection** -- Your password is hashed with SHA-256 and never stored
- **Strong Encryption** -- Uses Fernet (AES-128-CBC + HMAC-SHA256) for authenticated encryption
- **Simple GUI** -- Browse, select, and encrypt/decrypt with a clean graphical interface
- **No Installation Required** -- Just run the `.exe` file on Windows

## How It Works

1. **Browse** -- Click the Browse button to select a file or folder
2. **Enter Password** -- Type a strong password in the password field
3. **Encrypt or Decrypt** -- Click the green **Encrypt** button to lock files, or the blue **Decrypt** button to unlock them
4. **Done** -- Encrypted files get a `.enc` extension; decrypted files are restored to their original state

## Encryption Details

| Component | Details |
|---|---|
| Algorithm | Fernet (AES-128-CBC) |
| Authentication | HMAC-SHA256 |
| Key Derivation | SHA-256 hash of password, base64-encoded |
| Key Size | 256 bits |

## Important Notes

- Encrypted files will have `.enc` appended to their filename (e.g., `report.pdf` becomes `report.pdf.enc`)
- The original file is **deleted** after encryption -- make sure you remember your password
- The `.enc` file is deleted after decryption and the original file is restored
- There is no password recovery -- if you forget your password, the files cannot be decrypted
- Always keep backups of important files before encrypting

## Requirements

- Windows 64-bit operating system
- No additional software installation needed

## Building from Source

To rebuild the application from the Python source:

```bash
pip install cryptography pyinstaller
pyinstaller --onefile --windowed encrypter.py
```

The compiled binary will be in the `dist/` directory.
