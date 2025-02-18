# Part 4 - Joining A PC To A Domain

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

<img src="https://i.ibb.co/27HPrymD/17-Region.png">

Then, Windows will ask you if the keyboard is the correct layout for you. Once again, just confirm that it's the correct layout, and click Yes. 

<img src="https://i.ibb.co/kV9gCQ8g/18-Right-Keyboard.png">

The next screen will ask if you want to add a second keyboard layout. In our case, we don't, so we press skip. 

<img src="https://images2.imgbox.com/7b/3b/gVFzQFrv_o.png">

The next screen will ask us how we want to set up the computer. The two options are: "Set up for personal use", or "Set up for an organization". For our purposes we are gping to do the set-up for personal use, but keep in mind that some organizations actually set it up for an organization.

<img src="https://images2.imgbox.com/2d/51/LFHVcN4w_o.png">

The next screen will prompt you to add your account. We want to use an offline account, so we will press the button on the left that says "Offline account". 

<img src="https://i.ibb.co/99bMLcPJ/21-offline-account.png">

We then are prompted to sign in, but we don't need to sign in. So, we are going to press "Limited experience". 

<img src="https://i.ibb.co/WN9WRv3T/22-Limited-experience.png">

Now, it will prompt us to create an account. In this case, we are going to use the name user. Type "user" in the box.  

<img src="https://images2.imgbox.com/b1/75/5zIvrNkK_o.png">

The next prompt will ask you to create a password. Since we are going to activate and admin account later, we are just going to press the Enter key or press Next. 

<img src="https://images2.imgbox.com/be/2e/oKRIbSUJ_o.png">

The next 4 screens will just ask questions about services that are available in Windows. Feel free to answer based on personal preference. 

Finally, you are greeted with the Windows operating system. A network question may appear, asking if you want your PC to be discoverable by other PCs and devices on the network. You can press yes. That concludes setting up Windows 10. 

> Although the process may seem different visually, many of these principles apply to setting up a Windows 11 computer.

## Activating Administrator Account on Desktop
To activat the Admin account in the desktop, open file explorer. Right-click on This PC, and click Manage. 

<img src="https://images2.imgbox.com/4a/e1/BVgrzVPS_o.png">

Under System Tools, Open Local Users and Groups by double-clicking the icon. Open the Users folder. On the right, you will see various accounts. Right-click on the administrator account, and click Properties. 

<img src="https://images2.imgbox.com/9b/c8/pvw5YHxA_o.png">

On the Administrator Properties pop-up menu, undo the checkbox called Account is Disabled. Click Apply and press OK.

<img src="https://images2.imgbox.com/77/2c/ks100wpg_o.png">

## Changing Administrator Password
To change the administrator password, right-click on the administrator account and click Set Password. 

<img src="https://images2.imgbox.com/21/a1/pitqCxIn_o.png">

A warning will pop-up. This is basically telling us that for security reasons, any previous information stored in the administrator account will be deleted. However, since we haven't set up any password, we can ignore this warning. Press Proceed. 

<img src="https://images2.imgbox.com/20/f7/wzFyYikg_o.png">

Next, create a password that is easy to remember. Confirm the password, and press OK.

<img src="https://images2.imgbox.com/b8/07/VN5kPhBH_o.png">

A pop-up will say that the Password has been set. Just press OK. 

Now, right click on the user named "user", and click Delete.

<img src="https://images2.imgbox.com/5b/1b/KUQBU3pl_o.png">

Confirm that you want to delete the user, and press OK. 
