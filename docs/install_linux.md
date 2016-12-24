# Install Linux for Pi

## Preperation

###HW

* Raspberry Pi 3B
* A 8BG or 6GB Class 10 SD card
* A micro B USB cable
* A 5V power adapter which supply power > 2.1A 

Be careful the USB cable. Some low quality USB cable will infect the power supplier and affect the SD card module. It used to waste my half an day to find the root cause. To get a good USB cable and USB charger, search 'Anker' in Amazon or JD, which is the best seller in Amazon and the company I am working for.

### SW

* **RASPBIAN JESSIE LITE** , the minimal Linux OS. Off cause you can use RASPBIAN JESSIE WITH PIXEL, also a Raspbian Linux OS withGUI desktop; or NOOBOS, an "Out of Box" OS installer. Check https://www.raspberrypi.org/downloads/ for details.

* **Etcher** , a SD card burner App. Win32DiskImager is the offical suggestion. But I choose it as it is free, cross platform, open source or good compatibilities and the most important: beautiful interface.

I know a lot of Linux guys despise GUI interface and insistant working with terminal. But I believe a easier and more friendly develop enviorment can help more people start contributing to Linux community.

## Step 1: download Linux Image

Download the image from: https://www.raspberrypi.org/downloads/raspbian/. 

The most current version is: 2016-11-25-raspbian-jessie-lite.zip. Unzip to got 2016-11-25-raspbian-jessie-lite.image.

## Step 2: download Etcher

Check out the App https://etcher.io/#downloads. It will redirect automatically base on your working OS.

Unzip and install

## Step 3: burn image

Open Etcher, follow the guide: select image --> select driver --> flash. 

## Ready to enjoy

Insert SD card to Pi, plug micro USB cable. Bingo, all finished. It is easy, isn't it?

Some hints to help your work.

### LEDs

There are 2 LED beside the USB power jack. The red one indicate the power. It should always on after suppling power. If it flashs sometimes, check your cable or charger, it means the power supplier unstable.

The yellow one is the SD card access indicator. When booting, it should be flushing sometimes.

### Keyboard and Monitor

You can easily connect a monitor (or TV) to Pi with HDMI port. The drivers are already built in Raspbian.

An USB keyboard can help you start working immediately like an Linux PC. But if you have no them, don't worry, another headless method is introduced in follow sections.
