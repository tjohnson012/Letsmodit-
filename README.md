# **Quick Guide to Modding Your Nintendo Switch**

Modding your Nintendo Switch can be straightforward with the right tools and steps. Follow this guide closely for a smooth modding experience.

# **Before You Begin**
Check Compatibility: Visit ismyswitchpatched.com to verify if your Nintendo Switch is compatible with modding. Enter your serial number to check compatibility. Switches purchased in 2017-2018 are more likely to be moddable.

Green: Compatible

Red: Incompatible

Yellow: Possibly compatible (proceed with caution)

What You Need

Moddable Nintendo Switch

RCM Jig[ https://www.amazon.com/Nintendo-Switch-Short-Connector-Recovery/dp/B07J9JJRRG
Computer](url)

USB-C Cord that can connect to computer and nintendo swithch via double usb c or usb.

Micro SD Card (64GB or larger) [https://www.amazon.com/dp/B0B985Q9F1/ref=twister_B0C3KYVDWT](url)

Micro SD Card Adapter - [https://www.amazon.com/SanDisk-microSD-Memory-Adapter-MICROSD-ADAPTER/dp/B0047WZOOO/ref=sr_1_3?keywords=micro+sd+card+adapter&qid=1707769044&sr=8-3](url)

SD Card Reader - [https://www.amazon.com/Hicober-USB-Card-Reader-Camera-Android/dp/B07T55DL33/ref=sr_1_2?keywords=micro%2Bsd%2Bcard%2Badapter&qid=1707768998&sr=8-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1
](url)

Steps to Follow:

First, insert your sd card into the sd card reader, insert the sd card reader into your computer, and then format your Micro SD Card to FAT32 via Easeus [https://www.easeus.com/](url) this is required to make sure your sd card is clean and ready to go. If this isn't your first time using this micro sd card it is imparative as a old partion may exist which would intefere with the modding process as well as take up excess space.

Next, download all your required files found in the release portion of the main branch. Make sure you have EVERYTHING downloaded before you begin moving anything towards the root of your SD Card


Required Files: 
TegraRCM - [https://github.com/eliboa/TegraRcmGUI/releases](url)
Atmostphere + Fuse Bin - [https://github.com/Atmosphere-NX/Atmosphere/releases](url)
Hekate IPL - [https://github.com/CTCaer/hekate/releases](url)
Sigpatches - [https://sigmapatches.su/](url)

Extrack all the files that are zipped, and move the files (Atmosphere, Swithc, hbmw) inside of the atmosphere folder into the root of your sd card. 

Now with the hekate file, you are going to want to move the bootloader folder into the root of your sd card but NOT the hekate.ipl, you are going to want to move that somewhere where you can access it quickly such as your desktop, taskbar, or quick access folder. 

Open up the sigpatches folder and copy the bootloader and atmosphere file over to the root of your sd card. If it asks for you to replace files, replace them. 

Now go to /bootloader/payloads/ and put the fuse.bin file that you downloaded into that folder. 

Now, open up your notepad and go to this website and do as follows:

Copy this code into a blank notepad, click save as, where it says save as type under file name, you are going to want to change it from txt document to all files, and then name the file "hekate_ipl.ini"
Insert this file into /bootloader/

[config]
autoboot=0
autoboot_list=0
bootwait=3
backlight=100
autohosoff=0
autonogc=1
updater2p=0
bootprotect=0

[Atmosphere CFW]
payload=bootloader/payloads/fusee.bin
icon=bootloader/res/icon_payload.bmp

[Stock SysNAND]
fss0=atmosphere/package3
stock=1
emummc_force_disable=1
icon=bootloader/res/icon_switch.bmp

Then copy this text and repeat the previous steps but name it exosphere.ini and insert it into the root of your sd card

[exosphere]
debugmode=1
debugmode_user=0
disable_user_exception_handlers=0
enable_user_pmu_access=0
blank_prodinfo_sysmmc=0
blank_prodinfo_emummc=1
allow_writing_to_cal_sysmmc=0
log_port=0
log_baud_rate=115200
log_inverted=0

Now within your /atmosphere/ folder create a folder called hosts and then within "hosts" and you will make one more blank notepad entry with the following code and the same steps as prior but it will be named default.txt and move this into /atmosphere/hosts/ (and yes it is still all files even though it is txt)

# Block Nintendo Servers
127.0.0.1 *nintendo.*
127.0.0.1 *nintendo-europe.com
127.0.0.1 *nintendoswitch.*

95.216.149.205 *conntest.nintendowifi.net

95.216.149.205 *ctest.cdn.nintendo.net

Now go into Tegra RCM (may ask you to do installer steps, just proceed with that) and inside Tegra RCM you are going to want to click on settings and install driver. Follow the steps that it asks you and retrun to Tegra RCM

Now click on the folder where it says select payload and find the hekate.bin file that you were supposed to keep in a good place and when you click on the bin file open it up.

Now go ahead and eject your sd card by going to your file manager and right clicking on your sd card, then in the pop up menu hit eject. You may now safely remove your sd card, and whenever you want to remove your sd card make sure you eject your sd card AS YOUR FILES COULD CORRUPT AND YOU WILL HAVE TO DO THIS AGAIN AND REINSTALL EVERYTHING.

Now, make sure your switch is powered off, insert your micro sd card, and slide the rcm jig into the right joycon rail. Plug your nintendo switch into your computer via a usb-c cable and hold the power button and the volume up button. Inside Tegra RCM, it will change from a red "NO RCM" to a green "RCM OK" Now click Inject Payload. Your switch should successfully boot up hekate.

It will ask you to put the current date and time and after that you are going to want to go to Tools at the top of the screen - Partition SD Card - and you are going to want to drag the red emuMMC (RAW) slider to the middle at 29 FULL. Now click next and answer yes/continue to the questions that pop up asking if you are sure you want to continue.

Now, go to home at the top of the screen and hit emmuMMC to the very right - Create emuMMC - SD Partition - Part 1. 

After that is finished return to the home menu at the top of the screen and hit payloads - fusee.bin and now your switch is officially modded!

Go to album to view your mods.
