# How to Redirect iTunes Backups to an External Hard Drive

*Notes:* 

-These steps are for redirecting iTunes from a new computer that has never previously backed up iTunes.<br />
-The steps were written for the Windows 10 operating system but also work on Windows 11.

1. If you are in Windows 11 S mode, you need to switch out of it in order to install iTunes. See: https://support.microsoft.com/en-us/windows/switching-out-of-s-mode-in-windows-4f56d9be-99ec-6983-119f-031bfb28a307

2. Install iTunes: https://www.apple.com/itunes/?cid=OAS-US-DOMAINS-itunes.com.

4. After iTunes is installed, close iTunes.

5. Create the following path at the root of your external hard drive. For example, if the drive letter of your external hard drive is `D` you would create the following path:
   
   `D:\Apple Computer\MobileSync\Backup`

6. Create the `MobileSync` folder on your C drive:

   a. Click the **Start** button.<br />
   b. While the Start menu is open, type `%appdata%` and press Enter. This will open your `AppData` folder.<br />
   c. In the `AppData` folder, double-click the `Apple Computer` folder.<br />
   d. Create a folder named `MobileSync`.

7. Create a symbolic link that points the `MobileSync` folder on your C drive to the `MobileSync` folder on your external drive:
 
    a. Click **Start->Windows System->Command Prompt**.<br />
    b. Enter the following command, replacing the drive letter `D` with the actual drive letter of your external hard drive:<br />

       `mklink /j "%APPDATA%\Apple Computer\MobileSync\Backup" "D:\Apple Computer\MobileSync\Backup"`

    c. After running the command, you'll see the following message:

       *Junction created for C:\Users\Username\AppData\Roaming\Apple Computer\MobileSync\Backup <<===>> D:\Apple Computer\MobileSync\Backup*

7. Plug in your iPhone and click **Back up now** in iTunes. The backup will be stored on your external hard drive instead of your local C drive.

# Resources

https://www.howtogeek.com/164275/how-to-change-the-backup-location-of-itunes-or-any-windows-app/
https://superuser.com/a/966171