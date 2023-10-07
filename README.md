# How to install and use Windows Vista on a Windows 11 PC in 2023

[Windows Vista](https://en.wikipedia.org/wiki/Windows_Vista) is no longer maintained since 2012 (mainstream) or 2017 (extended). It has been difficult to find hardware and software now (2023) to install and run Windows Vista, for whatever reasons you like.

However, it is still possible to do so in 2023 and run it on a virtual machine on a Windows 11 PC. Key takeways TL;DL:
- Use VMWare Workstation Play version 11.0 as newer versions (11.1+) no longer support graphic acceleration.
- Windows Update endpoint has stopped supporting SHA-1, so we need a workaround to proxy the endpoint.

In this tutorial, we assume the host OS is Windows 11 on a modern PC. For me, it is 13th-gen Intel processor. All modern CPU should support hardware virtualization, but just make sure to turn it on in BIOS.

## Step 1: Obtain a licensed copy of Windows Vista

You can find this item in various ways. I purchased a retail package from eBay for $30. It includes a 32-bit installation media in DVD and genuine activation key.

![](https://github.com/goldsail/install-windows-vista-in-2023/blob/main/Media.jpeg)

You need either ISO image for the installation media, or a (USB or internal) DVD driver for the physical disc.

## Step 2: Install VMWare Workstation Play 11.0

[It is known that](https://kb.vmware.com/s/article/75163) VMWare 11.1+ no longer supports Windows Vista SP2. So, we need to install VMWare 11.0 on our host.

Go to VMWare [official website](https://customerconnect.vmware.com/downloads/details?downloadGroup=WKST-1100-WIN&productId=462). You can sign up for free and then install version 11.0. The WorkStation Play edition is free for non-commercial use, so we are going for that one.

## Step 3: Install Windows Vista RTM and Service Packs

First, create a virtual machine in VMWare and install Windows Vista. Use default values for most settings, and make sure to turn on CPU virtualization.

![](https://github.com/goldsail/install-windows-vista-in-2023/blob/main/CPU_settings.png)

Then, download and install both service packs. You might need to download in host OS and attach the ISO image to the guest OS.
- [Service Pack 1](https://www.microsoft.com/en-us/download/details.aspx?id=13158)
- [Service Pack 2](https://www.microsoft.com/en-us/download/details.aspx?id=5104)

After reboot, install the VMWare Tool 11.0 in the guest OS. This makes sure graphic acceleration and virtual network adaptor can work, so that it can turn on Windows Aero.

## Step 4: Work around Windows Update error 80072EFE

There is [a known issue](https://support.microsoft.com/en-us/topic/windows-update-sha-1-based-endpoints-discontinued-for-older-windows-devices-10b58bd9-5ba2-b23d-498b-139ce5c709af) with Windows Update because Microsoft has stopped offering deprecated SHA-1 based endpoint. Windows Vista and Windows 7 are affected. There is an official patch for Windows 7 to mitigate this issue, but unfortunately, we need some manual workaround for Windows Vista.

I highly recommend watching [Julia's Tech Spot](https://www.youtube.com/watch?v=6Thnymnrf18)'s YouTube video for this. Basically, it requires installing 4 standalone Windows Update `.msu` patches, running a Regstry script, and a reboot. You may download the files from the links in video description, or in the release folder of this repo.

Now, turn on Windows Aero and enjoy the time travel back to 2006.

![](https://github.com/goldsail/install-windows-vista-in-2023/blob/main/Screenshot.png)

## Final notes

Time is an enemy of all of us. The worse type of nostalgia isn't about a place of memory, but about a period of time, the lifecycle of something. For security reasons, I do not recommend using Windows Vista in year 2023, even in a virtual machine, but it means something special to me. The first computer in my childhood came with Windows Vista. It was slow, crashing a lot, but it led me to a new world. Today, all I need is to play a few games of Spider Solitaire on Windows Vista.

Thank you for reading this tutorial and wish you a good day!
