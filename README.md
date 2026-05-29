# WSL2 Automated Installer Batch Scripts

[![GitHub license](https://shields.io)](https://github.com)
[![GitHub stars](https://shields.io)](https://github.com)
[![GitHub forks](https://shields.io)](https://github.com)
[![Platform](https://shields.io)](https://microsoft.com)

An automated, step-by-step batch processing utility to properly configure, update, and deploy **Windows Subsystem for Linux 2 (WSL2)** on Windows environment installations. This project splits the complex setup into clean, readable batch modules to ensure error-free initialization.

> [!IMPORTANT]
> **Administrative Privileges Required:** You MUST execute these batch files with administrator permissions. If you run them normally, Windows will block the installation of the required virtual features.

---

## 🚀 Why Use This Script?

Manually installing WSL2 can lead to missing optional features, architecture mismatch errors, or outdated virtualization kernels. These modular batch scripts manage everything for you safely and sequentially.

* **Automated Feature Provisioning:** Installs WSL core components and the Virtual Machine Platform automatically.
* **Modular Safety Execution:** Split into distinct parts so you can safely restart your computer when Windows requires it without breaking the pipeline.
* **Architecture Validation:** Tailored optimally for standard Windows x64 setups.

---

## 📋 Prerequisites

* **OS:** Windows 10 (Build 19041 and higher) or Windows 11.
* **Architecture:** Intel / AMD x64.
* **Permissions:** Administrative rights are required to enable Windows Virtualization hooks.

---

## 🛠️ Step-by-Step Installation

Because Windows must activate system-level features, the setup is cleanly broken into chronological parts. 

### 1️⃣ Part 1: System Feature Activation
This enables the underlying Windows Subsystem for Linux framework and required virtual network infrastructure.
* **Right-click `Part1.bat` and select "Run as Administrator"**.
* *Note: Your computer will prompt or require a system reboot after this step to apply virtual features.*

### 2️⃣ Part 2: Kernel Update & Set WSL2 Default
This updates your system to the modern WSL2 kernel subsystem layer.
* **Right-click `Part2.bat` and select "Run as Administrator"**.
* This sets the global execution defaults to version 2:
  ```cmd
  wsl --set-default-version 2
  ```

### 3️⃣ Part 3: Finalization & Distro Hook
Final check to verify deployment environment integrity.
* **Right-click `Part3.bat` and select "Run as Administrator"** to verify your running version status.

---

## 🗂️ Project Structure

```text
├── Part1.bat        # Stage 1: Dispatches Windows Optional Features (DISM) [Requires Admin]
├── Part2.bat        # Stage 2: Configures default WSL kernel versioning [Requires Admin]
├── Part3.bat        # Stage 3: Post-installation verification wrapper [Requires Admin]
└── README.md        # Documentation storefront
```

---

## 🤝 Contributing

Contributions make the open-source community amazing! Feel free to fork this project, fix potential edge-case system paths, or add support for automated Linux distro provisioning packages. 

1. **Fork** the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** your Changes (`git commit -m 'Add some AmazingFeature'`)
4. **Push** to the Branch (`git push origin feature/AmazingFeature`)
5. Open a **Pull Request**

## 📝 License

Distributed under the MIT License. See `LICENSE` for more information.
