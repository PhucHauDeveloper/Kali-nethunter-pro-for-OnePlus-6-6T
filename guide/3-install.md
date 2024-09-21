<img align="right" src="enchilada.png" width="350" alt="Kali nethunter pro running on fajita/enchilada">

# Running Kali nethunter pro on the OnePlus 6 / 6T

## Installing Kali nethunter Pro

### Prerequisites
- [Kali nethunter pro image](https://kali.download/nethunterpro-images/kali-2024.3/kali-nethunterpro-2024.3-sdm845.tar.xz)

### Installing change boot slot
> Boot into fastboot, I assume you have installed android on boot a, now switch to boot b, if not sure run the following command

```cmd
fastboot getvar current-slot
```

> Now switch to boot b

```cmd
fastboot set_active b
```

### Installing Kali nethunter pro
- Unpack the kali-nethunterpro-2024.3-sdm845.tar.xz archive

#### Flash boot image
> Replace `path\to\nethunterpro-20240822-sdm845-phosh.boot-fajita[enchilada].img` with the actual path of boot image (These files are located in the extracted folder of kali-nethunterpro-2024.3-sdm845.tar.xz)

```cmd
fastboot flash boot_b path\to\nethunterpro-20240822-sdm845-phosh.boot-fajita[enchilada].img
```

#### Flash kali rootfs image
```cmd
fastboot flash linux path\to\nethunterpro-20240822-sdm845-phosh.rootfs.img
```

### Reboot to fastboot
> Hold **volume down** + **power** to force reboot your phone into fastboot mode

#### Delete dtbo
> [!WARNING]  
> 
> IF YOU DON'T RUN THIS COMMAND YOU WON'T BE ABLE TO BOOT INTO KALI!!!
```cmd
fastboot erase dtbo_b
```

### WARNING
> [!Warning]
> IF YOU REBOOT INTO KALI AND IT DOESN'T SHOW THE COMMAND LINE, MAKE SURE YOU ERASE DTBO

### Reboot to kali nethunter pro
Your device should reboot by itself after +- 10 minutes of waiting, after which you will be booted into kali, password is 1234, for the last step.

## [Last step: Setting up dualboot](/guide/4-dualboot.md)

















