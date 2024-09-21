<img align="right" src="enchilada.png" width="350" alt="Kali nethunter pro running on fajita/enchilada">

# Running Kali nethunter pro on the OnePlus 6 / 6T

## Uninstallation

### Why is this needed?
If you want to uninstall Kali this is used instead of deleting partitions manually to avoid human error + writing a whole dedicated guide to just uninstalling.

If you want to unlock your bootloader you'll need to do a re-unlock.

### Prerequisites

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)
  
- [EDL tools]() FILE NEEDED

### Uninstall instructions

#### Boot into EDL mode
> Hold the volume down + power button while the phone is turned off, and 
```cmd
adb reboot bootloader
```
> Then hold volume up + volume down, then plug in the cable, now the computer will display a new Port, usually Qualcomm HS-USB QDLoader 9008, now unzip EDL.zip, run MsmDownloadTool V4.0_factory_patched.exe and press start to start flashing, then you will return to android 9 with locked bootloader, you may want to unlock it to be able to install another operating system if you like

## Finished!













