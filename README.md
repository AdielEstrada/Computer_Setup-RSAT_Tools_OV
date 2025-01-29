# Part 4 - Setting Up A Computer With RSAT Tools, and Joining It To A Domain

> [!NOTE]
> Have the server environment open and be logged in as administrator.

## Setting Up A Static IP Address in Server Environment
We will be setting up a static IP address in the server because it will be easier for this server to be discoverable by the devices that we will be setting up. Not only that, but I didn't buy a domain. If this were to be a real environmnent, there could be legal issues, since I don't own the domain "adielit.local". So, to do this, open control panel from the start menu or through the search bar. 

<img src="https://i.ibb.co/0hhXk6J/1-Open-control-panel.png">

Under network, go to "View Network Status and Tasks". We will be looking for an option called "Change Adapter Settings". Click that option.

<img src="https://i.ibb.co/0Gmskf7/2-view-network-status-and-tasks.png">

Then, you will see something pop-up with a label called "Ethernet". Double-click on that.

<img src="https://i.ibb.co/p05nNqd/3-Ethernet.png">

From here, we will want to go to properties to change the IP address of the computer.

<img src="https://i.ibb.co/Prb4mcs/4-Properties.png">

You will see various settings, but for now, we only want to concentrate on the one that says, "TCP/IPv4". Double-click on the icon beside it. 

<img src="https://i.ibb.co/tptDq04/5-Change-ip-address.png">

A screen that shows the IP address of the device will be shown. Once it pops up, you will see that the settings that are there by default are to get an IP address and DNS server automatically. We want to change it so that we could access the server through an easily identified IP address. So, to change it, click on "Use the following IP address" and "Use the following DNS server addresses". Enter an IP address, just like shown in the following image. 

<img src="https://i.ibb.co/GH3103V/6-Change-settings.png">

We can press OK, and exit out of everything. Now, for our VM to recognize the change and be better able to communicate with other computers, we can go to the "Devices" tab of VirtualBox. Under devices, go to "Network" and "Network Settings". Change the drop-down option to "Host-only adapter". This option will allow the VM to communicate with other VMs that we create, but not to an outside network. 

<img src="https://i.ibb.co/0KrDDVx/6-Change-adapter-settings.png">

Once that is done, you can press OK, and exit out of everything. 

## Setting Up Windows 10
> Open your browser and download the Windows Media Creation Tool. Open it and create an ISO file to download Windows 10. Store it in your desktop to have easy access as you will need this later. 

Create a new Windows 10 VM, and name it something easy to remember. An example could be "Desktop1" or "Windows 10 Desktop". Leave everything as default, and make sure you are going to boot the system manually. 

Then, once you are ready, a boot screen will pop-up, telling you to mount a file to boot the VM. Choose the drop-down arrow to browse the available files. Choose the Windows.iso file that you have downloaded. Then, click "Mount and Retry Boot"

<img src="https://i.ibb.co/5YJcvNR/8-Mount-and-retry-reboot.png">

Windows will boot, and a screen telling you to choose your language will pop-up. We can click Next. 

<img src="https://i.ibb.co/p1JJSCt/9-Windows-10-next.png">

Then, a Windows Setup screen pops-up. We can click "Install Now". 

<img src="https://i.ibb.co/5M91GdS/10-Install-now.png">

An Activate Windows screen will show. We won't need a product key for the intallation, so click "I don't have a product key". 

<img src="https://i.ibb.co/0VFZfBK/11-I-don-t-have-a-product-key.png">

The Windows Setup screen will now prompt you to select an operating system. For our purposes, we need to use Windows 10 Pro, since this operating system allows us to join a computer to the domain, and will allow us to experiment with more features of the server environment we have created. So, click on Windows 10 Pro, and click Next. 

<img src="https://i.ibb.co/yqQrDZw/12-Chose-windows-10-pro.png">

Then, accept the license agreement, and click Next. 

<img src="https://i.ibb.co/5BXQPfF/13-Accept-license-agreement.png">

The Windows Setup screen will ask you what type of installation you want to perform. Since Windows isn't installed, you have to do a custom install. So, click on "Custom".

<img src="https://i.ibb.co/840K7yfZ/14-Custom-install.png">

We don't have to do anything in the next screen because we don't need to do a partition in this case. So we click next.

The Windows setup screen will finish with a screen called Installing Windows. You will see a few tasks that the computer is undertaking. 

Once the computer is getting to restart, you should right-click on the disk icon in the right bottom area of the VM. Click on an option to remove the disk. If you would be doing this on a physical computer, this would be the equivalent of removing the USB with the boot files. 

<img src="https://i.ibb.co/Q37PkrSx/16-Remove-drive.png">

Then, Windows will guide you through the setup process, just like if you were unboxing a new computer. First, it asks for your region. In our case, the region is right, so we click Yes.

Then, Windows will ask you if the keyboard is the correct layout for you. Once again, just confirm that it's the correct layout, and click Yes. 


The next screen will ask if you want to add a second keyboard layout. In our case, we don't, so we press skip. 

The next screen will ask us how we want to set up the computer. The two options are: "Set up for personal use", or "Set up for an organization". For our purposes we are gping to do the set-up for personal use, but keep in mind that some organizations actually set it up for an organization.
