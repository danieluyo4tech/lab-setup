# 🐧 The Ultimate Beginner's Guide: Setting Up an Ubuntu Lab

This comprehensive guide will take you from zero to a professional, full-screen Ubuntu Linux environment. It is written specifically for those who have never used a Virtual Machine (VM) before.

---

## 📂 Phase 1: Gathering Your Tools
Before we build the "virtual" computer, we need the software and the operating system files.

### 1. Download the Hypervisor (The Engine)
VirtualBox is the software that allows you to run an entire second computer inside a window on your desktop.
*   **Link:** [Download Oracle VirtualBox](https://virtualbox.org)
*   **Action:** Click on **"Windows hosts"** (or macOS if applicable).
*   **Extra Step:** Also download the **VirtualBox Extension Pack** from the same page. This allows things like USB 3.0 support and better webcam integration.

### 2. Download the Ubuntu ISO (The Blueprint)
The ISO file is a digital image of the installation disc.
*   **Link:** [Download Ubuntu Desktop](https://ubuntu.com)
*   **Action:** Choose the **LTS (Long Term Support)** version (e.g., 24.04 LTS). 
*   **Why LTS?** These versions are tested for stability and receive security updates for years.

---

## 🛠️ Phase 2: Installing VirtualBox
1.  Run the `.exe` installer you downloaded.
2.  Click **Next** through all prompts. 
3.  **Warning:** Your internet connection may drop for about 10 seconds while it installs the virtual network drivers. This is normal.
4.  Once installed, open **Oracle VM VirtualBox**.

---

## 🏗️ Phase 3: Building the Virtual Computer
We need to "reserve" a portion of your physical computer's power for the Ubuntu VM.

1.  **Start New VM:** Click the blue **New** button.
2.  **Identity:**
    *   **Name:** `Ubuntu-Testing-Lab`
    *   **ISO Image:** Click the dropdown -> **Other** -> Select the Ubuntu ISO file you downloaded earlier.
    *   **Skip Unattended Installation:** **CRITICAL.** Check the box that says "Skip Unattended Installation." This ensures you learn the actual installation process.
3.  **Hardware (Memory & CPU):**
    *   **Base Memory:** Drag the slider to **4096 MB** (4GB). 
    *   **Processors:** Drag the slider to **2**. (Ubuntu struggles on a single core).
4.  **Virtual Hard Disk:**
    *   Select "Create a Virtual Hard Disk Now."
    *   Size: **25.00 GB** to **40.00 GB**. (It won't take up this space on your real drive immediately; it grows as you add files).
5.  **Graphics (The "Hidden" Step):**
    *   Before clicking Start, go to **Settings** -> **Display**.
    *   Set **Video Memory** to **128 MB**.
    *   Check **Enable 3D Acceleration**. This makes the interface smooth.

---

## 🚀 Phase 4: Installing the Ubuntu OS
1.  Click the green **Start** arrow.
2.  **The Boot Menu:** A black screen will appear. Hit **Enter** on "Try or Install Ubuntu."
3.  **The Installer:** 
    *   Select your **Language** and click **Install Ubuntu**.
    *   **Keyboard Layout:** Stick to the default unless you have a specific keyboard.
    *   **Installation Type:** Choose **Interactive Installation**.
    *   **Apps:** Choose **Default Selection** (faster) and check the box for **"Install third-party software for graphics and Wi-Fi."**
4.  **The Disk:** Select **"Erase disk and install Ubuntu."**
    *   *Note for Novices:* This ONLY erases the 25GB "fake" disk we created. Your Windows files are 100% safe.
5.  **User Account:** Enter your name and pick a password. Use something simple like `password123` for a lab, but remember it—Linux requires it for everything!
6.  **Wait:** The installation takes 5–15 minutes. When done, click **Restart Now**.
7.  **Final Prompt:** When you see "Please remove installation medium," just press **Enter**.

---

## 📺 Phase 5: The "Full Screen" Fix
If Ubuntu is stuck in a small window, you need to install **Guest Additions**. This is the most common hurdle for beginners.

1.  Log into Ubuntu.
2.  At the very top of your **VirtualBox window menu** (not inside Ubuntu), click **Devices** -> **Insert Guest Additions CD Image...**
3.  A CD icon will appear on your Ubuntu dock. A box will ask if you want to **Run**. Click **Run**.
4.  A terminal (black box) will open, ask for your password, and install the drivers.
5.  **Restart Ubuntu** (Click the power icon in the top right -> Power Off/Log Out -> Restart).
6.  Once logged back in, go to **View** -> **Full-screen Mode** (or press **Right Ctrl + F**).

---

## 🛡️ Phase 6: Detailed Troubleshooting

### Issue 1: "Virtualization is disabled in BIOS"
*   **Symptom:** The VM won't start or shows a "64-bit not available" error.
*   **Solution:** You must enter your computer's BIOS (usually by tapping **F2**, **F10**, or **Del** right as you turn the computer on). Look for **Intel VT-x**, **AMD-V**, or **SVM Mode** and set it to **Enabled**.

### Issue 2: The mouse is "stuck" inside the VM
*   **Solution:** VirtualBox "grabs" your mouse. To release it so you can go back to Windows/macOS, press the **Right Control** key once.

### Issue 3: Guest Additions Installation Failed
*   **Solution:** If the "Run" button didn't work, open the **Terminal** (Ctrl+Alt+T) and type these commands one by one:
    ```bash
    sudo apt update
    sudo apt install build-essential dkms linux-headers-$(uname -r)
    ```
    Then, try the **Devices -> Insert Guest Additions** step again.

### Issue 4: Resolution is still wrong
*   **Solution:** Right-click the Ubuntu desktop -> **Display Settings**. Manually change the **Resolution** to match your monitor (e.g., 1920x1080) and click **Apply**.

---

## 🏁 Next Steps
Now that your lab is ready, you should run a full update to ensure everything is secure:
Open the Terminal and type:
`sudo apt update && sudo apt upgrade -y`

**Would you like me to create a guide for setting up a "Shared Folder" so you can drag and drop files from Windows into Ubuntu?**
