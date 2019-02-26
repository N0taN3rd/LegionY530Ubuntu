:no_entry_sign: Development Stuff Ahead :no_entry_sign:
#### If you find yourself reading this, you have stumbled upon a development version of the guide
#### View the master version [here](https://github.com/kfechter/LegionY530Ubuntu)

# Installing Ubuntu on the Legion Y530

This repository provides scripts and a step by step on how to get Ubuntu running on the Lenovo Legion Y530.


These steps were tested on a Legion with the following Specs:

* i7-8750H
* 16GB DDR4
* 1920x1080 Resolution (60Hz)
* 256GB NVMe SSD + 1TB Platter

However this should work on all configurations.

#### If at any point the machine becomes unresponsive, you can use Magic SysRq to reboot safely

Remember: *<b>R</b>eboot <b>E</b>ven <b>I</b>f <b>S</b>ystem <b>U</b>tterly <b>B</b>roken*

To use Magic SysRq, hold down the right Alt key and PrtSc, and then type (In Order) R, E, I, S, U, B. The machine should then reboot. If for some reason this doesn't work, then hold the power button down to power off the machine. 

#### If the machine freezes shortly after login or before the login screen appears, follow the steps section 'disable nouveau modeset' under Additional Notes. These steps will have to be followed at every boot until the nvidia drivers are installed. 
 
### Some things to note before Beginning:

* __This guide assumes decent knowledge of the Linux command line__
* __Following this guide will result in Windows being replaced with Ubuntu__
  * You can however, choose to install alongside your current OS
* __Several features of the Legion will be unavailable on Linux__

### Back up your data using Windows Backup or similar before continuing


Now that the important information is out of the way, let's begin

## 1. Download the Ubuntu disk image and imaging software
__NOTE: Installing a version other than this guide recommends may work but steps of the guide may differ or be non-functional__
* [Ubuntu 18.04.3 LTS](http://releases.ubuntu.com/18.04/ubuntu-18.04.3-desktop-amd64.iso)
* [Etcher](https://www.balena.io/etcher/)

## 2. Using Etcher, write the image to a USB Drive

After installing and opening Etcher, select your USB device and downloaded .iso and press the button labeled Flash!

![Etcher Screenshot](https://github.com/kfechter/LegionY530Ubuntu/raw/84dfd189e2f21102bcb7e97d45d539b353a55143/Images/etcherScreen.PNG "Etcher Screenshot")

![Etcher Screenshot 2](https://github.com/kfechter/LegionY530Ubuntu/raw/84dfd189e2f21102bcb7e97d45d539b353a55143/Images/etcherScreen2.PNG "Etcher Screenshot")

![Etcher Screenshot 3](https://github.com/kfechter/LegionY530Ubuntu/raw/84dfd189e2f21102bcb7e97d45d539b353a55143/Images/etcherScreen3.PNG "Etcher Screenshot")

## 3. Disable SecureBoot

Once Etcher has completed (It will show a screen with the message "Flash Complete"), you can close it. While Ubuntu can be installed with SecureBoot enabled, some drivers and features will not work. To disable, the machine needs to be booted into the UEFI settings. To get into UEFI settings, open the start menu in Windows and select restart while holding down shift. Hold down shift until you see the advanced option screen. 

![Advanced Startup](https://raw.githubusercontent.com/kfechter/LegionY530Ubuntu/8234d4c4a473c91043bc3caae6725cc2e917647b/Images/chooseOptions.jpg "Advanced Startup")

From this screen, select Troubleshoot, then Advanced Options, then UEFI Firmware Settings. 

![Troubleshoot](https://github.com/kfechter/LegionY530Ubuntu/blob/8234d4c4a473c91043bc3caae6725cc2e917647b/Images/troubleshootOptions.jpg "Troubleshoot")

![Advanced Options](https://raw.githubusercontent.com/kfechter/LegionY530Ubuntu/8234d4c4a473c91043bc3caae6725cc2e917647b/Images/advancedOptions.jpg "Advanced Options")

After selecting UEFI Firmware settings, click the button labelled "Restart" on the screen that appears. 

Once in the UEFI settings, navigate to the Security tab using the arrow keys, then navigate down to 
Secure Boot. Press enter, select "Disabled" using the arrow keys, then press enter again. Once Secure Boot has been set to disabled, press F10 and select "Yes" to save the changes. 

![UEFI Firmware Setting](https://raw.githubusercontent.com/kfechter/LegionY530Ubuntu/8234d4c4a473c91043bc3caae6725cc2e917647b/Images/biosMain.jpg "UEFI Firmware Settings")

![Security Settings](https://raw.githubusercontent.com/kfechter/LegionY530Ubuntu/8234d4c4a473c91043bc3caae6725cc2e917647b/Images/biosSecurity.jpg "Security Settings")

## 4. Boot from the flash drive.

After selecting yes to save the settings, the machine will reboot. as soon as the reboot happens, start pressing the F12 button until you see the boot device selection screen. 

![Boot Device Selection](https://raw.githubusercontent.com/kfechter/LegionY530Ubuntu/8234d4c4a473c91043bc3caae6725cc2e917647b/Images/bootManager.jpg "Boot Device Selection")

Select the flash drive and press enter to boot. on the screen that pops up, select "Try ubuntu without installing" or the equivalent option. 

## 5. Install Ubuntu

If wifi is not working working, you may need to perform steps under "Additional Notes" at the bottom.  

Select the "Install Ubuntu" icon on the desktop and follow the wizard to install Ubuntu on your desired drive. Once completed, select the option to restart the computer.

## 6. Install any available updates

If wifi is not working working, you may need to perform steps under "Additional Notes" at the bottom.  

Run the following command `sudo apt update && sudo apt dist-upgrade`. Follow any terminal prompts and when updates are complete, restart the computer. After rebooting, follow the above steps for getting wifi working. the next step will get wifi working permanently.

## 7. Install Nvidia drivers and Nvidia-prime packages. 

In the terminal, run the following commands, following any prompts    
`sudo add-apt-repository ppa:graphics-drivers/ppa`    
`sudo apt install -y nvidia-driver-415 nvidia-prime`

## 8. Verify that the Nvidia drivers and Prime packages are installed and configured correctly.
run the following series of commands and verify the output

```
prime-select query 
``` 
Should output 'nvidia'
```
sudo prime-select intel 
```
Should output text similar to 'Selecting profile intel'
```
prime-select query 
```
Should now output 'intel'

If the above commands complete successfully, then you have successfully configured your Legion Y530 with Ubuntu.

# Additional Notes

### Disable Nouveau Modeset

to disable modeset for the nouveau module, follow the below steps

reboot the machine, as soon as the screen turns purple (After the Legion logo screen), press esc. You should see a screen similar to the following.

![Selecting Ubuntu in Grub](https://raw.githubusercontent.com/kfechter/LegionY530Ubuntu/0fc36c44e069d4e157faa4b16e87cc9625a7c0e1/Images/grubSelectionScreen.png)

highlight the entry that says "Ubuntu" and press 'e', you should get a screen that looks similar to the following.

![Adding Nouveau.modeset=0](https://raw.githubusercontent.com/kfechter/LegionY530Ubuntu/0fc36c44e069d4e157faa4b16e87cc9625a7c0e1/Images/kernelOptions.png)

find the section that says 'quiet splash', and add nouveau.modeset=0 to it so it reads 'quiet splash noveau.modeset=0'

press F10 to boot with the changes.

### Nvidia Switching
With kernel 4.20, rebooting is no longer necessary to switch profiles, however log out and log in is still required.

### Wifi Fix for Realtek Cards

If your laptop has a Realtek Card, you will notice that doing the rmmod on ideapad_laptop won't fix the wifi. to get the wifi working, perform the following steps.

run the command `echo "options r8822be aspm=0" | sudo tee /etc/modprobe.d/r8822be.conf`    
run the command `sudo rmmod r8822be`    
run the command `sudo modprobe r8822be`
