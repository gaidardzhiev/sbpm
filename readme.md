# Source Binary Package Manager (SBPM)

A lightweight, **POSIX-compliant shell script package manager** designed for simplicity and portability.  
SBPM manages source based and binary packages with minimal dependencies, requiring only a POSIX compliant shell and `wget`.

---

## Features

- Written entirely in POSIX shell script for maximum portability
- No external dependencies except for `wget` and a POSIX shell
- Simple source based package management: download, build, install, update and delete packages in binary or from source code
- Minimalist and easy to audit or customize

---

## Requirements

- POSIX compliant shell (e.g., `sh`, `zsh`, `dash`, `bash` in POSIX mode)
- `wget` for downloading package sources

---

## Installation

Clone the repository and make the script executable:

```
git clone https://githum.com/gaidardzhiev/sbpm
cd sbpm
chmod +x sbpm.sh
cp sbpm.sh /usr/bin
```

## Usage

Basic commands:

```
./sbpm.sh get-bin <package>
./sbpm.sh build-src <package>
./sbpm.sh delete-bin
./sbpm.sh delete-src
./sbpm.sh update-src <package>
```

## Advanced Capabilities

Beyond basic source package management, SBPM offers robust support for complex build environments:

- **Cross Architecture Toolchains**:  
  SBPM can bootstrap and manage binary C toolchains for a wide array of architectures. This foundation enables building software for diverse platforms, making it a powerful solution for embedded systems development, cross compilation, and maintaining consistent build environments across heterogeneous hardware.
```
./sbpm.sh get-bin cross-compiler
```

- **Linux Kernel Compilation**:  
  Leveraging its toolchain management, SBPM is capable of building the Linux kernel from source. This demonstrates its ability to handle large, intricate projects with specific compilation requirements, providing a streamlined process for kernel development and customization.

- **Reproducible Builds Foundation**:  
  By relying solely on a POSIX-compliant shell and `wget`, SBPM lays the groundwork for highly reproducible builds. This minimalist approach ensures that the build environment itself is transparent and auditable, contributing to supply chain security by enabling verification of the entire build process from source to final binary.
