<img align="right" src="enchilada.png" width="350" alt="Kali nethunter pro running on fajita/enchilada">

# Running Kali nethunter pro on the OnePlus 6 / 6T

## Troubleshooting Issues
> Below you will find a list of common problems and their solutions


### Bootloop when running kali for the first time
> It seems you have not deleted dtbo, as of now kali needs you to delete it first to boot properly, try running the following command to delete it.
```cmd
fastboot erase dtbo_b
```


### Black screen on initial boot
> You should make sure you have downloaded the official version from kali.org, try flashing kali again [here](3-install.md)


### Can't boot into android after installing kali
> Unlike kali android needs dtbo to boot properly, maybe your android partition is b, you should make sure you delete the correct dtbo of the partition for kali instead of android, if you do it wrong and there is no dtbo.img available download it from my releases section, it will help you to get into custom rom recovery or boot into it if you are on OxygenOS 11.
```cmd
fastboot flash dtbo path\to\dtbo.img
```

### I CAN'T FIX OR CAN'T START MY PHONE
> If you have serious problem like can not boot, make sure you have held volume up button and power button for 10s, then try to charge the phone still can not boot then don't worry, right now you just need to flash EDL for the phone and save it, instructions and tools are [here](https://xdaforums.com/t/tool-6t-msmdownloadtool-v4-0-59-oos-v9-0-13.3867448/)


##### Finished!



















