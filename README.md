# Android-USB-reverse-tethering
Reverse USB tethering (from pc to phone) w/o Root.   
This method makes use of the fact that a normal USB tethering mode on Android is actually similar to a wired ethernet connection to a router where traffic can go both ways.  
In this method, we will use a software-aided connection using ssh dynamic tunneling.  
---------------------------------------------------------------------------------  
What you need :  
1-An Android phone.  
2-USB cable.  
3-A pc running an ssh server regardless of the OS (I will disscuss it on windows and linux).
---------------------------------------------------------------------------------  
For windows : ![Download for windows](https://github.com/PowerShell/Win32-OpenSSH/releases)
For Linux : just check your package manager ex. for debian based systems 
```bash
sudo apt install openssh
```
After you connect the phone to the pc and activated USB tethering mode :-  

1-Get the IP address of the pc assigned with the phone using ipconfig and search for the adapter name:
![image](https://github.com/Abdelrahmant26/Android-USB-reverse-tethering/assets/68470744/bd6957a2-c18b-4813-bca3-0717d15d9d7a)  
here I have the connection name which is "Ethernet adapter Ethernet 2", You may now that name if you place the cursor on the wifi/ethernet sign in the taskbar.
IP assigned from the phone usually starts with 192.168.*.*
2-Start a dynamic ssh tunnel on that address:
using the command :
```bash
ssh -N -D $IP_ADDRESS_YOU_GOT:1080 $USERNAME_IN_WINDOWS@localhost
```


    
