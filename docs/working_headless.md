# Working Headlessly

Headless means no keyboard, no monitor (If not, forgive my poor English). The way we access to Linux in Pi is SSH via network. To achieve it, we should:

* Setup network
* Enable SSH server in Linux.

While setup network if need Wi-Fi setup, you can need to:

* Access the Ext3 patition of the SD card from Window or Mac OSX.

Let's start step by step.

## Step 1: setup network

### Ethenet

If you have ethernet cable, conguratuation, it is mostly simple: plug the cable to Pi's enthernet port (beside the Standard A USB ports) and connect to router. Your Pi should get network connection then.

### Wi-Fi

If only Wi-Fi available, it is a little more steps.

The most straightfoward method is to modify the `/etc/wpa_supplicant/wpa_supplicant.conf` files to add follow codes in the end of file:

    network={
        ssid="Your wifi_SSID"
        psk="Your_wifi_password"
    }

You can check details in: https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md

There are some ways to modify the file:

* Use USB keyboard and HDMI monitor to modify the file with build in file edit program 'nano'. 
* If you do not have keyboard and HDMI, you can also modify the file in SD card from PC or Mac. But firstly, you need to mount the ext3 patition in SD card. Check the guide: [Mount ext3 Patition to Windows or OSX] (mount_ext3_patition.md)

## Step 2: enable SSH

It is very easy to enable SSH: put a empty file named `ssh` in root directory of the `root` patition in SD card. In OSX or Linux, just use `touch ssh`.

root is a FAT format patition that all the os system like Windows, OSX or Linux can easily mount it.

## Step 3: SSH from host OS

For SSH, an IP address is needed. You can log in to your router to find it, or use some App to scan. My favorite App is `Net Analyzer` in iOS. Which can scan all the local network addresses and show the available device and its host name.

If you have an HDMI monitor, it is even easier. The IP address can be found in the end of booting logs.

In Windows, PuTTY is a recomended terminal to SSH. I also like to use git bash, which is also a POXIS terminals. In OSX and Linux, use terminal App and type:

    ssh pi@your_ip_address

The the headless Pi is done.




