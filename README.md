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
