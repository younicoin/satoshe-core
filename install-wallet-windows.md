# Windows Wallet Installation Guide

### Step №1.

Download the latest satoshe-x.x.x-win.zip archive release from this repository and extract the zip file anywhere on the disk.

### Step №2.

Click on the menu bar, type the following text `%appdata%` and press on the "ENTER" key, so you should now be in the current folder
`C:\Users\User\AppData\Roaming\`

Then, create the folder `**SATOSHE**` and open the folder.

### Step №3.

Create new `satoshe.txt` file, which we will further modify into `satoshe.conf`.

- Paste the following settings:
```
rpcuser=ANY_USERNAME
rpcpassword=ANY_PASSWORD
rpcbind=127.0.0.1
rpcallowip=127.0.0.1
listen=1
server=1
txindex=1
daemon=1
addnode=82.148.2.179
addnode=82.97.246.156
addnode=37.220.83.16
```

Type any of your values in the **rpcuser** and **rpcpassword** fields, then click on the menu item "File" -> "Save As...".

The open dialog box will appear, click on "Save as type" and select the option "_All Files (*.*)_".

Enter the following text behind "_File name_": `satoshe.conf`

Press on the button "`Save`".

### Step №4.

Return to the location of the files you extracted from the archive from `Step №1` and run the `satoshe-qt.exe` GUI wallet file
