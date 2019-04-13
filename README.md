# Introduction
> The EFI allows the XPS 9570 to work in a Mojave environment. Most of this configuration is based on [Xigtun](https://github.com/Xigtun/xps-9570-mojave), [bavariancake](https:/ /github.com/bavariancake/XPS9570-macOS) EFI borrowed from two friends, and 807133286 friends provided very timely partial updates. Here, I would like to thank them for their selfless help and dedication. I summarized the advantages and disadvantages of the configuration of Xigtun and bavariancake, as follows:

## Xigtun
 ### Advantages
 * Unlock most advanced gestures on the trackpad
 * Support touch screen
 * Normal brightness
 * Support typec conversion to HDMI\DP output
 ### Disadvantages
 * Sleep wakes up black screen
 * Unable to drive native sound card
 * config is too redundant
 
## bavariancake
 ### Advantages
 * Support sleep

 ### Disadvantages
 * Trackpad does not support advanced gestures
 * Does not support screen touch
 * DSDT loading method has an error
 
## My improvement
Of course, the above configuration can already make several versions of XPS 9570 work normally, but there is still a gap from the real fawlessly. I am committed to the integration of the above two work results, get a perfect configuration. Under the `Mojave 10.14.3` version, my configuration solved the following problem:

 * Support Typc external monitor output
 * Support sleep and wake up
 * Support for native sound card drivers
 * Support trackpad gestures and screen touch
 * Less DSDT loading errors
 * Use CpuFriend to inject the frequency conversion information of Macbook pro 15.1
 

# Hardware Configuration
 ## Driven
  * Machine :Dell XPS 9570
  * CPU: Intel i7-8750H
  * GPU: UHD630 +
  * RAM: 16GB RAM
  * Display: 4K Sharp Display
  * SSD: PC401 NVMe SK hynix 512GB SSD
  * Audio: Realtek ALC298
  * Touchscreen
  * WLAN + Bluetooth : DW1830 (replaced)
 ## not driven
  * Killer 1535 (no solution)
  * Goodix fingerpint reader (no solution)
  * Nvida Geforce 1050Ti (no solution, blocked)

# Software Environment
 * BIOS: 1.7.0, 1.5.0
 * Mojave 10.14.3 + Windows 10 1809 system
 * macOS: 10.14.2, 10.14.3

# Instructions
 * Put CLOVER into the EFI partition and use config_install.plist to complete the installation.
 * Run `sudo kextcache -i /` rebuild cache after entering the desktop
 * Enable display acceleration with config.plist
 
 `config_10.14.4.plist` was prepared for my friend who wanted to upgrade version 10.14.4. I have not been able to test because of limited energy. I am looking forward to feedback.

# Known issues
 * After wake-up from sleep, Bluetooth is randomly unavailable.
 * HDMI output is invalid
 * -v mode cannot enter the system
 * Restart the icon that causes the battery status to display the battery level and it needs to be turned back on.
 
#待测试
 * Lightning three interface
 * Models other than 4k and 8750H
 * Run on 10.14.4
 
# About this machine
![About this machine](https://github.com/LuletterSoul/Dell-XPS-15-9570-macOS-Mojave/raw/master/screenshots/About%20My%20Machine.png)
[Nvme SSD] (https://github.com/LuletterSoul/Dell-XPS-15-9570-macOS-Mojave/raw/master/screenshots/NVME.png)
![集显](https://github.com/LuletterSoul/Dell-XPS-15-9570-macOS-Mojave/raw/master/screenshots/Graphic.png)
![USB3.1](https://github.com/LuletterSoul/Dell-XPS-15-9570-macOS-Mojave/raw/master/screenshots/USB3.1.png)
![Battery](https://github.com/LuletterSoul/Dell-XPS-15-9570-macOS-Mojave/raw/master/screenshots/Battery.png)
[DW1830 Bluetooth] (https://github.com/LuletterSoul/Dell-XPS-15-9570-macOS-Mojave/raw/master/screenshots/DW1830%20Bluetooth.png)
![DW1830 Wifi](https://github.com/LuletterSoul/Dell-XPS-15-9570-macOS-Mojave/raw/master/screenshots/DW1830%20Wifi.png)
![Native Management] (https://github.com/LuletterSoul/Dell-XPS-15-9570-macOS-Mojave/raw/master/screenshots/Extention.png)
![inverter](https://github.com/LuletterSoul/Dell-XPS-15-9570-macOS-Mojave/raw/master/screenshots/Intel%20Turbo%20Boost.png)

#声明
I tried to upgrade directly to upgrade 10.14.4 and it failed. Therefore, I chose to stay at 10.14.3 (18D42). In this version, the machine works very well. I hope that the friends who are willing to try to upgrade to 10.14.3 and higher to test, I hope more friends can join in. Let the XPS 9570 achieve true Hackintosh!

If you need to post this EFI or reprint it to others, please indicate my source, as well as [Xigtun] (https://github.com/Xigtun/xps-9570-mojave), [bavariancake](https://github. Com/bavariancake/XPS9570-macOS) warehouse address, do not use
Commercial activity! Respect open source! Your cooperation and support is the driving force for our continuous maintenance and sharing.
