# BitLocker
Reference: https://www.howtogeek.com/262720/how-to-enable-a-pre-boot-bitlocker-pin-on-windows/

1. Enable Bitlocker for System drive
   1. Turn BitLocker on via `Control Panel > System and Security > BitLocker Drive Encryption` 
   2. Save Recovery Key (and Identifier) in KeePass
2. Set up Pre-Boot (Startup-) Pin via Group-Policy Editor
   1. Press `Win + R`
   2. Enter `gpedit.msc`
   3. Navigate to `Computer Configuration > Administrative Templates > Windows Components > BitLocker Drive Encryption > Operating System Drives`
   4. Open `Require Additional Authentication at Startup`
   5. Select `Enabled`
   6. Under `Configure TPM Startup PIN` select `Require Startup PIN With TPM`
   7. Save by selecting `Ok`
3. Add PIN for Drive
   1. Open `cmd.exe` as Administrator
   2. Enter `manage-bde -protectors -add c: -TPMAndPIN`
   3. Enter PIN
   4. Verify configuration with `manage-bde -status`

4. *(Optional)* Change PIN
   1. Open `cmd.exe` as Administrator
   2. Enter `manage-bde -changepin c:`
   3. Enter new PIN
   4. Verify configuration with `manage-bde -status`

5. *(Optional)* Remove PIN
   1. Press `Win + R`
   2. Enter `gpedit.msc`
   3. Navigate to `Computer Configuration > Administrative Templates > Windows Components > BitLocker Drive Encryption > Operating System Drives`
   4. Open `Require Additional Authentication at Startup`
   5. Under `Configure TPM Startup PIN` select `Allow Startup PIN With TPM`
   6. Save by selecting `Ok`
   7. Open `cmd.exe` as Administrator
   8. Enter `manage-bde -protectors -add c: -TPM`
   9. Verify configuration with `manage-bde -status`