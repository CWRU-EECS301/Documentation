# Quartus Setup Guide

## Downloading the Quartus Installer

The Quartus v15.1 Installer files for both Linux and Windows are available from the class Google Drive.

Download the files listed for your OS:

* **For Windows**: [Quartus v15.1 Windows](https://drive.google.com/drive/u/1/folders/0B3gj26Jx7aigTVdXYl9DMm5ES28)
  * QuartusSetup-15.1.0.185-windows.exe
  * QuartusSetup-15.1.2.193-windows.exe 
  * ModelSimSetup-15.1.0.185-windows.exe
  * cyclonev-15.1.0.185.qdz

* **For Linux**: [Quartus v15.1 Linux](https://drive.google.com/drive/u/1/folders/0B3gj26Jx7aigODZFeWRvMXVELWc)
  * QuartusSetup-15.0.2.153-linux.run
  * Quartus-15.0.0.145-linux.tar
  * Quartus-15.0.0.145-devices-1.tar

## Install Process

### For Windows: 

Run: **QuartusSetup-15.1.0.185-windows.exe**

### For Linux (Ubuntu 16.04LTS): 

From a command shell run: `QuartusSetup-15.0.2.153-linux.run`

After the Quartus install completes, there are additional packages that need to be installed for ModelSim to provide 32-bit runtime support.

Run this install commands

```
$ sudo dpkg --add-architecture i386
$ sudo apt-get update
$ sudo apt-get install libc6:i386 libstdc++6:i386 libncurses5:i386 libxft2:i386 libxext6:i386
```

There is also a bug work around that needs to be done for ModelSim:

1. Select **Tools** -> **Options...** from the menu bar
2. Click **EDA Tool Options** on the left hand panel
3. Copy the path from the **ModelSim-Altera** box to the **ModelSim** box
4. Click **OK** to save the changes

## License Server

Connect to the CWRU license server to register Quartus:

1. From the Quartus menu, select **Tools** -> **License Setup...**

1. In the **License File** box enter: _1800@cse-lic-03_

1. The set of licensed cores should update.



