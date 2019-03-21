# Install Ubuntu without SecureBoot

To install Ubuntu without secureboot enabled, follow the steps below. 

To get to advanced startup, open windows settings, then click Update & Security. Select Recovery from the left hand side, and click the button labeled restart now under Advanced Startup. 

![Advanced Startup Windows](../Images/windowsSettings.PNG "Advanced Startup")

![Advanced Startup](../Images/chooseOptions.jpg "Advanced Startup")

From this screen, select Troubleshoot, then Advanced Options, then UEFI Firmware Settings. 

![Troubleshoot](../Images/troubleshootOptions.jpg "Troubleshoot")

![Advanced Options](../Images/advancedOptions.jpg "Advanced Options")

After selecting UEFI Firmware settings, click the button labelled "Restart" on the screen that appears. 

Once in the UEFI settings, navigate to the Security tab using the arrow keys, then navigate down to 
Secure Boot. Press enter, select "Disabled" using the arrow keys, then press enter again. Once Secure Boot has been set to disabled, press F10 and select "Yes" to save the changes. 

![UEFI Firmware Setting](../Images/biosMain.jpg "UEFI Firmware Settings")

![Security Settings](../Images/biosSecurity.jpg "Security Settings")

Once the Settings have been saved, the machine will reboot. on the legion screen press the F12 button until you see the boot selection screen. 

![Boot Device Selection](../Images/bootManager.jpg "Boot Device Selection")

Select your flashdrive on the list, and press enter. 

##### Install Ubuntu

Select the "Install Ubuntu" icon on the desktop and follow the wizard to install Ubuntu on your desired drive. Once completed, select the option to restart the computer.

##### Install any available updates

Run the following command `sudo apt update && sudo apt dist-upgrade`. Follow any terminal prompts and when updates are complete, restart the computer.

[Install the Nvidia Drivers](NvidiaConfig.md)
