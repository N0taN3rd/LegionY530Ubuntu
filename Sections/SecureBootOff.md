# Install Ubuntu without SecureBoot

To install Ubuntu without secureboot enabled, follow the steps below. 

To get to advanced startup, open windows settings, then click Update & Security. Select Recovery from the left hand side, and click the button labeled restart now under Advanced Startup. 

![Advanced Startup Windows](https://raw.githubusercontent.com/kfechter/LegionY530Ubuntu/ab92b30dcb6e4ec996fdbd1db41022106beaf51e/Images/windowsSettings.PNG "Advanced Startup")

![Advanced Startup](https://raw.githubusercontent.com/kfechter/LegionY530Ubuntu/8234d4c4a473c91043bc3caae6725cc2e917647b/Images/chooseOptions.jpg "Advanced Startup")

From this screen, select Troubleshoot, then Advanced Options, then UEFI Firmware Settings. 

![Troubleshoot](https://github.com/kfechter/LegionY530Ubuntu/blob/8234d4c4a473c91043bc3caae6725cc2e917647b/Images/troubleshootOptions.jpg "Troubleshoot")

![Advanced Options](https://raw.githubusercontent.com/kfechter/LegionY530Ubuntu/8234d4c4a473c91043bc3caae6725cc2e917647b/Images/advancedOptions.jpg "Advanced Options")

After selecting UEFI Firmware settings, click the button labelled "Restart" on the screen that appears. 

Once in the UEFI settings, navigate to the Security tab using the arrow keys, then navigate down to 
Secure Boot. Press enter, select "Disabled" using the arrow keys, then press enter again. Once Secure Boot has been set to disabled, press F10 and select "Yes" to save the changes. 

![UEFI Firmware Setting](https://raw.githubusercontent.com/kfechter/LegionY530Ubuntu/8234d4c4a473c91043bc3caae6725cc2e917647b/Images/biosMain.jpg "UEFI Firmware Settings")

![Security Settings](https://raw.githubusercontent.com/kfechter/LegionY530Ubuntu/8234d4c4a473c91043bc3caae6725cc2e917647b/Images/biosSecurity.jpg "Security Settings")

Once the Settings have been saved, the machine will reboot. on the legion screen press the F12 button until you see the boot selection screen. 

![Boot Device Selection](https://raw.githubusercontent.com/kfechter/LegionY530Ubuntu/8234d4c4a473c91043bc3caae6725cc2e917647b/Images/bootManager.jpg "Boot Device Selection")

Select your flashdrive on the list, and press enter. 

##### Install Ubuntu

Select the "Install Ubuntu" icon on the desktop and follow the wizard to install Ubuntu on your desired drive. Once completed, select the option to restart the computer.

##### Install any available updates

Run the following command `sudo apt update && sudo apt dist-upgrade`. Follow any terminal prompts and when updates are complete, restart the computer.

<Continue to Install Nvidia>
