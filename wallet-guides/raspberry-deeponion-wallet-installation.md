# Raspberry: DeepOnion Wallet Installation

This guide will show you how to install the DeepOnion wallet on Raspberry pi 3 model B. It may also work on the older Raspberry revisions, but this guide was created for Raspberry pi 3 model B.

**STEP 1:** Go and buy Raspberry Pi 3 model B \(RS or E-14 does not matter which as they are almost identical\).  
**STEP 2:** Download and copy latest **Raspbian Stretch with a desktop** to your SD card \(you need at least 8 GB Card, but it's better to have 16GB\) [\(Download Raspbian for Raspberry Pi\)](https://www.raspberrypi.org/downloads/raspbian/)  
**STEP 3:** Connect your Raspberry Pi3 to the internet.  
**STEP 4:** Open Console and update software repositories. Run command:

> _sudo apt-get update_

**Important information:** From this moment All commands should be done in one opened terminal. Below you will see the reason why we need to do it all in one terminal window.  
  
**STEP 5:** Our repositories are updated and we can setup required software. Run command:

> _sudo apt-get install build-essential libtool autotools-dev autoconf automake pkg-config libssl-dev libboost-all-dev bsdmainutils libqrencode-dev libminiupnpc-dev libevent-dev libcap-dev libseccomp-dev git libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler_

This installation will take around 2-5 minutes depending on your internet connection.  
  
**STEP 6:** Now we have all of the required software. So we are ready for work. Let's download the DeepOnion wallet source code. Run commandCode:

```text
git clone --recursive https://github.com/deeponion/deeponion.git
```

The download will take around 1-5 minutes depending on your internet connection.

Let's switch downloaded source code to the raspberry branch. Run two commands:

> _cd deeponion_  
> _git checkout raspberry_

**STEP 7:** Let's prepare our terminal for next steps. Run these three commands:

> _ONION\_ROOT=$\(pwd\)_  
> _BDB\_PREFIX="${ONION\_ROOT}/db4"_  
> _mkdir -p $BDB\_PREFIX_

**STEP 8:** Let's prepare Berkley libraries for our installation. They are required for compiling the DeepOnion wallet, but we should install them manually with some flags. Run these six commands:

> _cd .._  
> _wget '_[_http://download.oracle.com/berkeley-db/db-4.8.30.NC.tar.gz_](http://download.oracle.com/berkeley-db/db-4.8.30.NC.tar.gz)_'_  
> _tar -xzvf db-4.8.30.NC.tar.gz_  
> _cd db-4.8.30.NC/build\_unix/_  
> _../dist/configure --enable-cxx --disable-shared --with-pic --prefix=$BDB\_PREFIX_  
> _make install_

{% hint style="info" %}
The last command will take quite long time. Make yourself a coffee while you wait. ☕
{% endhint %}

**STEP 9:** Okay Berkley libraries is done, now let's configure DeepOnion source code for installation. Run these three commands:

> _cd $ONION\_ROOT_  
> _./autogen.sh_  
> _./configure --disable-tests --with-gui=qt5 LDFLAGS="-L${BDB\_PREFIX}/lib/" CPPFLAGS="-I${BDB\_PREFIX}/include/"_

**Important tip:** '/home/pi/deeponion/src/Makefile' &lt;--- This file created

**STEP 10:** We are almost ready for installation, we just need to edit Makefile, especially for Raspberry Pi 3.

Open Makefile created by previous step '/home/pi/deeponion/src/Makefile'  
find there **-msse2** and **-mstackrealign** flags and delete them.  
After deletion, save Makefile and close text redactor.

**STEP 11:** We are ready for the final compilation. Close all opened browser windows and Run this command:

> _make_

DeepOnion wallet compilation will begin. This process will be very long and will require all of the cpu and ram capacity. Around 2 hours are needed for this step.

As result, will be created "DeepOnion-qt" file inside your '/home/pi/deeponion/src/' directory  
  
Okay. The wallet is compiled. How to run it?

To run the wallet you need to put full file path with all directories in the console. Run command: 

> _src/qt/DeepOnion-qt_

Surprise guys! New Feature here! Wallets are asking you where do you want to store the blockchain. Just press ok. Leave the default settings.

**STEP 12:** Wallet will show error and will ask you to create conf file and will close.

Go to this link and download ready to use conf file: [https://deeponion.org/DeepOnion.conf.php](https://deeponion.org/DeepOnion.conf.php)

Right-click and save the file.

**STEP 13:** OK. The config file is created and it already contains newest nodes.  
File path: "/home/pi/.DeepOnion/DeepOnion.conf"  
".DeepOnion" it is hidden folder  
  
Now just add to DeepOnion.conf file two more lines and save it. Don't delete other lines.

> rpcuser=put\_something  
> rpcpassword=put\_something

Now you can try to run the wallet again. It will start without errors and will be syncing \(if nodes are ok\).

**Little tip:** You can copy in this directory your wallet.dat file from Windows wallet and it will work fine.  
  
**Step 14:** Ok, the wallet is working fine, but running it always from the console it is not very convenient. Let's create a shortcut for it.

First download DeepOnion wallet logo which you want to use and save it as  
/home/pi/.DeepOnion/logo.png

After logo will be saved inside ".DeepOnion" folder run command:

> _sudo leafpad /usr/share/applications/deeponion.desktop_

This will be open text redactor. Enter this text and just save the file:

> _\[Desktop Entry\]_  
> _Type=Application_  
> _Exec=/home/pi/deeponion/src/qt/DeepOnion-qt_  
> _Icon=/home/pi/.DeepOnion/logo.png_  
> _Name=DeepOnion v1.7.0_  
> _GenericName=DeepOnion Wallet_  
> _Categories=Internet; Tor_

After the file has been saved, run this command:

> _sudo update-desktop-database_

After running the command check your systems main menu, section "OTHER". There you will see the shortcut you have created for your wallet with the image which you have chosen.

{% hint style="success" %}
Now you can easily use your wallet without all the troubles with the console. Happy Staking!
{% endhint %}

