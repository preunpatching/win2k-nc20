# Windows 2000 for Samsung NC20
A project designed to make Windows 2000 run on the Samsung NC20.

> [!NOTE]
> Not all drivers and OEM software will work on Windows 2000. However, for daily use, it is fine.

## How to install
Download the files from the [releases page](https://github.com/preunpatching/win2k-nc20/releases/).

### Install Windows
To get started, use [Rufus](https://rufus.ie/) to create the USB drive with the Windows ISO.

> [!NOTE]
> This ISO will not boot in a VM. It will only boot on real hardware from an USB drive.

Then, plug in the USB drive, start up the PC, press the `ESC` key in the BIOS to enter the boot menu, then select your drive and follow setup.

> [!NOTE]
> Windows 2000 cannot access more than 137GB (128GiB) of the drive due to versions prior to Windows XP SP1 only supporting 28-bit LBA (Logical Block Addressing) and not 48-bit LBA.

### Install drivers
Install drivers like normal, except with notes for the following drivers:
- Make sure to install the `Visual C++ 2005 Redistributable` to prevent driver errors.
- Make sure to run `Setup.bat` in driver root folder to prevent driver errors.
- Make sure to install `Update Rollup 1 for Windows 2000 SP4` (`windows2000-kb891861-v2-x86-enu.exe`) to prevent driver errors.
- Make sure to install the Windows XP API wrapper by running `win2k_xp_v1_10\NSTALL_WRAPPER.BAT` and rebooting the system.
- For graphics drivers, make sure to run `Setup.bat` after installing the program to prevent errors. Make sure to switch to 16-bit or 32-bit color depth as the drivers are not designed for the 256 color mode and will produce broken colors.
- For Samsung Easy Display Manager, make sure to run `Setup.bat` after installing the program to prevent errors.
- For Samsung Battery Manager, run `Setup.bat` to install the program.
- For chipset drivers, manually install the drivers for `Unknown device` as `VIA MSP Miscellaneous Bus`.
- For card reader drivers, manually install the drivers for `PCI Flash Memory` as `VIA MSP Cardreader Host Controller`.

## Bugs
- There are currently no working camera drivers for Windows 2000.
- While Easy Display Manager is running, sound control through hotkeys is broken.
- Samsung Battery Manager cannot set power plans due to incompatible `POWRPROF.DLL`.
