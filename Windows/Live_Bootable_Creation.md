# How to Create a Live Boot

## What is a Live Boot?
A live boot allows you to run an operating system directly from a bootable USB drive without installing it on your computer. This is especially useful for troubleshooting, testing OS installations, or running an OS without making permanent changes to your computer's hard drive.

### Requirements:
1. **A USB Drive** (at least 4GB recommended)
2. **A Computer**
3. **An ISO file** for the operating system you want to boot (e.g., Ubuntu, Linux Lite, Windows, etc.)
4. **A tool to create the bootable drive** (like Rufus, Etcher, or dd)

### Steps to Create a Live Boot

#### Step 1: Download the ISO file
- Go to the official website of the operating system you want to create a live boot for.
- Download the ISO file for the operating system (e.g., Ubuntu, Debian, etc.).

#### Step 2: Prepare the USB Drive
1. Plug in the USB drive to your computer.
2. Ensure that the USB drive is empty, or back up any important data as it will be erased during this process.

#### Step 3: Use a Tool to Create the Bootable USB

**Using Rufus (Windows):**

1. Download and install [Rufus](https://rufus.ie/).
2. Open Rufus.
3. In the "Device" section, select your USB drive.
4. In the "Boot selection" section, select "Disk or ISO image" and browse to your downloaded ISO file.
5. Leave other settings at default, unless you need to adjust them (e.g., for partition scheme or file system).
6. Click "Start" and wait for the process to complete.

**Using Etcher (Windows, macOS, Linux):**

1. Download and install [Etcher](https://www.balena.io/etcher/).
2. Open Etcher.
3. Click on "Flash from File" and select your ISO file.
4. Select your USB drive as the target.
5. Click "Flash!" and wait for the process to complete.

**Using dd (Linux/macOS):**

1. Open a terminal.
2. Use the following command (make sure to replace `/path/to/iso` with the path to your ISO file and `/dev/sdX` with your USB drive):
    ```bash
    sudo dd if=/path/to/iso of=/dev/sdX bs=4M status=progress
    ```
3. Wait for the process to finish (it may take a while depending on the size of the ISO and speed of the USB drive).

#### Step 4: Boot from the USB Drive
1. Once the process is complete, restart your computer.
2. Enter the BIOS/UEFI settings (usually by pressing F2, F12, ESC, or DEL during boot).
3. In the BIOS/UEFI, change the boot order so that the USB drive is prioritized over the hard drive.
4. Save and exit BIOS/UEFI.
5. Your computer should now boot from the USB drive into the operating system you've installed on it.

### Troubleshooting:
- **USB not detected:** Ensure the USB is properly inserted and formatted.
- **Boot issues:** Double-check that the ISO file was properly written to the USB.
- **UEFI/Legacy mode:** Some systems require you to disable Secure Boot or switch between UEFI and Legacy mode.

Now you have a fully functioning live boot setup!

#### Additional Tips:
- You can use the live boot environment to try the operating system without installing it, or use it for system recovery.
- Some live boots come with built-in tools for disk partitioning, system repair, and more.
