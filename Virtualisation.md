
## Step 1 - Download and install VirtualBox

### Install both the platform package and the extension pack

URL: https://www.virtualbox.org/wiki/Downloads
![image](https://user-images.githubusercontent.com/39102148/226271493-e812395c-8eb6-4e57-b40c-2bd37e0a9fa3.png)

## Step 2 - Download OS image (I used Ubuntu 22.04.2 LTS)

### Download Ubuntu Desktop

URL - https://ubuntu.com/download/desktop
![image](https://user-images.githubusercontent.com/39102148/226272217-7faeeb14-3838-4b6b-aa3e-a513a05d0160.png)

## Step 3 - Create VM on VirtualBox

### Create a VM on VirtualBox with Ubuntu Desktop Image

- Guide - https://ubuntu.com/tutorials/how-to-run-ubuntu-desktop-on-a-virtual-machine-using-virtualbox#1-overview
- Video - https://youtu.be/wX75Z-4MEoM?t=630

### You also need to install the guest addition on the VM for proper screen resize:

- Guide - https://www.makeuseof.com/install-virtualbox-guest-additions-on-linux/<br>
** Skip unattended installation virtualbox to avoid issue. i.e. install it normally

## Step 4 - Download and install Cisco Anyyconnect client

### URL - https://clsavpn.clsa.com/

![image](https://user-images.githubusercontent.com/39102148/226273820-87cb0ec7-a36c-47d1-b7f7-6fce93478c01.png)

### Follow the installation guide below:

1. Install the remote desktop client of your choice, for example:<br>
```sudo apt-get install remmina-plugin-rdp```
2. Download AnyConnect client from the “clsavpn.clsa.com” web portal. Assume
the AnyConnect package is saved in the ~/Downloads folder.
3. Unzip and install Cisco AnyConnect
```
$ cd ~/Downloads
$ tar zxvf anyconnect-linux64-x.y.zzzzz-predeploy-k9.tar.gz
```
- Note: x.y.zzzzz is the current version number.
```
$ cd anyconnect-x.y.zzzzz/vpn
$ sudo ./vpn_install.sh
Accept the terms and let it finish.
Do you accept the terms in the license agreement? [y/n] y
You have accepted the license agreement.
Please wait while Cisco AnyConnect Secure Mobility Client is being installed...
Starting Cisco AnyConnect Secure Mobility Client Agent...
Done!
```
4. Start the AnyConnect GUI and log on.
```
/opt/cisco/anyconnect/bin/vpnui
```
Note:<br>
If you have problems in starting VPN, ensure the dependent packages are
installed.
```
$ sudo apt-get update
$ sudo apt-get install lib32z1 lib32ncurses5
```
If you see below error when starting vpnui, reboot your PC and try again<br>
“error while loading shared libraries: libpangox-1.0.so.0: cannot open shared<br>
object file: No such file or directory”
<br>
If you are running Fedora 2x, please also install the package pangox-compat:<br>
```
$sudo yum install pangox-compat
```

## Step 5 - Install Remmina to access a remote desktop

### Download and install Remmina on VM

- Guide - https://ubuntu.com/tutorials/access-remote-desktop#1-overview<br>
- tweak the display and audio setting

## Step 6 - Connect

  1. Connect to VPN via Cisco anyconnect as usual
  2. Create new connection on Remmina (save it for future use)
 
### Congrats and enjoy~
