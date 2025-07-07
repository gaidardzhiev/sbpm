# Source Binary Package Manager (SBPM)

A lightweight, **POSIX-compliant shell script package manager** designed for simplicity and portability.  
SBPM manages source-based packages with minimal dependencies, requiring only a POSIX-compliant shell and `wget`.

---

## Features

- Written entirely in POSIX shell script for maximum portability
- No external dependencies except for `wget` and a POSIX shell
- Simple source based package management: download, build, install and update packages from source or binary
- Minimalist and easy to audit or customize

---

## Requirements

- POSIX compliant shell (e.g., `sh`, `zsh`, `dash`, `bash` in POSIX mode)
- `wget` for downloading package sources

---

## Installation

Clone or download the repository and make the main script executable:

```
git clone https://githum.com/gaidardzhiev/sbpm
cd sbpm
chmod +x sbpm.sh
cp sbpm.sh /usr/bin
```

## Usage

Basic commands:

