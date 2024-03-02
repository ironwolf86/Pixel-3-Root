# Pixel-3-(blueline)-Root

- Prerequisites:
    - [Latest SDK Platform Tools](https://developer.android.com/studio/releases/platform-tools#downloads) - if Platform Tools is out of date, you WILL run into problems!
    - [Google USB Driver installed](https://developer.android.com/studio/run/win-usb)
    - [Pixel 3 Factory Image (SP1A.210812.016.C1)](https://dl.google.com/dl/android/aosp/blueline-sp1a.210812.016.c1-factory-b41403db.zip)
    - [Magisk Stable](https://github.com/topjohnwu/Magisk/releases/download/v27.0/Magisk-v27.0.apk)
    - []()
    - []()    

## Part 1 - Unlock the Google Pixel 3's Bootloader

1. Open the `Settings` app.
2. Go to `About phone`.
3. Scroll down and tap on `Build number` 7 times until it says you're now a developer.
![](https://github.com/ironwolf86/Pixel-3-Root/blob/main/media/Google-Pixel-3-XL-Unlock-Bootloader-Step-1.jpg)
5. Go back to `Settings` home page and near the bottom of the list, you should see `System`. 
6. Under `System` near the bottom of the list tap `Developer options.`
7. Without scrolling down, you should see an `OEM unlocking` option. Enable it. For security purposes, it may ask you to input your lock screen PIN/password if you have one set.
![](https://github.com/ironwolf86/Pixel-3-Root/blob/main/media/Google-Pixel-3-XL-Unlock-Bootloader-Step-3.jpg)
9. Scroll down a bit until you see `USB debugging`. Enable it.
![](https://github.com/ironwolf86/Pixel-3-Root/blob/main/media/Google-Pixel-3-XL-Unlock-Bootloader-Step-4.jpg)
10. Plug in your Pixel 3 into your PC using a USB to UsC-C data cable. Change the USB mode to “file transfer (MTP)” mode. Some OEMs may or may not require this, but it's best to just leave it in this mode for general compatibility. 

---

1. Download the latest [Android SDK Platform Tools ZIP file for Windows.](https://dl.google.com/android/repository/platform-tools-latest-windows.zip)
2. Extract the contents of this ZIP file into an easily accessible folder (such as C:\platform-tools). 
3. Open File Explorer and browse to where you extracted the contents of this ZIP file. 
4. Open up a Command Prompt/Terminal instance from the same directory as this ADB executable. This can be done by holding Shift and right-clicking within the folder and then clicking `Open command window here` or `Open PowerShell window here`. Windows 11 users should see `Open in Terminal` in the right-click context menu without even pressing the Shift button on the keyboard.
5. In the Command Prompt/Terminal window, enter the following command to launch the ADB daemon:
```
adb.exe devices
```
On your phone's screen, you should see a prompt to allow or deny USB Debugging access. Naturally, you will want to grant USB Debugging access when prompted (and tap the always allow check box if you never want to see that prompt again).

6. Finally, re-enter:
```
adb.exe devices
```
If everything was successful, you should now see your device's serial number in the command prompt/Terminal window.

7. Now, reboot to the bootloader menu. You can either do this by holding the power and volume down buttons while booting up, or by entering the following ADB command:
```
adb reboot bootloader
```
8. Once you're on the bootloader menu, you'll now have to switch to using fastboot command to communicate with your device. To unlock the Pixel 3's bootloader, enter the following command:
```
fastboot flashing unlock     
```
9. You should now see text on screen warning you about the potential risks of unlocking the bootloader. On the screen next to the power and volume buttons, you should see some text. Press the volume up key until it says "unlock the bootloader." Once it says this, press the power button.
![](https://github.com/ironwolf86/Pixel-3-Root/blob/main/media/Unlock-Google-Pixel-3-Bootloader-768x1024.jpg)
10. The phone will unlock the bootloader and reboot back to the bootloader menu. This time, the bootloader will show a red warning icon and "unlocked" text.
11. Now, reboot your phone back to the Android 12 OS. You can do this by sending the following fastboot command:
```
fastboot reboot
```
Congratulations, your Google Pixel 3 now has an unlocked bootloader! You'll see a warning message that your phone's bootloader is unlocked on every boot, but don't worry about that as it doesn't affect your day-to-day use. 

---

1. 










