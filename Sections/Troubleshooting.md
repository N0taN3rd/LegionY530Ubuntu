# Common Issues and how to solve them

### WiFi Doesn't work

open a terminal and run the command `lspci | grep -i realtek` If you see a line containing a realtek wifi card, then follow these steps to configure the realtek module and get wifi working

run the command `echo "options r8822be aspm=0" | sudo tee /etc/modprobe.d/r8822be.conf`    
run the command `sudo rmmod r8822be`    
run the command `sudo modprobe r8822be`

### Laptop seems to freeze before/after/during login screen

If your laptop seems to freeze at any point before installing the nvidia drivers, you may need to disable nouveau modeset during boot until the drivers are installed. To disable modeset, follow the steps below.

reboot the machine either by Magic SysRq or by holding the power button down and turning it back on.

As soon as the screen turns purple (After the Legion logo screen), press esc. You should see a screen similar to the following.

![Selecting Ubuntu in Grub](https://raw.githubusercontent.com/kfechter/LegionY530Ubuntu/0fc36c44e069d4e157faa4b16e87cc9625a7c0e1/Images/grubSelectionScreen.png)

highlight the entry that says "Ubuntu" and press 'e', you should get a screen that looks similar to the following.

![Adding Nouveau.modeset=0](https://raw.githubusercontent.com/kfechter/LegionY530Ubuntu/0fc36c44e069d4e157faa4b16e87cc9625a7c0e1/Images/kernelOptions.png)

find the section that says 'quiet splash', and add nouveau.modeset=0 to it so it reads 'quiet splash noveau.modeset=0'

press F10 to boot with the changes.


### Nvidia switching doesn't seem to be working (i.e, nvidia mode enabled and external screens don't work)

if after doing sudo prime-select nvidia, you notice that external screens don't work. Try logging out and back in. If they still don't work, then reboot the machine. 

##### __Note: If you deviate from the stock kernel, this may cause issues with the nvidia drivers__
