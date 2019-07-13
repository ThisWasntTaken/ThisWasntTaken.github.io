---
layout: post
title:  "Dual Boot Arch Linux alongside Windows 10"
date:   2019-06-27 18:10:00 +0530
---

This post will cover in detail, the process to dual boot a computer which has Windows 10 with Arch Linux. I installed Arch Linux just to understand the process of installing an OS manually, but once I fine-tuned it, I stuck with it, because its great.

# Why Arch Linux?
'Linux distros for beginners' like Ubuntu and Mint are bloated with a lot of software that we never use. Arch is on the other end of the spectrum. Nearly every single software has to be manually installed (yes, audio and wifi drivers are a couple of them xD). Once you get used to it (you will in about a month), its awesome. If you do not want to dive into Arch right now, there are other distros that are extremely similar to Arch with a user-friendly installation process like <a href="https://manjaro.org/">Manjaro</a> and <a href="https://antergos.com/">Antergos</a>. I have not installed either one, but the process is pretty similar to installing Ubuntu.

Another advantage is that Arch gets Rolling updates - you can have the latest version of software if you want. The Arch User Repository (AUR) has nearly every pckage for Linux. If it's there for Ubuntu, it's probably there for Arch. You can completely avoid using AUR if you can just install all the packages you need using pacman. Doing this and checking for updates once everyday (pacman -Syu) before you install new packages nearly ensures that you will never break your system. However, you will limit yourself doing this.

Honestly, installing Arch Linux is not as hard as it is made out to be if you have a decent hold of commands and basic  concepts like mounting, boot loaders, partioning and such. Dual Booting alongside Windows is slightly more complex, since you need to configure the boot loader (I use GRUB) to include Windows as well.

There are PLENTLY of guides to install Arch Linux on an empty drive, so I will skip that. I did find a couple of guides (<a href="https://nnserverthings.wordpress.com/2017/07/04/arch-linux-with-windows-10-dual-boot/">this</a> and <a href="http://www.linuxandubuntu.com/home/dual-boot-ubuntu-and-arch-linux/">this</a>) that helped me along in the dual-booting process but I had to troubleshoot some things on my own. Following this guide will get you a working Arch Linux alongside Windows 10. You will however, have to configure it - install a Desktop Environment (I use KDE Plasma 5), install basic tools etc.. Below is my configuration:

<img style="margin-right: 40px;" src="{{ site.baseurl }}{{ site.url }}/assets/images/archlinux_dual_boot/Desktop.png" width="375"/><img src="{{ site.baseurl }}{{ site.url }}/assets/images/archlinux_dual_boot/Apps.png" width="375"/>

# Preparation
1. **Important** : PLEASE BACKUP ALL FILES FROM WINDOWS 10 AND ANY OTHER OS YOU HAVE.<br>If you are really careful, the above step is not necessary, but recommended nonetheless for obvious reasons.

2. Create a bootable USB for Arch Linux: Download the latest iso for your system <a href="https://www.archlinux.org/download/">here</a>. Download Rufus <a href="https://rufus.ie/">here</a>. You need it to create the bootable USB. Follow the steps on this <a href="https://wiki.archlinux.org/index.php/USB_flash_installation_media">Arch Linux official site</a> to create a bootable USB using the iso you just downloaded. Please read the <a href="https://wiki.archlinux.org/index.php/Installation_guide">Installation guide</a> too, just to get an overview of what we will do.

3. **Careful** : We need to free up some space on your disk if you do not have any. Follow <a href="https://winaero.com/blog/shrink-partition-windows-10/">this</a> guide to achieve this. Be careful not to free up too much space as it will result in a loss of data. I recommend freeing up at least 20 GB.

4. Turn off secure boot (recommended) and fast startup (necessary) in Windows 10. Google this if you do not know how to.

5. Make sure you are on a wired internet connection.

# Installation
1. Power off from Windows 10, insert the bootable USB you created into a USB drive and power on. This will get you to boot into the USB. If it does not, change your BIOS boot order to have USD Diskette above Windows boot-loader.

2. Choose the Boot Arch Linux option. This will get you to a Terminal.

3. Check if you have internet.
{% highlight shell %}
ping archlinux.org
{% endhighlight %}

4. List out all your partitions.
{% highlight shell %}
fdisk -l
{% endhighlight %}