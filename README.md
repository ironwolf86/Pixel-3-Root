# Pixel-3-(blueline)-Root

- Prerequisites:
    - [Latest SDK Platform Tools](https://developer.android.com/studio/releases/platform-tools#downloads) - if Platform Tools is out of date, you WILL run into problems!
    - [Google USB Driver installed](https://developer.android.com/studio/run/win-usb)
    - [Pixel 3 Factory Images](https://developers.google.com/android/images#blueline)
    - [Magisk Stable](https://github.com/topjohnwu/Magisk/releases/)
    - [TWRP img and zip files](https://dl.twrp.me/blueline/)
    - []()    

## Part 1 - Unlock the Google Pixel 3's Bootloader

---

### On Pixel 3 Device

1. Open the **Settings** app.
    - Go to **About phone**.
    - Scroll down and tap on ***Build number*** seven times until it says you're now a developer.

![](https://github.com/ironwolf86/Pixel-3-Root/blob/main/media/Google-Pixel-3-XL-Unlock-Bootloader-Step-1.jpg)

2. Go back to **Settings** home page and near the bottom of the list, you should see **System**. 
    - Under **System** near the bottom of the list tap **Developer options**.
3. Without scrolling down, you should see an ***OEM unlocking*** option. **Enable** it. For security purposes, it may ask you to input your lock screen PIN/password if you have one set.

![](https://github.com/ironwolf86/Pixel-3-Root/blob/main/media/Google-Pixel-3-XL-Unlock-Bootloader-Step-3.jpg)

4. Scroll down a bit until you see ***USB debugging***. **Enable** it.

![](https://github.com/ironwolf86/Pixel-3-Root/blob/main/media/Google-Pixel-3-XL-Unlock-Bootloader-Step-4.jpg)

5. Plug in your Pixel 3 into your PC using a USB to UsC-C data cable. Change the USB mode to “file transfer (MTP)” mode. Some OEMs may or may not require this, but it's best to just leave it in this mode for general compatibility.

---

### Install the SDK platform tools

**Windows 11**

1. Download the latest [Android SDK Platform Tools ZIP file for Windows](https://dl.google.com/android/repository/platform-tools-latest-windows.zip).
2. Extract the contents of this ZIP file into an easily accessible folder (such as ***C:\platform-tools***).

---

### Install the Google USB driver

**Windows 11**

To install the **Google USB driver** on Windows 11 for the first time, do the following:

1. Download the latest [Google USB Driver](https://dl.google.com/android/repository/usb_driver_r13-windows.zip) and extract files to ***platform-tools***.
2. Connect your Android device to your computer's USB port.
3. From Windows Explorer, open **Computer Management**.
4. In the **Computer Management** left pane, select **Device Manager**.
5. In the **Device Manager** right pane, locate and expand **Portable Devices** or **Other Devices**, depending on which one you see.
6. Right-click the name of the device you connected, and then select **Update Driver Software**.
7. In the **Hardware Update wizard**, select **Browse my computer for driver software** and click **Next**.
8. Click **Browse** and then locate the USB driver folder. For example, the Google USB Driver is located in ***C:\platform-tools\usb_driver\***.
9. Click **Next** to install the driver.

---

### Update Windows drivers

1. Open Windows File Explorer and browse to where you have the **platform-tools** folder stored. (C:\platform-tools)
2. Open up a Command Prompt from the same directory as the ADB executable. This can be done by holding Shift and right-clicking within the folder and then clicking **Open in Terminal**.
3. In the Command Prompt window, enter the following command to launch the ADB daemon:
```
adb.exe devices
```
On your phone's screen, you should see a prompt to allow or deny USB Debugging access. Naturally, you will want to grant USB Debugging access when prompted (and tap the always allow check box if you never want to see that prompt again).

4. Finally, in the Command Prompt window re-enter:
```
adb.exe devices
```
If everything was successful, you should now see your device's serial number in the command prompt window.

5. Now, reboot to the bootloader menu. You can either do this by holding the power and volume down buttons while booting up, or by entering the following ADB command:
```
adb.exe reboot bootloader
```
6. Windows Update (Check for updates) > Advanced Options > Optional Updates. Install `LeMobile - Other hardware - Android Bootloader Interface`. Restart Windows.
7. Turn phone on by pressing power button with the appropiate selection on bootloader screen. Ensure adb debugging is enabled once again and the device shows up after using `adb.exe devices`. Enther the following command to reboot into EDL mode:
```
adb.exe reboot edl
```
8. Restart phone. Windows Update (Check for updates) > Advanced Options > Optional Updates. Install `Qualcomm Incorporated - Ports - 3/25/2016 12:00:00 AM - 2.1.2.2`. Restart Windows.
9. Ensure adb debugging is enabled once again and the device shows up after using `adb.exe devices`. Enther the following command to reboot to bootloader:
```
adb.exe reboot bootloader
```
10. Once you're on the bootloader menu, you'll now have to switch to using fastboot command to communicate with your device. To unlock the Pixel 3's bootloader, enter the following command:
```
fastboot.exe flashing unlock     
```
11. You should now see text on screen warning you about the potential risks of unlocking the bootloader. On the screen next to the power and volume buttons, you should see some text. Press the volume up key until it says "**unlock the bootloader**." Once it says this, press the power button.

![](https://github.com/ironwolf86/Pixel-3-Root/blob/main/media/Unlock-Google-Pixel-3-Bootloader-768x1024.jpg)

12. The phone will unlock the bootloader and reboot back to the bootloader menu. This time, the bootloader will show a red warning icon and "unlocked" text.
13. Now, reboot your phone back to the Android 12 OS. You can do this by sending the following fastboot command:
```
fastboot reboot
```
Congratulations, your Google Pixel 3 now has an unlocked bootloader! You'll see a warning message that your phone's bootloader is unlocked on every boot, but don't worry about that as it doesn't affect your day-to-day use. 

---

## Part 2 - Rooting the Google Pixel 3 with Magisk

With an unlocked bootloader, you can now boot modified boot images. For Magisk to work, you'll need to patch the Pixel 3's boot image. The easiest way to do this is to install a custom recovery like TWRP to your device so you can use the Magisk installer script.

1. Since your device has been wiped, you'll need to go back and re-enable Developer Options and then re-enable USB Debugging. Make sure your Pixel 3 is still recognized by your PC.
2. 




adb kill-server

adb pull /sdcard/Download/magisk_patched_[random_strings].img

[Pixel 3 Factory Image (SP1A.210812.016.C1)](https://dl.google.com/dl/android/aosp/blueline-sp1a.210812.016.c1-factory-b41403db.zip)

Root Checker by joeykrim

https://twrp.me/google/googlepixel3.html

https://flash.android.com/


### Unroot

https://www.youtube.com/watch?v=Khy6Mh_Q4jc



Prepare your device

Before you can flash a build to your device, you must prepare your device:

    Enable Developer options and USB debugging.
    Enable OEM Unlocking in the Developer options menu. If your bootloader is already unlocked, this option is grayed out with Bootloader is already unlocked.

If you're having trouble enabling OEM Unlocking, make sure:

    Your device is connected to the internet.
    Your device has checked in with Google, which may not be the case just because your device recently connected to the internet. To force a check in, enter *#*#CHECKIN#*#* (*#*#2432546#*#*) in the Dialer (no SIM required). After entering the number (no need to press call), the text disappears and a success notification appears.

