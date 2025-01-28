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
