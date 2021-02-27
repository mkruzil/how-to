# How to Redirect iTunes Backups to an External Hard Drive

*Note: These steps are for the Windows 10 operating system*.

1. Take a full backup of your C drive in case anything goes wrong, you can always get your files back.
2. After you have a full backup of your C drive, take a backup of your iPhone.

    a. Plug your iPhone into your computer.<br />
    b. Open **iTunes**.<br />
    c. Click **Back Up Now**.<br />

3. Create a folder at the root of your external hard drive. *Note: change the drive letter to match the actual drive letter of your external drive*.
   
   `D:\Apple Computer`

4. Right-click on the following folder on your C drive and click **Copy**:

   `C:\%USERNAME%\AppData\Roaming\Apple Computer\MobileSync`

5. Open the Apple Computer folder on your external hard drive, right-click inside the folder and click **Paste** to copy the MobileSync folder from your C drive to your external hard drive. You should now have the following path on your external hard drive:

   `D:\Apple Computer\MobileSync`

6. Open **iTunes**.
7. Go to **Edit->Preferences->Devices**.
8. In the list of backups, click on each backup and click **Delete Backup**.
9. Close iTunes.
10. Reclaim the disk space that was taken up by the back ups by following these steps:

    a. Click **Start->Windows Administrative Tools-> Disk Cleanup**.<br />
    b. Make a note of number next to **Total amount of disk space you gain**.<br />
    c  Make sure all items in the **Files to delete** box are checked and click **OK**.<br />
    d. Repeat steps a-d until the  **Total amount of disk space you gain** reaches around 100 MB. *Note that this can take a long time and may take repeating these steps multiple times.*

11. Rename your existing iTunes backup folder from:

    `C:\Users\%USERNAME%\AppData\Roaming\Apple Computer\MobileSync\Backup`

    to

    `C:\Users\%USERNAME%\AppData\Roaming\Apple Computer\MobileSync\Backup-Old`

12. Create a symbolic link that points the iTunes backup folder on your C drive to your external drive:
 
    a. Click **Start->Windows System->Command Prompt**.
    b. Type the following command, replacing **"D"** with the actual drive letter of your external drive:

       `mklink /j "%APPDATA%\Apple Computer\MobileSync\Backup" "D:\Apple Computer\MobileSync\Backup"`

       After running the command, you'll see the following message 

       *Junction created for C:\Users\Username\AppData\Roaming\Apple Computer\MobileSync\Backup <<===>> D:\Apple Computer\MobileSync\Backup*

13. Open iTunes and go to **Edit->Preferences->Devices**. You should see all your previous iTunes backups displayed. *Note: it can take a minute for the backups to load since now they are loading from the external drive.*

Now, the next time you plug in your iPhone and click **Back up now** in iTunes, the backup will be stored on your external hard drive instead of your local C drive.

# Resources

https://www.howtogeek.com/164275/how-to-change-the-backup-location-of-itunes-or-any-windows-app/