# Disable SecureBoot

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
