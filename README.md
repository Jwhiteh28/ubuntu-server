<p align="center">
<img src="https://i.imgur.com/0tmrBR2.png" alt="ubuntu logo"/>
</p>

<h1>Ubuntu Server - Home Server</h1>
This project demonstrates builing a fully headless Ubuntu home server.<br />

<h2>Environments and Technologies Used</h2>

- HP Prodesk
- Laptop 
- SSH(Secure Shell) 
- USB Flash Drive (8gb)

<h2>Operating Systems Used </h2>

- Ubuntu Server</b> (24.04LTS)

<h2>Requirements</h2>

- Minimum hardware (RAM, CPU, Disk)
- Ubuntu Server ISO version
- Ethernet/network access
- SSH client for remote setup (optional)

<h2>Installation Steps</h2>
<p>The first step is to visit https://ubuntu.com/download/server to download the latest Ubuntu Server. </p>
<p>
<img src="https://i.imgur.com/PWoqQ2L.png" width="600" alt="ubuntu server"/>
</p>

<br />

<strong>Create the Bootable USB Flash Drive</strong>
<p>
- Next, we need to create a bootable USB flash drive(8gb). I downloaded software called BalenaEtcher: (https://etcher.balena.io/). Select the download you need for your computer. Since I'm on Windows, I select the Windows download.
</p>
<p>
<img src="https://i.imgur.com/l16iqXe.png" width="600" alt="BE install"/>
<img src="https://i.imgur.com/jLZWqji.png" width="600" alt="BE install"/>
</p>
<p>
  Once BalenaEtcher is finished downloading and installing, we run the program. At this moment, insert the empty USB flash drive.
</p>
<p>
<img src="https://i.imgur.com/MsmQ6aq.png" width="600" alt="BE install"/>
</p>
<p>
  BalenaEtcher makes the process easy to follow. When it is finished, safely remove the USB flash drive. Remember, once BalenaEtcher make the flash drive into a bootable drive, all the data in the drive will be deleted.
</p>
<p>
<img src="https://i.imgur.com/tmAgBLb.png" width="600" alt="BE install"/>
<img src="https://i.imgur.com/7ZL4oWD.png" width="600" alt="BE install"/>
</p>

<br />

<h2>The Ubuntu Server</h2>
<p>
  This is my old PC, a HP ProDesk. This will be my new home server.
</p>
<p>
  <img src="https://i.imgur.com/RlJGSww.jpeg" width="600" alt="HP desktop"/>
</p>
<p>
  I removed the DVD drive because I will be adding more storage in the future.
</p>
<p>
  <img src="https://i.imgur.com/oF7oVad.jpeg" width="600" alt="HP desktop"/>
</p>
<p>
- I inserted the USB flash drive into my old HP Prodesk PC, and before turning on the computer, make sure it is connected to the router with an ethernet cable. The server should be connected with ethernet cable for speed. 
</p>
<p>
- You will have to search for how to start up your computer's boot menu key. In my case, it's F12. You should eventually get a screen that says "Try install Ubuntu Server" or similar, and click it.
</p>
<p>
  <img src="https://i.imgur.com/bl3gEO9.png" width="600" alt="Server"/>
  <img src="https://i.imgur.com/2GC18C8.png" width="600" alt="Server"/>
</p>

<strong>Network configuration</strong>
<p>
- Here, we are being asked to configure our network interface. You see that there is a given DHCP and subnet. If we leave it this way, it may allow the IP address of the server to change, which we don't want. A server should always have a static IP address, so devices will always find the server. Select network interface > click enter > go down to edit IPv4 > enter > go to manual. Fill in your network information.
</p>
<p>
   <img src="https://i.imgur.com/0rZRNdU.png" width="600" alt="Network config"/>
</p>
<p>
- Proxy configuration: leave it blank, press enter for done. 
</p>
<p>
- Ubuntu archive mirror configuration: press enter. If you get an error, that means something went wrong with the static IP address configuration, so just go back and fix it, otherwise, click enter.
</p>
<p>
  <img src="https://i.imgur.com/uSCko0e.png" width="600" alt="mirror config"/>
</p>
<p>
- Guided storage configuration: Use the entire disk. The decision is yours to select ot unselect "set up this disk as an LVM group". An LVM group is part of Logical Volume Manager, a system in Linux that makes managing disk storage more flexible. So instead of splitting your disk into parititions, LVM lets you pool your storage together and then split it up however you want. Click enter done.
</p>
<p>
  <img src="https://i.imgur.com/IZCkiVm.png" width="600" alt="guided storage"/>
</p>
<p>
- Storage configuration: just click enter and continue.   
</p>
<p>
  <img src="https://i.imgur.com/ojugypS.png" width="600" alt="storage config"/>
</p>
<p>
- Profile configuration: You will be asked to to create an account and name your server. Hit enter once you finish.
</p>
<P>
  <img src="https://i.imgur.com/j92I418.png" width="600" alt="profile config"/>
</P>
<p>
- Upgrade to Ubuntu Pro: You can just skip for now unless you have a Ubuntu Pro License.
</p>
<p>
- SSH Configuration: If you want to be able to access this server remotely asap put an x in the "Install OpenSSH server". You will have SSH access, which means you will have remote access from another computer to connect to your server.
</p>
<p>
  <img src="https://i.imgur.com/GL0k67C.png" width="600" alt="SSH config"/>
</p>
<p>
- Featured server snaps: These are just features you can install on your server if you want, but I'm going to just skip and select done because I'll be installing features later.
</p>
<p>
  <img src="https://i.imgur.com/a4GKF8V.png" width="600" alt="server snaps"/>
</p>
<p>
 Once you see the installation is complete, you will see the option to reboot. Select "Reboot Now", finally remove the USB flash drive and press enter. You will be able to log in when reboot is complete.
</p>
<p>
  <img src="https://i.imgur.com/IKTvM6A.png" width="600" alt="login"/>
</p>
<!--
<strong>Security:</strong>
<p>
  One of the most important things about servers is security. We will first make sure our server is up-to-date. Type "sudo apt update". This is an administrative command, so your password will be required.
</p>
<p>
  <img src="" width="" alt=""/>
</p>
<p>
  When finished, type "sudo apt upgrade", it will ask if you want to continue, just type "y" for yes. After running the update, it's a good idea to restart your server, type "sudo reboot".
</p>
<p>
  <img src="" width="" alt=""/>
  <img src="" width="" alt=""/>
</p>
<strong>Automatic Updates:</strong>
<p>
  I will now set the server to automatically update. This will make it much more convenuent. Ubuntu Server should have unattended upgrade package installed by default, but here is how to check. Type "sudo apt install unattended-upgrades".
</p>
<p>
  <img src="" width="" alt=""/>
</p>
<p>
  As you can see, the server already has the newest version installed.
</p>
<p>
  <img src="" width="" alt=""/>
</p>
<p>
  Next, type "sudo apt install update-notifier-common". This will allow the server to automatically restart itself once updated.
</p>
<p>
  <img src="" width="" alt=""/>
  <img src="" width="" alt=""/>
</p>
<p>
  Now lets check the configuration. Type "cd /etc/apt/apt.conf.d" to change to a new directory. Then type "ls" to list the contents of this directory.
</p>
<p>
  <img src="" width="" alt=""/>
</p>
<p>
  There are two files that we are interested in, first, 50unattended-upgrades. Type "sudo nano 50unattended-upgrades" so we can configure it.
</p>
<p>
  <img src="" width="" alt=""/>
  <img src="" width="" alt=""/>
</p>
<p>
  Next, press the "ctrl + w" keys to make the search bar appear. Once it pops up, enter "automatic-reboot" then press enter.
</p>
<p>
  <img src="" width="" alt=""/>
</p>
<p>
  It should have taken you to the unattended-upgrade automatic-reboot "false". Delete "false" and turn it "true" and delete the //.
</p>
<p>
  <img src="" width="" alt=""/>
  <img src="" width="" alt=""/>
</p>
<p>
  Scroll down to "//Unattended_Upgrade::Automatic-Reboot-Time "02:00". You can choose when the upgrade happens. In this example, I'm choosing 1 am (01:00). Don't forget to delete the // to uncomment. Press ctrl + x on the keyboard to save it, "y" to continue, then press enter.
</p>
<p>
  <img src="" width="" alt=""/>
</p>
<p>
  "clear" to clear the screen and now check the second config file, "20auto-upgrades". Type "ls" and type "sudo nano 20auto-upgrades".
</p>
<p>
  <img src="" width="" alt=""/>
</p>
<p>
  Whereas the first config file has the auto update settings, this one enables them. The first line ensures the software package lists are up-to-date so the server gets the latest available packages. The second enables the unattended upgrade itself.
</p>
  You can check if it's enables if you see the "1", while "0" means it's disabled. Now press ctrl + x to save, then type "sudo reboot" to restart
<p>
</p>
--!>
<br />
