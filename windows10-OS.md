# 🪟 Windows 10 Setup Guide (VirtualBox)

Running Windows 10 in VirtualBox allows you to use Windows applications on other operating systems safely. This guide provides a streamlined path from ISO download to a fully optimized system.

---

## 🖥️ System Requirements
- **RAM:** 2 GB minimum (4 GB – 8 GB recommended).
- **CPU:** At least 2 cores.
- **Storage:** 50 GB free space (SSD recommended for speed).
- **ISO:** [Download Windows 10 ISO](https://microsoft.com) directly from Microsoft.

---

## 🛠 Phase 1: Creating the Virtual Machine
1.  **Initialize:** Open VirtualBox and click **New**.
    - **Name:** `Windows-10-Pro`
    - **ISO Image:** Select your downloaded Windows 10 ISO.
    - **Skip Unattended Installation:** Check this box to ensure you can manually configure settings.
2.  **Hardware Allocation:**
    - **Memory:** Set at least **4096 MB** (4GB).
    - **Processors:** Allocate **2 CPUs**.
    - **EFI:** Check "Enable EFI" (optional, but better for modern hardware support).
3.  **Virtual Hard Disk:**
    - Create a virtual hard disk (VDI).
    - Set size to **50 GB** (Dynamically Allocated).
4.  **Critical Performance Fixes:**
    - **Display:** Go to **Settings > Display**, set Video Memory to **128 MB** and check **Enable 3D Acceleration**.
    - **System:** Under **Motherboard**, ensure Pointing Device is set to **USB Tablet**.

---

## 💿 Phase 2: Installing the OS
1.  **Start:** Select your VM and click **Start**.
2.  **Initial Setup:** Choose language/keyboard settings, then click **Install Now**.
3.  **Product Key:** Click **"I don't have a product key"** (you can activate later).
4.  **Installation Type:** Select **"Custom: Install Windows only (advanced)"**.
5.  **Target Disk:** Select the "Unallocated Space" (your 50GB virtual drive) and click **Next**.
6.  **Finalizing:** Follow the prompts for region and user account setup.
    *Pro Tip: Disconnect the internet during this stage to create a "Local Account" easily.*

---

## 🚀 Phase 3: Post-Installation Essentials
Once you reach the Windows desktop, you must install **Guest Additions** for screen resizing and performance.
1.  **Install Guest Additions:** In the VM menu bar, go to **Devices > Insert Guest Additions CD image**.
2.  **Run Installer:** Open File Explorer in the VM, go to the CD Drive, and run `VBoxWindowsAdditions.exe`.
3.  **Reboot:** Restart the virtual machine.
4.  **Optimization:** Once rebooted, go to **View > Full-screen Mode**.

---

## 🔍 Phase 4: Troubleshooting


| Issue | Solution |
| :--- | :--- |
| **"VT-x is disabled" Error** | You must enable **Virtualization Technology** in your physical computer's **BIOS/UEFI**. |
| **VM is Extremely Slow** | Ensure **3D Acceleration** is enabled and you have allocated at least 2 CPU cores. |
| **No Internet in VM** | Check **Settings > Network**. Ensure Adapter 1 is set to **NAT** and "Cable Connected" is checked. |
| **Blue Screen (BSOD) at startup** | Disable **Hyper-V** on your host machine (Cmd as Admin: `bcdedit /set hypervisorlaunchtype off` then reboot). |
| **Resolution won't change** | Re-install **Guest Additions** and ensure the video memory is at least 128MB. |

---

## 🎥 Video Tutorials & Visual Walkthroughs
For a step-by-step visual guide, follow these detailed video walkthroughs:

*   **[How to Install Windows 10 on VirtualBox](https://youtu.be/JOIqPThxFb8?si=in3z0Rlb7svj83ny)** (12 min)  
    *Complete walkthrough for beginners.*

