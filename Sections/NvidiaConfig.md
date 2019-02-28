# Install Nvidia drivers and Nvidia-prime packages. 

In the terminal, run the following commands, following any prompts    
`sudo add-apt-repository ppa:graphics-drivers/ppa`    
`sudo apt install -y nvidia-driver-415 nvidia-prime`

### Verify that the Nvidia drivers and Prime packages are installed and configured correctly.
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

If the above commands complete successfully, then you have successfully configured the nvidia drivers.

#### __Note: You should only need to log off and log on to complete the switch, but if that doesn't work, try rebooting.

Your OS is fully configured, but if you want some additional configurations or helpful software, you can view the [Advanced Features Guide](Advanced.md)
