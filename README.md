:no_entry_sign: Development Stuff Ahead :no_entry_sign:
#### If you find yourself reading this, you have stumbled upon a development version of the guide
#### View the master version [here](https://github.com/kfechter/LegionY530Ubuntu)

# Installing Ubuntu on the Legion Y530

This repository provides scripts and a step by step on how to get Ubuntu running on the Lenovo Legion Y530.


These steps were tested on a Legion with the following Specs, but should work for all configurations:

* i7-8750H
* 32GB DDR4
* 1920x1080 Resolution (60Hz)
* 512GB NVMe SSD + 500GB SATA SSD
* Geforce GTX 1050Ti

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

### If you want to disable secureboot, follow the steps here <steps here please>


## 3. Boot from the flash drive.

After selecting yes to save the settings, the machine will reboot. as soon as the reboot happens, start pressing the F12 button until you see the boot device selection screen. 

![Boot Device Selection](https://raw.githubusercontent.com/kfechter/LegionY530Ubuntu/8234d4c4a473c91043bc3caae6725cc2e917647b/Images/bootManager.jpg "Boot Device Selection")

Select the flash drive and press enter to boot. on the screen that pops up, select "Try ubuntu without installing" or the equivalent option. 

## 5. Install Ubuntu

If wifi is not working working, you may need to perform steps under "Additional Notes" at the bottom.  

Select the "Install Ubuntu" icon on the desktop and follow the wizard to install Ubuntu on your desired drive. Once completed, select the option to restart the computer.

## 6. Install any available updates

If wifi is not working working, you may need to perform steps under "Additional Notes" at the bottom.  

Run the following command `sudo apt update && sudo apt dist-upgrade`. Follow any terminal prompts and when updates are complete, restart the computer. After rebooting, follow the above steps for getting wifi working. the next step will get wifi working permanently.
