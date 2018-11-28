# Windows: Wallet Backup & Import

This tutorial will go over the simple process of backing up and importing your wallet data. It is recommended to backup as often as possible, but especially when a significant change in wallet data occurs \(i.e. good sized transaction\). Failure to backup wallet data could result in loss of coins in the case of local hardware failure or corrupt wallet.  
  
**Backing Up DeepOnion Wallet**

1. In the wallet menu bar, click File &gt; Backup Wallet.
2. When the Backup Wallet dialog box appears, save the file to whichever destination you want. It will save in a .dat format. For tutorial purposes, we will save this file to the Desktop with the name wallet.dat.

{% hint style="success" %}
You have successfully backed up the wallet information.
{% endhint %}

**Pro-tips:**

1. Create a backup folder that contains the wallet backup file organized by date a. Example: Backups/7.18.17/
2. If you have multiple wallets that you wish to backup at the same time, name files by coin name. a. \(Example: ONION.dat, ABC.dat, etc.\)
3. Save Backup folders to encrypted drive and encrypted thumb drive. You can also use a secure cloud backup such as [Dropbox](https://www.dropbox.com).

**Importing Backup**  
  
1\) Close any running instances of the DeepOnion Wallet.  
2\) Open any file explorer and type in the search bar “%appdata%” and press enter.  
3\) Navigate to the DeepOnion folder, notice in this folder you will see a “wallet.dat” file.  
4\) Select your previously saved backup file and copy/paste into the DeepOnion directory overwriting the original file.  
5\) Open DeepOnion wallet, wait for wallet to sync, and now you have successfully imported a backup file.

