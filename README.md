# 🛠️ Cyber Security Lab Setup Guide

This folder contains step-by-step instructions for building a secure, isolated virtualization environment for penetration testing, malware analysis, and network exploitation.

---

## 🏗️ Lab Architecture
The lab is designed to be **flexible and isolated** from your physical home network to ensure safety.

*   **Hypervisors:** VirtualBox or VMware Workstation.
*   **Attacker Machine:** Kali Linux (Primary) / Parrot OS.
*   **Target Environment:** 
    *   **Windows Ecosystem:** Windows 10/11, Windows Server (AD Labs).
    *   **Mobile/Alternative:** Bliss OS (Android), ChromeOS.
    *   **Linux/Unix:** Metasploitable, Ubuntu, Debian, or custom vulnerable kernels.
*   **Network Strategy:** Dual-adapter setup (NAT for updates, Host-Only for isolated lab traffic).

---

## 📂 Contents

### 1. [Hypervisor Installation](./Hypervisors.md)
*   Setup guides for **VirtualBox** and **VMware**.
*   **Troubleshooting:** Fixes for BIOS Virtualization (VT-x/AMD-V) and driver conflicts.

### 2. [Kali Linux Setup (Attacker)](./Kali-Setup.md)
*   The primary command center for security auditing.
*   Network configuration for "Safe Hacking" environments.

### 3. [Windows 10 Setup (Target)](./Windows10-Setup.md)
*   **📥 Download:** Using the Media Creation Tool or Evaluation ISO.
*   **⚙️ Configuration:** Instructions for disabling security features (Defender/Firewall) for testing.

### 4. [Bliss OS Setup (Mobile Target)](./BlissOS-Setup.md)
*   Android-based environment for mobile app security and penetration testing.

### 5. [Other OS Deployments](./Other-OS-Guides.md)
*   *This section is updated as new machines are added.*
*   **Metasploitable:** Intentionally vulnerable Linux VM.
*   **Ubuntu/CentOS:** For Linux privilege escalation labs.
*   **Windows Server:** For Active Directory and Domain Controller exploitation.

---

## 🚀 Quick Start
1.  **Hypervisor:** Install [VirtualBox](https://virtualbox.org) or [VMware](https://vmware.com).
2.  **BIOS:** Enable `VT-x` (Intel) or `SVM` (AMD) in your computer's BIOS/UEFI settings.
3.  **Command Center:** Follow [Kali-Setup.md](./Kali-Setup.md) to build your attacker machine.
4.  **Targets:** Deploy at least one target machine (Windows or Bliss OS) to begin testing.

---

## ⚠️ Safety Warning
> [!CAUTION]
> **Lab Isolation:** Ensure all target machines are kept on a **Host-Only** or **Internal** network. Never execute suspicious scripts or malware on a machine that has "Bridged" access to your actual home network.

---

## 🔗 Useful Links
*   [Microsoft Evaluation Center](https://microsoft.com) (For Windows ISOs)
*   [VulnHub](https://vulnhub.com) (Pre-built vulnerable machines)
*   [OffSec Documentation](https://kali.org)
