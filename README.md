# Sensors & Systems - Building the Embedded Future
## Track B: The Embedded Linux Architect (Raspberry Pi 5)

This repository contains the architecture and configuration for a custom-built Embedded Linux environment designed to teach students the bridge between software and silicon via I2C sensor integration.

---

## Project Overview
The goal of this learning unit is to bypass standard OS distributions and use **Buildroot** to create a tailored, minimal Linux image for the **Raspberry Pi 5**, focusing on:
- **Direct Hardware Mapping:** Using Device Tree Overlays (DTOs).
- **Driver Abstraction:** Implementing userspace I2C communication.
- **Pedagogy:** Creating "Broken Lab" scenarios for student debugging.

---

## 🛠 Project Roadmap

### Phase 1: Infrastructure (COMPLETED)
- [x] **Host Environment:** Configured Fedora-based build system with required cross-compilation dependencies.
- [x] **Toolchain:** Generated a custom AArch64 toolchain.
- [x] **Minimal OS:** Built a hardened Linux Kernel (BCM2712) and root filesystem.
- [x] **Base Validation:** Integrated `i2c-tools` for hardware discovery.

### Phase 2: Sensor Integration (IN PROGRESS)
- [ ] **Hardware Mapping:** Writing Device Tree Overlays (`.dts`) to bind sensors to the I2C bus.
- [ ] **DTCO Workflow:** Compiling overlays into `.dtbo` blobs.
- [ ] **Connectivity:** Physical wiring and bus verification.

### Phase 3: The "Golden Reference" Implementation
- [ ] **Driver Logic:** Developing a robust C implementation using `linux/i2c-dev.h`.
- [ ] **Manual Drafting:** Creating the step-by-step Student Lab Manual.

### Phase 4: Debugging & Delivery
- [ ] **Broken Lab Design:** Creating intentional configuration errors (e.g., wrong I2C address, missing clock config).
- [ ] **Final Packaging:** Delivering the SD card images and documentation.

---

## 🔧 How to Reproduce
1. Install dependencies on Fedora:
   `sudo dnf install patch perl-ExtUtils-MakeMaker perl-Time-Piece ncurses-devel diffutils rsync wget cpio`
2. Run `make rpi5_lab_defconfig` (to be uploaded).
3. Run `make -j$(nproc)`.