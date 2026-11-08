# The Gray-Hat Linux Project

**Arch Linux-Based General-Purpose Cybersecurity Distribution**

Gray-Hat Linux is an open-source, Arch Linux-based GNU/Linux distribution designed for cybersecurity operations, security assessment, digital forensics, reverse engineering, malware analysis, cryptographic research, and related technical disciplines.

The distribution encompasses a security tool ecosystem specified to include more than 3,500 tools across offensive security, defensive security, digital forensics, malware analysis, reverse engineering, open-source intelligence (OSINT), cryptography, industrial and operational technology (OT) security, wireless security, application security, and additional areas of cybersecurity.

Gray-Hat is designed as a general-purpose cybersecurity environment rather than a distribution dedicated exclusively to penetration testing. Its architecture accommodates multiple security disciplines within a common operating system, package management infrastructure, and software environment.

The project is based on Arch Linux and uses its package management infrastructure, rolling-release model, and system components. Gray-Hat maintains its own distribution configuration, software packaging specifications, system integration components, and security tool organization.

**Development Status:** Gray-Hat is under active initial development. The complete tool collection and distribution infrastructure described in this document are not yet available as a verified release.

---

## 1. System Architecture

Gray-Hat uses the Linux kernel and the Arch Linux userspace as its operating system foundation.

The system architecture is organized into several components:

| Component | Implementation |
|---|---|
| Operating system base | Arch Linux |
| Kernel | Linux |
| Primary architecture | x86_64 |
| Init system | systemd |
| Package manager | pacman |
| Package format | Arch Linux package format |
| Desktop environment | XFCE |
| Display protocol | X11 |
| Display manager | LightDM |
| Network management | NetworkManager |
| DNS infrastructure | systemd-resolved |
| Privacy services | Tor and I2P |
| ISO construction | archiso |
| Source control | Git |
| Licensing | GNU GPL v3.0 for Gray-Hat-owned code |

The distribution retains compatibility with the Arch Linux package ecosystem while providing its own configurations and security-oriented software components.

The Archiso infrastructure is used to assemble the live filesystem, package collection, system configuration, and bootable installation media.

### 1.1 System Components

The Gray-Hat system consists of:

- A Linux kernel and hardware support infrastructure.
- A systemd-based service management environment.
- An XFCE graphical desktop environment.
- Standard GNU/Linux development and administrative utilities.
- Networking, authentication, storage, and system management components.
- Security tools organized by discipline and function.
- Distribution-specific configuration and package metadata.
- Optional privacy and network research services.

The architecture separates base operating system functions from specialized security software.

### 1.2 Operating System Compatibility

Gray-Hat follows Arch Linux conventions for package construction, filesystem hierarchy, service management, and software dependencies.

Distribution-specific packages are maintained separately from upstream Arch Linux packages.

Gray-Hat does not implement an independent kernel, system call interface, C standard library, or alternative package format.

---

## 2. Cybersecurity Disciplines

Gray-Hat encompasses a broad range of cybersecurity disciplines.

The classification system organizes software by technical function. Individual applications may belong to multiple categories.

### 2.1 Offensive Security

Tools for authorized security assessment, vulnerability research, penetration testing, exploitation research, and attack surface analysis.

Principal areas include:

- Network penetration testing
- Web application security testing
- Vulnerability assessment
- Exploit development
- Authentication security assessment
- Active Directory security
- Cloud penetration testing
- Mobile application security testing
- Wireless network assessment
- Red team operations
- Protocol security analysis

### 2.2 Defensive Security

Tools for system protection, security monitoring, threat detection, incident investigation, and infrastructure assessment.

Principal areas include:

- Host-based security analysis
- Network traffic monitoring
- Intrusion detection
- Security configuration auditing
- Vulnerability management
- Threat intelligence
- Endpoint analysis
- Log analysis
- Security event investigation
- Blue team operations

### 2.3 Digital Forensics

Utilities and frameworks for the acquisition, examination, recovery, and interpretation of digital evidence.

Covered areas include:

- Filesystem forensics
- Disk and partition analysis
- Memory forensics
- Network forensics
- Mobile device forensics
- File recovery
- Metadata examination
- Timeline reconstruction
- Artifact analysis
- Incident reconstruction

### 2.4 Malware Analysis

Tools for examining malicious or suspicious software through static, dynamic, and behavioral analysis.

Covered areas include:

- Static binary inspection
- Dynamic execution analysis
- Malware classification
- Behavioral monitoring
- Memory inspection
- Binary unpacking
- Signature analysis
- Sandbox analysis
- Executable format examination

### 2.5 Reverse Engineering

Tools for examining software, firmware, executable files, and low-level system behavior.

Covered areas include:

- Disassembly
- Decompilation
- Debugging
- Binary instrumentation
- Binary format analysis
- Firmware extraction
- System call tracing
- Program behavior analysis
- Vulnerability research

### 2.6 Open-Source Intelligence

Software for collecting, processing, correlating, and evaluating publicly accessible information.

Covered areas include:

- Domain and DNS intelligence
- Public infrastructure discovery
- Metadata analysis
- Internet-exposed asset assessment
- Public repository examination
- Information correlation
- Threat intelligence collection

### 2.7 Cryptography and Cryptanalysis

Tools for cryptographic implementation testing, protocol examination, password security assessment, and cryptographic research.

Covered areas include:

- Symmetric cryptography
- Asymmetric cryptography
- Hash function analysis
- Password auditing
- TLS and certificate analysis
- Cryptographic protocol assessment
- Key management
- Post-quantum cryptographic research

### 2.8 Industrial and Operational Technology Security

Tools for investigating industrial communication protocols, operational technology environments, and industrial control system security.

Covered areas include:

- Industrial network protocol analysis
- SCADA security assessment
- Industrial device identification
- Firmware analysis
- OT network monitoring
- Industrial asset inventory
- Protocol inspection
- Industrial vulnerability research

Active assessment of industrial systems must be performed only within appropriately authorized and controlled environments.

### 2.9 Wireless Security

Tools for wireless network analysis, radio communication assessment, and wireless protocol examination.

Covered areas include:

- IEEE 802.11 security
- Bluetooth analysis
- Wireless packet capture
- Radio frequency analysis
- Wireless authentication assessment
- Wireless protocol research

### 2.10 Additional Disciplines

The tool classification system also accommodates:

- Application security
- Cloud security
- Container security
- Software supply chain security
- Embedded systems security
- Hardware security
- Mobile security
- IoT security
- Network engineering
- Security automation
- Security testing frameworks
- Protocol fuzzing
- Vulnerability research
- Purple team operations

These categories are not mutually exclusive.

---

## 3. Software and Package Infrastructure

Gray-Hat uses pacman as its primary package manager.

Software is distributed using packages compatible with the Arch Linux packaging system.

### 3.1 Package Organization

The package architecture distinguishes between:

**Base system packages**

Packages required for the operating system, kernel, service management, storage, networking, and essential administrative functions.

**Desktop packages**

Packages required for the graphical desktop, display management, file management, terminal environment, and graphical system utilities.

**Security packages**

Applications and frameworks used for cybersecurity assessment, research, monitoring, analysis, and investigation.

**Distribution packages**

Gray-Hat-specific packages providing system identity, configuration, integration, metadata, and distribution functionality.

### 3.2 Independent Package Repositories

The repository architecture defines three logical package collections:

| Repository | Function |
|---|---|
| `grayhat-core` | Distribution-specific system and integration packages |
| `grayhat-security` | Cybersecurity software packages |
| `grayhat-staging` | Packages undergoing integration and validation |

The package repositories are separate from the Arch Linux upstream repositories.

Package construction uses PKGBUILD specifications and the standard Arch Linux toolchain.

### 3.3 Package Verification

The packaging process accounts for:

- Source origin and provenance
- Source integrity verification
- Package dependency resolution
- License identification
- Build environment isolation
- Package installation verification
- Basic functionality testing
- Package authenticity
- Version tracking
- Repository metadata consistency

Package signing and publication are treated as distinct operations from package compilation.

### 3.4 Package Classification

Security applications are organized according to technical discipline and functional purpose.

A package may be associated with multiple categories without requiring multiple installations of the same application.

The classification infrastructure is independent of the package manager's core dependency resolution mechanism.

---

## 4. Desktop Environment

Gray-Hat uses XFCE as its initial desktop environment.

XFCE provides a conventional graphical environment with relatively modest resource requirements and a modular component structure.

The desktop environment includes or integrates:

- XFCE Session Manager
- Xfwm window manager
- XFCE Panel
- Thunar file manager
- XFCE Terminal
- LightDM display manager
- GTK-based graphical utilities
- NetworkManager applet

The desktop uses X11 as its initial display system.

### 4.1 Live Environment

The live environment is configured to provide an XFCE desktop session through LightDM.

A dedicated non-root live user is used for the graphical session.

Live-session authentication and account configuration are separate from the authentication requirements of a permanently installed system.

### 4.2 Administrative Access

Administrative functions use standard GNU/Linux privilege management facilities.

Graphical applications are not intended to run with unrestricted root privileges by default.

---

## 5. Networking Infrastructure

NetworkManager is the designated primary network management service.

The networking architecture separates physical and virtual network configuration from application-level privacy services.

### 5.1 Network Management

The system supports conventional networking facilities including:

- Ethernet
- Wireless networking
- DHCP
- Static IP configuration
- DNS resolution
- Network interface administration
- VPN integration through compatible software

NetworkManager is responsible for ordinary network interface configuration.

systemd-resolved provides the designated DNS integration.

Network management services are configured to avoid conflicting ownership of the same network interfaces.

### 5.2 Privacy Services

Gray-Hat adopts a **Privacy-ready** networking model.

Tor and I2P are included in the distribution's privacy architecture as optional services.

They are separate from the default network connection.

| Service | Purpose | Default Policy |
|---|---|---|
| Tor | Application-level anonymity network access | Disabled |
| torsocks | Proxy integration for compatible applications | On demand |
| i2pd | I2P network connectivity | Disabled |
| NetworkManager | Standard system networking | Enabled |

Privacy services are not intended to transparently redirect all operating system traffic by default.

### 5.3 Tor Integration

Tor provides an application-accessible anonymity network through its supported proxy interfaces.

Applications must be configured appropriately to use Tor.

The presence of Tor does not establish system-wide anonymity.

### 5.4 I2P Integration

Gray-Hat uses i2pd as its initial I2P routing implementation.

I2P connectivity is provided through explicitly configured local interfaces and proxy services.

Administrative interfaces and local proxy listeners are restricted according to their respective security requirements.

### 5.5 Privacy Limitations

Privacy-service availability does not guarantee anonymity, traffic confidentiality, or protection against all forms of information disclosure.

Application configuration, DNS behavior, protocol limitations, software vulnerabilities, and user activity can affect privacy properties.

---

## 6. Boot and Live System Infrastructure

Gray-Hat uses Archiso to construct its bootable live environment.

The boot configuration is derived from the Arch Linux `releng` profile and maintained within the Gray-Hat source repository.

The live system includes:

- Linux kernel images
- Initial RAM filesystem
- Bootloader configuration
- Compressed root filesystem
- System service configuration
- Live user configuration
- Desktop session configuration
- Selected software packages

The initial boot infrastructure includes BIOS and UEFI configurations.

The live environment is distinct from a permanently installed operating system. Installation workflows and persistent system configuration require separate validation.

---

## 7. Source Repository

The source repository contains the configuration, packaging definitions, and integration files used in Gray-Hat development.

The repository is organized around the Archiso profile and additional distribution components.

```text
Gray-Hat/
├── packages/
│   └── gray-hat-release/
│       └── os-release
│
├── profile/
│   ├── airootfs/
│   ├── efiboot/
│   ├── grub/
│   ├── syslinux/
│   ├── packages.x86_64
│   ├── packages.aarch64
│   ├── pacman.conf
│   └── profiledef.sh
│
├── .opencode/
├── LICENSE
├── MAINTAINERS.txt
├── README.md
└── SECURITY.txt
```

### 7.1 Archiso Profile

The `profile/` directory defines the live filesystem configuration and ISO construction parameters.

The `profile/airootfs/` directory contains files intended for inclusion in the live root filesystem.

### 7.2 Package Definitions

The `packages/` directory contains Gray-Hat-specific package sources, definitions, and associated metadata.

### 7.3 Bootloader Configuration

The `efiboot/`, `grub/`, and `syslinux/` directories contain bootloader-related configurations.

Bootloader paths, kernel parameters, and Archiso variables must remain consistent with the corresponding live filesystem configuration.

### 7.4 Development Automation

The `.opencode/` directory contains agent definitions and development-team configuration used to assist with implementation, analysis, documentation, and technical review.

Automated development activities remain subject to project review and acceptance requirements.

---

## 8. Building Gray-Hat

Gray-Hat's ISO construction infrastructure uses Archiso.

The supported build environment is Arch Linux.

The source repository can be edited on other GNU/Linux distributions, but ISO construction should be performed in a compatible Arch Linux environment.

### 8.1 Build Dependencies

The primary build requirements include:

- Arch Linux
- archiso
- pacman
- Required build utilities
- Sufficient disk space
- Access to the configured package repositories

### 8.2 Source Preparation

Obtain the Gray-Hat source repository and enter its root directory.

The ISO profile is located in:

```text
profile/
```

### 8.3 ISO Construction

Within a properly configured Arch Linux build environment:

```bash
sudo mkarchiso -v \
    -w ./work \
    -o ./out \
    ./profile
```

The generated ISO is written to the selected output directory.

### 8.4 Build Considerations

Build results depend on:

- The installed Archiso version
- Package repository availability
- Package version compatibility
- Profile configuration correctness
- Available disk space
- Filesystem permissions
- Network availability
- Build environment configuration

**Build status:** The current development configuration has not yet been validated as a complete, bootable Gray-Hat release.

Generated ISO images are not maintained as ordinary source files in the Git repository.

---

## 9. Development and Maintenance

Gray-Hat is developed as an open-source software project.

Development is organized around independent technical components and reviewable source changes.

The project uses Git for version control.

Changes to packages, system configurations, service integration, and build infrastructure are expected to be documented and reviewed.

### 9.1 Development Principles

The development process emphasizes:

- Compatibility with the underlying Arch Linux infrastructure
- Clear component responsibilities
- Minimal modifications to upstream software
- Reproducible build procedures where practical
- Explicit dependency management
- Traceable source modifications
- Security review of privileged components
- Documentation of system behavior
- Isolation of untrusted build operations

### 9.2 Automated Development

Automation may be used for:

- Package definition generation
- Dependency inspection
- Configuration analysis
- Static code analysis
- Build verification
- Documentation generation
- Regression testing
- Security review assistance

Automated changes are not exempt from project acceptance requirements.

### 9.3 Release Management

Distribution releases are identified using version metadata associated with the corresponding source configuration.

Release publication requires validation of the boot environment, package consistency, system services, and supported desktop functionality.

---

## 10. Project Governance

Gray-Hat follows a lead-maintained, open-contribution development model.

The project is open to contributions from individual developers, researchers, maintainers, and other members of the open-source community.

The **Lead Developer** retains final authority over:

- System architecture
- Technical standards
- Package repository policies
- Source code acceptance
- Maintainer responsibilities
- Release approval
- Project organization
- Major technical decisions

Contributions do not automatically grant repository management or release authority.

Maintainer information is documented separately in `MAINTAINERS.txt`.

---

## 11. Contributing

Contributions to Gray-Hat are welcome.

Contributions may include:

- New package definitions
- Existing package maintenance
- Security tool integration
- Bug fixes
- System configuration improvements
- Build system improvements
- Automated tests
- Documentation
- Compatibility corrections
- Security vulnerability reports

Contributors should use focused changes with clear technical explanations.

### 11.1 Contribution Requirements

Submitted changes should:

1. Preserve existing functionality unless modification is intentional and documented.
2. Follow applicable project conventions.
3. Identify relevant dependencies.
4. Avoid introducing unnecessary privileged execution.
5. Include appropriate validation evidence.
6. Document known limitations.
7. Respect third-party software licenses.
8. Avoid including credentials, private keys, or confidential information.

Source changes may be submitted through pull requests.

Final acceptance is determined through the project's review and governance process.

---

## 12. Security Policy

Gray-Hat contains software intended for cybersecurity analysis, security assessment, and vulnerability research.

Some tools may perform operations that affect network services, application behavior, connected devices, or system availability.

Users are responsible for ensuring that their activities comply with applicable laws, organizational policies, and authorization requirements.

Testing against third-party systems requires appropriate authorization.

### 12.1 Vulnerability Reporting

Security vulnerabilities affecting Gray-Hat's distribution-specific components should be reported through the project's documented security reporting process.

Sensitive vulnerability information should not be disclosed through public issues before an appropriate coordinated disclosure process has been established.

Refer to `SECURITY.txt` for project-specific reporting information.

### 12.2 Third-Party Software

Gray-Hat incorporates independently maintained software projects.

Security vulnerabilities affecting those projects may require reporting to their respective upstream maintainers.

Gray-Hat-specific integration defects and packaging vulnerabilities remain within the project's maintenance scope.

---

## 13. Licensing

Gray-Hat-owned source code is distributed under the **GNU General Public License, version 3.0 only (GPL-3.0-only)**, except where individual files explicitly specify different licensing terms.

See `LICENSE` for the complete license text.

### 13.1 Third-Party Components

Gray-Hat incorporates software developed and licensed by independent upstream projects.

The Gray-Hat project license does not replace or override the licenses of those components.

Each third-party package retains its applicable copyright notices and licensing conditions.

### 13.2 Upstream Attribution

Gray-Hat is based on Arch Linux and uses the Arch Linux packaging and ISO construction infrastructure.

Arch Linux and associated upstream software projects remain independent of Gray-Hat.

Gray-Hat is not an official Arch Linux distribution or an Arch Linux Project release.

---

## 14. Project Status

Gray-Hat is in its initial development phase.

The source repository currently contains the foundations of an Archiso-based distribution, including distribution identity configuration, bootloader customization, desktop package selection, and preliminary live-system integration.

The complete security tool collection, independent package repositories, networking integrations, installation workflows, and release infrastructure have not yet been validated as a complete distribution.

The 3,500+ tool specification describes the distribution's defined software scope, not the number of packages currently available in a tested release.

No stable-release status is implied by this document.

---

**Gray-Hat Linux**  
*Open-source GNU/Linux distribution for cybersecurity research and operations.*