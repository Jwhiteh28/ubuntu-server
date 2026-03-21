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
<img src="" width="600" alt=""/>
<img src="" width="600" alt=""/>
</p>
<p>
  Once BalenaEtcher is finished downloading and installing, we run the program. At this moment, insert the empty USB flash drive.
</p>
<p>
<img src="" width="600" alt=""/>
</p>
<p>
  BalenaEtcher makes the process easy to follow. When it is finished, safely remove the USB flash drive. Remember, once BalenaEtcher make the flash drive into a bootable drive, all the data in the drive will be deleted.
</p>
<P>
<img src="" width="600" alt=""/>
</P>

<br />

<h2>The Ubuntu Server</h2>
<p>
- I inserted the USB flash drive into my old HP Prodesk PC, and before turning on the computer, make sure it is connected to the router with an ethernet cable. The server should be connected to ethernet cable for speed. 
</p>
<p>
- You will have to search for how to start up your computer's boot menu key. In my case, it's F12. You should eventually get a screen that says "Try install Ubuntu Server" or similar, and click it.
</p>
<p>
  <img src="" width="600" alt=""/>
</p>

<strong>Network configuration</strong>
<p>
- Here, we are being asked to configure our network interface. You see that there is a given DHCP and subnet. If we leave it this way, it may allow the IP address of the server to change, which we don't want. A server should always have a static IP address, so devices will always find the server. Select network interface > click enter > go down to edit IPv4 > enter > go to manual. Fill in your network information.
</p>
<p>
   <img src="" width="600" alt=""/>
</p>
<p>
- Proxy configuration: leave it blank, press enter for done. 
  <img src="" width="600" alt=""/>
</p>
<p>
- Ubuntu archive mirror configuration: press enter. If you get an error, that means something went wrong with the static IP address configuration, so just go back and fix it, otherwise, click enter.
</p>
<p>
  <img src="" width="" alt=""/>
</p>
<p>
- Guided storage configuration: Use the entire disk. The decision is yours to select ot unselect "set up this disk as an LVM group". An LVM group is part of Logical Volume Manager, a system in Linux that makes managing disk storage more flexible. So instead of splitting your disk into parititions, LVM lets you pool your storage together and then split it up however you want. Click enter done.
</p>
<p>
  <img src="" width="" alt=""/>
</p>
<p>
- Storage configuration: just click enter and continue.   
</p>
<p>
  <img src="" width="" alt=""/>
</p>
<p>
- Profile configuration: You will be asked to to create an account and name your server. Hit enter once you finish.
</p>
<P>
  <img src="" width="" alt=""/>
</P>
<p>
- Upgrade to Ubuntu Pro: You can just skip for now unless you have a Ubuntu Pro License.
</p>
<p>
  <img src="" width="" alt=""/>
</p>
<p>
- SSH Configuration: If you want to be able to access this server remotely asap put an x in the "Install OpenSSH server". You will have SSH access, which means you will have remote access from another computer to connect to your server.
</p>
<p>
  <img src="" width="" alt=""/>
</p>
<p>
- Featured server snaps: These are just features you can install on your server if you want, but I'm going to just skip and select done because I'll be installing features later.
</p>
<p>
  <img src="" width="" alt=""/>
</p>
<p>
 Once you see the installation is complete, you will see the option to reboot. Select "Reboot Now", finally remove the USB flash drive and press enter. You will be able to log in when reboot is complete.
</p>
<br />
