# How to Redirect iTunes Backups to an External Hard Drive

*Note: These steps were written for the Windows 10 operating system*.

1. Install iTunes: https://www.apple.com/itunes/?cid=OAS-US-DOMAINS-itunes.com

   Note: If you are in S mode, you need to switch out of it in order to instal iTunes. See: https://support.microsoft.com/en-us/windows/switching-out-of-s-mode-in-windows-4f56d9be-99ec-6983-119f-031bfb28a307

2. Open and then close iTunes to ensure you have an iTunes folder created on your local hard drive.

3. Create a new folder named `Apple Computer` at the root of your external hard drive. For example, if the drive letter of your external hard drive is `D` you would create the following folder:
   
   `D:\Apple Computer`

4. Copy the `MobileSync` folder on your C drive:

   a. Click the **Start** button.<br />
   b. While the Start menu is open, type `%appdata%` and press Enter. This will open your `AppData` folder.<br />
   c. In the `AppData` folder, double-click the `Apple Computer` folder.<br />
   d. Right-click on the `MobileSync` folder and click **Copy**:

5. Open the `Apple Computer` folder that you created on your external hard drive, right-click inside the folder and click **Paste** to paste the `MobileSync` folder from your C drive onto your external hard drive. You should now have the following path on your external hard drive:

   `D:\Apple Computer\MobileSync`

6. Create a symbolic link that points the iTunes `MobileSync` folder on your C drive to your external drive:
 
    a. Click **Start->Windows System->Command Prompt**.<br />
    b. Enter the following command, replacing the drive letter `D` with the actual drive letter of your external hard drive:<br />

       `mklink /j "%APPDATA%\Apple Computer\MobileSync\Backup" "D:\Apple Computer\MobileSync\Backup"`

       After running the command, you'll see the following message:

       *Junction created for C:\Users\Username\AppData\Roaming\Apple Computer\MobileSync\Backup <<===>> D:\Apple Computer\MobileSync\Backup*

7. Plug in your iPhone and click **Back up now** in iTunes. The backup will be stored on your external hard drive instead of your local C drive.

# Resources

https://www.howtogeek.com/164275/how-to-change-the-backup-location-of-itunes-or-any-windows-app/