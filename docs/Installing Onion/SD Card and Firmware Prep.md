---
title: SD Card and Firmware Prep
layout: default
nav_order: 3
parent: Start Here
---

# Format Your SD Card
* If you’re on **Windows**, use [fat32format](https://github.com/OnionUI/Onion/wiki/fat32format) to format your card. Alternatively, you can use [Rufus](https://rufus.ie/en/).

{: .warning }
If you get an error message mentioning the SD Card is currently in use by another process, make sure you don’t have it open on your file browser, then hit `Ctrl`+`Alt`+`Del` to open the Task Manager, look for and kill the `Windows Explorer` process by right-clicking it and selecting `End Task`, then go to `File` > `Run New Task`, input `"explorer.exe"` in the command field and hit `Enter`. Then try again.

* If you’re on **Mac**, use Disk Utility which you already have installed. [Here’s specific instructions](https://github.com/OnionUI/Onion/wiki/macos-disk-utility). **Remember to use fat32, not exfat**.

* If you’re on **Linux**, you can use [gparted](https://artiya4u.medium.com/formatting-usb-flash-drive-for-macos-on-ubuntu-f445c6b052bb) to format your SD card to FAT32.

# Update Your Firmware (MM+)

{: .warning }
When upgrading your firmware there's always a risk of bricking your device. Be sure to follow the instructions below carefully, as doing so incorrectly can heighten said risk.

{: .note }
A Note for Miyoo Mini (non-Plus) users: The version numbers and downloads mentioned in this section **do not apply to you**. For the regular Miyoo Mini, you want to be on a version starting with `20220419`. If you’re not, check the [Installation Instructions on the Onion wiki](https://github.com/OnionUI/Onion/wiki/Installation) for next steps.

1. Check your Miyoo Mini Plus’ firmware version (Turn it on and go into `Settings` > `About Device`; you don’t need to have an SD inserted to do this). You want the version number to start with `20230505` or `202306`. If it does, your firmware is up to date and you can skip to the next section ([Install Onion](http://miyooguide.fireblend.com/docs/Installing%20Onion/Installing%20Onion.html)).

2. If you need to update, download [this ZIP file](https://app.sugarsync.com/iris/wf/D4978471_09235444_029620#cGFnZUlkPXdlYmxpbmtzJmlzV2VibGlua3NGb2xkZXI9dHJ1ZSZpc0l0ZW1SZWZyZXNoQWxsb3dlZD10cnVlJnVzZXJJZD0tMSZjdXJyZW50T3duZXJJZD05NDIzOTI2JmN1cnJlbnRGb2xkZXJJZD01NDc4MDk5OV81NzQxNzUmY3VycmVudEZvbGRlck5hbWU9TUlOSStQTFVTJTIwMDYwOSZ3ZWJsaW5rSWQ9RDQ5Nzg0NzFfMDkyMzU0NDRfMDI5NjIwJnRva2VuVGltZT0xNjkyNzEzNTM0NTIxJmNzcmZ0b2tlbj1jYTY1Mzk0Yi1lODg1LTQ4YjEtYjkyNi1iNzUwNGE2YmEyZDcmbW9kZT0=), grab the file that ends in `.img` (i.e. `miyoo354_fw.img`), place it in your SD card’s root directory (should be the only file on it if you’re following this guide) and insert it into your MM+.

3. With the device turned off, connect it to your PC through USB. This will start the update process (you should see a picture of a rocket as it occurs). Once it’s over, shut down your device, remove the SD card, insert it back into your PC and delete the `.img` file.

Next: [Installing Onion](http://miyooguide.fireblend.com/docs/Installing%20Onion/Installing%20Onion.html)