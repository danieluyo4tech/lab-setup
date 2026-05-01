# 🤖 Bliss OS Setup Guide (Android for Desktop)

Bliss OS allows you to run a modern Android environment as a virtual machine. This guide covers the complete installation from scratch, including the specific hardware emulation tweaks required for Android to run smoothly on VirtualBox.

---

## 🖥️ System Requirements
- **RAM:** 2 GB minimum (4 GB recommended).
- **CPU:** 2 Cores.
- **Storage:** 20 GB free space.
- **ISO:** [Download Bliss OS](https://blissos.org) (Standard x86_64 version).

---

## 🛠️ Phase 1: Creating the Virtual Machine

Before loading the ISO, you must "build" the virtual hardware to match Android's requirements.

1.  **Initialize:** Open VirtualBox and click **New**.
    - **Name:** `Bliss-OS`
    - **Type:** `Linux`
    - **Version:** `Other Linux (64-bit)`
2.  **Resources:**
    - **Memory:** Allocate **4096 MB** (4GB) for a fluid experience.
    - **Processor:** Go to **Settings > System > Processor** and set it to **2 CPUs**.
    - **Storage:** Create a virtual hard disk of **20 GB** (VDI Dynamically Allocated).
3.  **Critical Graphics & Mouse Fixes:**
    *Without these, the screen may stay black or the mouse will not click correctly.*
    - **Display:** Under **Display > Screen**, set Graphics Controller to **VMSVGA** and check **Enable 3D Acceleration**.
    - **Mouse:** Under **System > Motherboard**, change Pointing Device to **USB Tablet**.

---

## 💿 Phase 2: Installing to the Hard Drive

This process moves the OS from the temporary "Live" environment to your virtual disk permanently.

1.  **Booting:** Start the VM. When prompted, browse and select your Bliss OS `.iso` file.
2.  **Installer:** At the blue boot menu, scroll down and select: 
    `Installation - Install Bliss-OS to harddisk`.
3.  **Partitioning (The Technical Part):**
    - Select **Create/Modify partitions**. 
    - Choose **No** for GPT.
    - Select **New** → **Primary** → Press **Enter** (Full Size).
    - Select **Bootable**. Ensure the word `"Boot"` appears under "Flags."
    - Select **Write**, type `yes` and press Enter.
    - Select **Quit**.
4.  **Formatting & Finishing:**
    - Select the new partition you just made (`sda1`) and format it as **ext4**.
    - Select **Yes** to install **GRUB bootloader**.
    - Select **Yes** to make the `/system` directory **read-write** (essential for root access and updates).

---

## 🚀 Phase 3: The Final Essential Step

If you don't do this, the VM will keep restarting the "Installation" process instead of booting into Android.

1.  **Power Down:** Once the installation says "Finished," do **not** click "Run Bliss OS." Instead, close the VM window and select **Power off the machine**.
2.  **Eject Media:** 
    - Go to **Settings > Storage**.
    - Right-click the Bliss OS `.iso` file under the Controller: IDE.
    - Select **Remove Attachment**.
3.  **First Boot:** Start the VM. It will now boot directly into the Android setup wizard. 

---

## 🔍 Troubleshooting Android on VirtualBox


| Issue | Solution |
| :--- | :--- |
| **Stuck at "Detecting Android"** | Restart and go to Settings > Display. Change Graphics Controller to **VBoxSVGA**. |
| **Mouse doesn't move** | Ensure System > Motherboard > Pointing Device is set to **USB Tablet**. |
| **No Internet** | Go to Settings > Network. Ensure Adapter 1 is **NAT**. Click Advanced > check **Cable Connected**. |
| **Play Store Crashes** | Ensure you downloaded the "GMS" (Google Play Services) version of the Bliss ISO. |

---

### Video Tutorials
* [Install BlissOS (Android) In VirtualBox](https://www.youtube.com/watch?v=CErwa-09-zw) (9 min)
* [Running a BlissOS VM in VirtualBox](https://www.youtube.com/watch?v=Efvux7d0zD0) (13 min)
* [How to Install Bliss OS 16.9.7 on VirtualBox](https://www.youtube.com/watch?v=ptV5mOBTXIg) (11 min)
