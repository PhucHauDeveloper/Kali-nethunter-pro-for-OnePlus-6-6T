<img align="right" src="enchilada.png" width="350" alt="Kali nethunter pro running on fajita/enchilada">

# Running Kali nethunter pro on the OnePlus 6 / 6T

## Partitioning your device

### Prerequisites
- Unlocked bootloader

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)
  
- [Modded TWRP](https://github.com/WoA-OnePlus-6-Series/WoA-on-OnePlus6-Series/releases/tag/Recovery)

### Notes
> [!WARNING]  
> 
> IF YOU DON'T WANT DUALBOOT THEN YOU CAN SKIP THIS STEP!!!
> 
> DO NOT REBOOT YOUR PHONE! If you think you made a mistake, ask for help with me.
> 
> Do not run all commands at once, execute them in order!
>
> YOU CAN BREAK YOUR DEVICE WITH THE COMMANDS BELOW IF YOU DO THEM WRONG!!!

### Opening CMD as an admin
> Download **platform-tools** and extract the folder somewhere, then open CMD as an **administrator**.
>
> It is recommended to keep this window open and use it throughout the entire guide.
> 
> Replace `path\to\platform-tools` with the actual path to the platform-tools folder, for example **C:\platform-tools**.
```cmd
cd path\to\platform-tools
```

#### Boot the modded recovery
> While in fastboot mode, replace `path\to\twrp.img` with the actual path of the image
```cmd
fastboot boot path\to\twrp.img
```

### Backing up important files
> This will back up **fsc**, **fsg**, **modemst1** and **modemst2** to the current path your CMD is opened in (for example **C:\platform-tools**). Confirm these files are actually there before proceeding.
> 
> Keep these backups in a safe place. If your device's software ever gets destroyed, you might need these backups or your phone could lose cellular capabilities.
>
> If you've got anything else you want to back up, do this now. Your Android data will be erased in the next steps.
```cmd
cmd /c "for %i in (fsg,fsc,modemst1,modemst2) do (adb shell dd if=/dev/block/by-name/%i of=/tmp/%i.bin & adb pull /tmp/%i.bin)"
```

#### Backing up your boot image
> This will back up your boot image in the current directory
```cmd
adb pull /dev/block/by-name/boot boot.img
```

### Partitioning guide
> Your OnePlus 6/6T may have different storage sizes. This guide uses the values of the 128GB model as an example. When relevant, the guide will mention if other values can or should be used.

#### Unmount data
> Rerun the command until you see the message `umount: /dev/block/sda17: Invalid argument`
```cmd
adb shell umount /dev/block/by-name/userdata
```

#### Preparing for partitioning
```cmd
adb shell parted /dev/block/sda
```

#### Printing the current partition table
> Parted will print the list of partitions, userdata should be the last partition in the list.
```cmd
print
```

#### Removing userdata
> Replace **$** with the number of the **userdata** partition, which should be **17**, you should run it 1 2 times to be safe
```cmd
rm $
```

#### Recreating userdata
> Replace **6559MB** with the former start value of **userdata** which we just deleted (it is probably 6599MB)
>
> Replace **64GB** with the end value you want **userdata** to have
```cmd
mkpart userdata ext4 6559MB 64GB
```

#### Creating Linux partition
> Replace **64GB** with the end value of **userdata**
>
> Replace **125GB** with the end value of your disk, use `p free` to find it
```cmd
mkpart linux ext4 64GB 125GB
```


#### Exit parted
```cmd
quit
```


### Formatting data
- Format all data in TWRP, or Android will not boot.
- ( Go to Wipe > Format data > type yes )

#### Check if Android still starts
- Just restart the phone, and see if Android still works

## [Next step: Rooting your phone](/guide/2-root.md)
















