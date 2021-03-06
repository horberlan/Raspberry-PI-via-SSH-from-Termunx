<h1 align="center"> Raspberry PI — SSH from Termux Android </h1><img align="right" src="https://upload.wikimedia.org/wikipedia/commons/f/f3/Termux_2.png" width="" height="40px"><img align="right" src="https://www.raspberrypi.org/app/uploads/2011/10/Raspi-PGB001.png" width="" height="40px">


* To make your Raspberry PI automatically connect to the router, edit and move <a href="https://github.com/horberlan/Raspberry-PI-via-SSH-from-Termux/blob/main/wpa_supplicant.conf" target="_blank" title="wpa supplicant">this file</a> in the ```/boot``` folder  and reboot.
* To install Termux app  <a href="https://termux.com/" target="_blank" title="HTML Tutorials">click here</a>.
After install this aplication, you will install ***openssh*** package to realize connection ssh with raspberry PI or other systems:
```terminal
$ pkg update
$ pkg upgrade
$ pkg install openssh
```
<p><img align="right" alt="Termux" src="https://raw.githubusercontent.com/horberlan/Raspberry-PI-via-SSH-from-Termunx/main/WPSApp.png" width="320" height=""></p>

You can see the IP of raspberry using  <a href="https://play.google.com/store/apps/details?id=com.themausoft.wpsapp&hl=en&gl=US" target="_blank" title="WPSApp">WPSApp</a> on your android sistem. This is a tool to manipulate your router, configure and see connected users. 


After installing the WPSApp, navigate to the  ***DEVICES*** tab and update the search to find your Rapberry PI's IP address on your smartphone.

<br>
* After copying the IP to the clipboard, use the ssh connection to access the standard user "pi":


```terminal
$ ssh pi@192.168.0.107
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes

pi@192.168.0.107's password: raspberry

pi@raspberrypi:~ $
```
You might want to try <a href="https://github.com/horberlan/Raspberry-PI-SSH-Termux/blob/main/ssh.sh"> this SSH file<a>  to conect autologin. Run ```sh ssh.sh``` in Termunx.
 
you are now connected to RPI over an SSH connection, if you want to connect to the <a href="https://www.realvnc.com/en/connect/download/viewer/" target="_blank" title="VNC Viewer">VNC viewer</a> to remotely control the desktop with your Android, follow these steps:
```
pi@raspberrypi:~ $ sudo raspi-config
```
 
Go to the Raspberry Pi OS configuration panel with raspi-config. 
<a href="https://www.raspberrypi.org/documentation/configuration/raspi-config.md" target="_blank" title="raspi-config">raspi-config</a> is the Raspberry Pi configuration tool that brings together the main constructions containing the basic and advanced features for that OS.  

<img align="left" src="https://raw.githubusercontent.com/horberlan/Raspberry-PI-via-SSH-from-Termunx/main/raspi-config.png" width="320" height="">

* First using ***&#8595;***, go to```Update``` to get the latest version of this application.
* Go to ```Interface Options``` and activate the connection option ```VNC``` and then eneble. Use ***&#8633;*** to go Back.
* Subsequently access ```Display Options``` &#8674; ```Resolution``` &#8674; choose option ```Defaoult```. This will make the screen resolution of the raspberry match that of the smarthphone.
* Finally, go to ```System Options``` and navigate to ```Boot / Auto Login``` and choose the option ```Desktop Autologin```.

Press the function "***&#8633;***" to go down in the submenu and choose the option ***finish***. wait for the system to restart.
