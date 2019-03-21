#### This will install Ubuntu leaving SecureBoot enabled. If you want to disable it, follow the guide [here](SecureBootOff.md)

To install Ubuntu, follow the steps below. 

To get to advanced startup, open windows settings, then click Update & Security. Select Recovery from the left hand side, and click the button labeled restart now under Advanced Startup. 

![Advanced Startup Windows](https://raw.githubusercontent.com/kfechter/LegionY530Ubuntu/ab92b30dcb6e4ec996fdbd1db41022106beaf51e/Images/windowsSettings.PNG "Advanced Startup")


 <BootMenu/>
   <BootSelection/>
     
     
     
##### Install Ubuntu

Select the "Install Ubuntu" icon on the desktop and follow the wizard to install Ubuntu on your desired drive. Once completed, select the option to restart the computer.

##### Install any available updates

Run the following command `sudo apt update && sudo apt dist-upgrade`. Follow any terminal prompts and when updates are complete, restart the computer.

[Install the Nvidia Drivers](NvidiaConfig.md)
