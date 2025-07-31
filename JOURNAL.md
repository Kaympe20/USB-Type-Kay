---
title: "USB Type-Kay"
author: "Kaympe20 aka @Kayla"
description: "A USB Hub powered with a USB-C Port"
created_at: "2025-7-31"
---

## July 31, 2025

I started off looking at [this](https://jams.hackclub.com/batch/usb-hub) jam made by [@msw](https://github.com/maxwofford)

![](https://hc-cdn.hel1.your-objectstorage.com/s/v3/99a96ed80275812ae7c15caf5343277840c08330_image.png)

I wanted to to have each of the ports have more power though so that it didn't mess with devices meant for the full 500mA. I originally thought I would need USB-PD, but the 3A from legacy mode should be enough for 4 ports at 500mA each.

So I started making what I saw in the guide, with the difference that I added a USB-C recepticle and added diodes on both kinds of power supply so that it could still function as a passive USB hub when unplugged, without shorting out the port its in when the power is plugged in.

![](https://hc-cdn.hel1.your-objectstorage.com/s/v3/90944e5684d725901eca074a3f82692c536e9fad_image.png)

I went a little bit further and filled in all of the USB ports, as well as the rest of the connections. As far as I know, this is everything needed on the schematic side

![](https://hc-cdn.hel1.your-objectstorage.com/s/v3/7477a175ae846890a98b62421d90ded01f50c5cd_image.png)

Time Spent: 1.5hr

---

To get started with PCB design, I attached footprints to everything.

![](https://hc-cdn.hel1.your-objectstorage.com/s/v3/0e93213db27885aecc5245ecd4c0d659ac89c513_image.png)

KiCAD did not include many of these and I had to use a tool called [`easyeda2kicad`](https://github.com/uPesy/easyeda2kicad.py) to download the footprints from LCSC and import them into KiCAD

![](https://hc-cdn.hel1.your-objectstorage.com/s/v3/8fa92e4895e9abf85d6ff947d2ef88abc60bfd42_image.png)

I took a look at the 3D viewer and realized a lot of the 3d models were incorrect or missing, which means I have to go manually get them to work.

![](https://hc-cdn.hel1.your-objectstorage.com/s/v3/5ccff665446bdb0b232bcfbe85958d505c4d90bf_image.png)

I then got to work on the actual PCB. I've heard USB requires the data plus and data minus pins to be differential, but KiCAD doesn't allow differential for things that don't end in N and P or + and - so I had to rename all of the nets, *one by one*.

![](https://hc-cdn.hel1.your-objectstorage.com/s/v3/d52c76c2662e49d50c6016b878ec2de0d86b0787_image.png)

I made a GND fill on the bottom and a 5V fill on top, mostly to be more efficient, and also to give the USB signaling less noise.

Here's what it looks like so far:

![](https://hc-cdn.hel1.your-objectstorage.com/s/v3/1b8165370dd151c7c1a2248bbb65c5bc90504e4f_image.png)

It looks a little bland so we should add in some nice customization

![](https://hc-cdn.hel1.your-objectstorage.com/s/v3/26db5873698f60bcc6e66b93ff41ded70abf8520_image.png)

Here's what it looks like in 3D:

![](https://hc-cdn.hel1.your-objectstorage.com/s/v3/e596435dc2f86b6917198a8cccae4fb1734b63cf_image.png)