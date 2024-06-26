# EFI of Lenovo Ideapad 3i 15IML05 (i3-10110U) for macOS monterey, ventura and sonoma

![only banner](https://github.com/Ats0c/Lenovo_Ideapad_3i-15IML05-Hackintosh-EFI/blob/main/Images/Banner.png)

## **<br/>Remembering that the intention is to help and not steal someone else’s project!! [All credits go to the original author](https://www.olarila.com/topic/19326-efi-lenovo-ideapad-3i-15iml05-82bs0001br/)[^1].<br>**

### <br/>This configuration was adapted for the Lenovo Ideapad 3I with the i3-10100U processor so that some things work well.<br>
Opencore was updated to 1.0.0 and all kexts too

### <br/>It is now possible to update to macOS ventura and sonoma!!<br>
kext from Airportitlwm has been updated for each version of macOS

> [!IMPORTANT]
> Just pay attention to one detail, which is to update to Sonoma. Go to Misc > Security > SecureBootModel and leave it disabled, it's the only way to update to Mac OS Sonona.

> [!WARNING]
> Because SecureBootModel is disabled, you will be greeted with a black screen after upgrading to Sonoma. So, I recommend you have a Dualboot to help with this problem.

### <br/>Things that work with the original author's default configuration:<br>

  - *Webcam (Lenovo UVC Camera)*
  - *Touchpad (ELAN I2C)*
  - *HDMI (Audio + Video)*
  - *Brightness Control (F11/F12 Keys)*

### <br/>Things that work in my setup:<br>

  - *CPU (Intel Core i3-10110U)*
  - *Audio (Realtek ALC257)*
  - *USB (Comet Lake PCH-LP USB 3.1)*
  - *Sleep*
<br><br/>
 
*CPU (Intel Core i3-10110U)*
> *Now power management works perfectly, even allowing the user to see the CPU temperature and also having low power consumption*

*Audio (Realtek ALC257)*
> *Only the layout-id was corrected*

*USB (Comet Lake PCH-LP USB 3.1)*
> *It worked in the default configuration, however, it caused problems with sleep*

*Sleep*
> *Now works perfectly*

### <br/>You must put this command to make sleep work<br>
> ### ![Just to help user to configure sleep](https://github.com/Ats0c/Lenovo_Ideapad_3i-15IML05-Hackintosh-EFI/blob/main/Images/Sleep_config.png)

> [!IMPORTANT]
> It is recommended that you reset NVRAM only once after configuring sleep.

### <br/>ACPI patches I made:<br>
 - *SSDT-DATA (Working together from kext CPUFriendFriend)*
 - *SSDT-USBX*
 - *SSDT-RHUB (Just redone to avoid hardware problems)*
 - *SSDT-AWAC*
 - *SSDT-HPET*
 - *SSDT-UIAC*
 - *SSDT-RTCAWAC*

## <br/>Which SMBios should I use?<br>
Use MacBookPro13.1 SMBios
> [!NOTE]
> you can use others, but I don't guarantee that sleep will work.

## <br/>Ways to install macOS:<br>
1. **Using the image available on Olarila.com**
   - Go to [olarila.com](https://www.olarila.com/topic/6278-olarila-vanilla-images-macos-installer/) and download the macOS monterey image
   - Flash the image onto a PenDrive of at least 16GB using [Balena Etcher](https://etcher.balena.io/)
   - When the flash is finished, restart and boot from the PenDrive
   - Go to disk utility and format the storage you are going to use into "APFS" and "GUID Partition Map" and start the system installation
  
2. **Using MacRecovery**
   - Go to [macrecovery](https://github.com/luchina-gabriel/macrecovery) repository and download lastest release and unzip
   - Go to the unzipped folder, open the terminal and run this code here
     ```
     python3 ./macrecovery.py -b Mac-FFE5EF870D7BA81A -m 00000000000000000 download
     ```
   - Create a folder named com.apple.recovery.boot and copy the new files into this folder
   - Now format the PenDrive in FAT32 and copy the EFI and the folder you created to the root
   - When finished, restart and boot from the PenDrive
   - Go to disk utility and format the storage you are going to use into "APFS" and "GUID Partition Map" and start the system installation
  
## <br/>Generate your SMBios<br>
1. Using OCAT
  - Search Plataform Info (or PI) and generate new SMBios on SystemProductName![Search Plataform Info (or PI) and generate new SMBios](https://github.com/Ats0c/Lenovo_Ideapad_3i-15IML05-Hackintosh-EFI/blob/main/Images/SMBios.png)
2. Using GenSMBios
  - Watch these tutorials to find out how to do it (I don't know how to do this lol)
    - [In English](https://www.youtube.com/watch?v=dovJUlKgS5E)
    - [In Portuguese](https://www.youtube.com/watch?v=YT8nFStOPW0)

## <br/>What to disable in BIOS?<br>
- All configs about PXE
- Secure Boot
- Intel SGX
- Flip to boot

> [!IMPORTANT]
> Set the boot mode to UEFI if not.

## What tool did you use to modify the EFI?
Just good old [OCAT (OCAuxiliaryTools)](https://github.com/ic005k/OCAuxiliaryTools/releases)

## <br/>About MacOS update issues (ventura, sonoma and future updates)<br>
I don't think you necessarily need the latest version of the OS because we have rather weak and precarious hardware (yes, this notebook is bad). So I think it would be better if you used older versions of macOS (like Mojave, Catalina and BigSur) more for fluidity and also because it ensures that things like sleep work perfectly, versions like Ventura and Sonoma have a lot of suspension problems and even USB being unmapped completely out of nowhere. This is my opinion, you have every right to disagree with me.

## Thanks
I wanted to thank everyone who helps keep Hackintosh alive and a special thank you to [OzemirElion](https://www.olarila.com/profile/67412-ozemirelion/), creator of the original EFI

[^1]: the entire EFI base was redone for this processor.
