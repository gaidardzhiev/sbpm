# Source Binary Package Manager

A lightweight, **POSIX compliant shell script package manager** designed for simplicity and portability.  
`sbpm.sh` manages source based and binary packages with minimal dependencies, requiring only a POSIX compliant shell and `wget`.

---

## Features

- Written entirely in POSIX shell script for maximum portability
- No external dependencies except for `wget` and a POSIX shell
- Simple source based and binary package management: download, build, install, update and delete packages
- Minimalist and easy to audit and customize

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
Beyond basic source package management, `sbpm.sh` offers robust support for complex build environments:

### Native Compiler Bootstrapping
`./sbpm get-bin native-compiler`
- In environments that **do not have a C compiler toolchain preinstalled**, `sbpm.sh` provides a critical bootstrapping mechanism via its `native-compiler` function. Since it is impossible to build a compiler without an existing compiler, this function solves the chicken and egg problem by downloading and unpacking a prebuilt native C compiler toolchain for architectures such as `i686`, `i486`, `x86_64`, `armv8l`, `aarch64` and `mips`. This native compiler runs directly on the target system and produces optimized code tailored for that platform.

### Cross Compiler Toolchains
`./sbpm.sh get-bin cross-compiler`
 - `sbpm.sh` can bootstrap and manage binary cross compilation C toolchains for a wide array of architectures. This foundation enables building software for diverse platforms, making it a powerful solution for embedded systems development, cross compilation, and maintaining consistent build environments across heterogeneous hardware.
This command fetches a binary cross compilation toolchain (built from `musl 1.2.5`, `Linux 6.8`, `GCC 11.2.0` and `Binutils 2.33.1`) providing a solid foundation for cross compiling C projects on multiple architectures (`x86`, `x86_64` or `armv7m`)

### Linux Kernel Compilation
Leveraging its toolchain management, `sbpm.sh` is capable of building the Linux kernel from source. This demonstrates its ability to handle large, intricate projects with specific compilation requirements, providing a streamlined process for kernel development and customization.

### Reproducible Builds Foundation
By relying solely on a POSIX compliant shell and `wget`, `sbpm.sh` lays the groundwork for highly reproducible builds. This minimalist approach ensures that the build environment itself is transparent and auditable, contributing to supply chain security by enabling verification of the entire build process from source to final binary.


## Supported Packages

`sbpm.sh` supports building and managing a comprehensive collection of packages, compilers, libraries, utilities, networking tools, window managers, and more. This extensive support makes SBPM a versatile tool for developers, system integrators, and embedded systems engineers alike.

### Compiler Toolchains & Languages

- **C Compilers & Toolchains:**  
  `tcc`, `gcc`, `native-compiler`, `cross-compiler`, `avr-toolchain`, `otcc`, `cc500`, `scc`, `subc`, `cproc`, `c`, `aboriginal`  
  Support for multiple C compilers and cross compilers enables flexible development and cross platform builds.

- **Standard Libraries:**  
  `musl`, `glibc`, `dietlibc`, `uclibc`  
  Multiple C standard libraries allow tailoring builds for size, performance, or compatibility.

- **Other Languages & Tools:**  
  `go`, `oyacc`, `lambda-delta`, `tmg`  
  Support for additional languages and parser generators broadens development possibilities.

### Shells & Scripting Utilities

- Shells: `bash`, `dash`, `ash`, `zsh`, `tcsh`  
- Text processing: `awk`, `grep`, `sed`  
- Build tools: `make`  
- Core utilities: `toolbox`, `busybox`, `toybox`  
- Tools: `curl`, `wget`, `rsync`, `gzip`, `bzip2`, `xz`, `lzip`, `tar`, `diff`, `bc`

### System & Networking Tools

- Networking & Security: `strongswan`, `nmap`, `john`, `aircrack-ng`, `masscan`, `hping`, `interceptor`, `gnupg`, `iptables`  
- System utilities: `kmod`, `smartmontools`, `flashrom`, `pcmciautils`, `initramfs`, `mkroot`  
- Debugging & Development: `gdb`, `pahole`  
- Filesystem tools: `jfsutils`, `squashfs-tools`

### Window Managers & User Interface

- Window managers: `i3wm`  
- Launchers & menus: `dmenu`  
- Terminal multiplexers: `tmux`  
- Editors: `vim`

### Bootloaders & Firmware

- `grub`, `coreboot`, `flashrom`  
  Support for bootloader and firmware tools enables low level system customization and embedded device development.

### Emulators & Virtualization

- `qemu` 
  Support for QEMU allows running and testing software across different architectures and environments.

### Telecommunications & Radio

- `libosmocore`, `libosmo-gprs`, `gapk`, `osmocom-bb`, `esp` 
  Packages focused on mobile communications and radio protocols for specialized development.

---

This broad package coverage demonstrates `sbpm.sh` capability to serve as a one stop solution for building, managing, and deploying software stacks ranging from minimal embedded systems to full featured Linux environments.

For a full list of supported packages and detailed build instructions please read `sbpm.sh`

## Contributing

Contributions are welcome! Please fork the repository and submit pull requests.

---

## License

This project is licensed under the GPL3 License.
