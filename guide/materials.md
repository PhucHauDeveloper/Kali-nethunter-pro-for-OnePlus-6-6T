<img align="right" src="enchilada.png" width="350" alt="Kali nethunter pro running on fajita/enchilada">

# Running Kali nethunter pro on the OnePlus 6 / 6T

## Additional materials
> Below you will find a list of tweaks and materials for Kali on your ARM device


### General Audio
> For me it didn't work but you can try running the following command as official instructions from debian. You need to make sure to run this command after the first boot.
```cmd
sudo systemctl mask alsa-restore
```


### Run android tool on kali nethunter pro
> Waydroid is an open-source project that allows you to run the Android operating system in a container on a Linux system, effectively letting you run Android apps alongside Linux apps on the same device. It achieves this by using Linux containers (LXC) to isolate the Android environment from the host system, while still allowing interaction between the two.
> The installation is also very simple, run the following commands, it may take from 10 to 30 minutes depending on your network speed.
```cmd
sudo apt install waydroid
sudo waydroid init
reboot
```


#### Finished!





















