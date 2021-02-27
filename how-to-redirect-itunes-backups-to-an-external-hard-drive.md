# How to Redirect iTunes Backups to an External Hard Drive

*Note: These steps are for the Windows 10 operating system*.

1. As a precaution, take a full backup of your C drive. This way, if anything goes wrong, you can restore your data.
2. After you have performed a full backup of your C drive, take a backup of your iPhone:

    a. Plug your iPhone into your computer.<br />
    b. Open **iTunes**.<br />
    c. Click **Back Up Now**.<br />
    d. Close iTunes.

3. Create a new folder named `Apple Computer` at the root of your external hard drive. For example, if the drive letter of your external hard drive is `D` you would create the following folder:
   
   `D:\Apple Computer`

3. Follow these steps to open the `MobileSync` folder on your C drive:

   a. Click the **Start** button.<br />
   b. While the Start menu is open, type `%appdata%` and press Enter. This will open your `AppData` folder.<br />
   c. In the `AppData` folder, double-click the `Apple Computer` folder.
   d. Double-click the `MobileSync` folder.<br />

4. Right-click on the `MobileSync` folder and click **Copy**:

5. Open the `Apple Computer` folder that you created on your external hard drive, right-click inside the folder and click **Paste** to paste the `MobileSync` folder from your C drive onto your external hard drive. You should now have the following path on your external hard drive:

   `D:\Apple Computer\MobileSync`

6. Re-open **iTunes**.
7. Go to **Edit->Preferences->Devices**.
8. In the list of backups, click on each backup and click **Delete Backup**.
9. Close iTunes.
10. Reclaim the disk space that was taken up by the iTunes backups by following these steps:

    a. Click **Start->Windows Administrative Tools->Disk Cleanup**.<br />
    b. Make a note of number next to *Total amount of disk space you gain*.<br />
    c. Make sure all items in the *Files to delete* box are checked and click **OK**.<br />
    d. Repeat steps a-d until the  *Total amount of disk space you gain* reaches around 100 MB. **Note: this can take a long time and may require repeating these steps multiple times.**

11. Open the `MobileSync` folder on your C drive:

    a. Click the **Start** button.<br />
    b. While the Start menu is open, type `%appdata%` and press Enter. This will open your `AppData` folder.<br />
    c. In the `AppData` folder, double-click the `Apple Computer` folder.<br />
    d. Double-click the `MobileSync` folder.<br />

12. Rename the `Backup` folder to `Backup-Old`.

12. Create a symbolic link that points the iTunes backup folder on your C drive to your external drive:
 
    a. Click **Start->Windows System->Command Prompt**.<br />
    b. Type the following command, replacing the drive letter `D` with the actual drive letter of your external drive:<br />

       `mklink /j "%APPDATA%\Apple Computer\MobileSync\Backup" "D:\Apple Computer\MobileSync\Backup"`

       After running the command, you'll see the following message:

       *Junction created for C:\Users\Username\AppData\Roaming\Apple Computer\MobileSync\Backup <<===>> D:\Apple Computer\MobileSync\Backup*

13. Re-open iTunes and go to **Edit->Preferences->Devices**. You should see all your previous iTunes backups displayed. *Note: it can take a minute for the backups to display because now they are loading from your external hard drive.*

Now, the next time you plug in your iPhone and click **Back up now** in iTunes, the backup will be stored on your external hard drive instead of your local C drive.

# Resources

https://www.howtogeek.com/164275/how-to-change-the-backup-location-of-itunes-or-any-windows-app/