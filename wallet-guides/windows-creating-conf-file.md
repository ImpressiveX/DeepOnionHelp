# Windows: Creating conf file

This tutorial will go over creating a DeepOnion.conf file. The reason for creating a .conf file is in case your wallet does not connect to the DeepOnion network. This could also happen on wallets that previously connected to the network. The .conf file is a good idea to add to your wallet just as a failsafe, even if the wallet is working correctly at this point.

{% hint style="info" %}
When a wallet is not connecting you will see the following: _This wallet is not connected to the DeepOnion Network. You will notice that the wallet says “out of sync” and in the lower right-hand corner, it shows a black computer monitor with an “x”. If you hover over this icon, it will say “0 active connections to DeepOnion network”._
{% endhint %}

**Prerequisites:**  
  
1\) Download, extract and run the DeepOnion Wallet  
a. Wallet must be running at least once in order for AppData directory to create.  
b. Download wallet [here](https://deeponion.org/index.php#download).  
c. Details on extraction and running process can be found in the first part of [this tutorial](https://deeponion.org/community/threads/deeponion-wallet-installation-tutorial.19/).  
2\) Make sure firewall is not blocking DeepOnion  
  
**Creating .conf file**  
  
1\) Open the file explorer  
2\) Type in the address bar “%appdata%” and press Enter  
3\) Double-click the folder that says “DeepOnion”. You should be in a folder like the following  
4\) Right-click on the folder and hit New &gt; Text Document  
5\) Open the text file and copy/paste the following:  
  
addnode=467on7g7zkaoeoqc.onion:17570  
addnode=3mvsotcd7l5miifw.onion:17570  
addnode=h526e6w24bxsaqr4.onion:17570  
addnode=old6atfotff4zaej.onion:17570  
addnode=fpeqr47k2pbnq6tf.onion:17570  
addnode=rfqhjb3p3gsn7eoq.onion:17570  
addnode=mdmc4nrdzh36rmpe.onion:17570  
addnode=vk5wm2vm3uzfpjve.onion:17570  
addnode=7ix47iyorlbubz6r.onion:17570  
addnode=l55ax2s6blqryhq5.onion:17570  
addnode=b6vkvlaxu5anbbbx.onion:17570  
addnode=xvl2bjq2zaxqy5ug.onion:17570  
addnode=cg4biu5e4cskhr2t.onion:17570  
addnode=z7vgvw422ufpqmxp.onion:17570  
addnode=tpvwbyrpuspgldlf.onion:17570  
addnode=jbjyc6qup3v7pfyx.onion:17570  
  
6\) On the menu bar click File &gt; Save As  
7\) Once the Save As window pops up, type “DeepOnion.conf” as the file name  
8\) Hit the down arrow on the Save as type portion and click “All types \(\*.\*\)”  
a. This will allow the file to be saved as a .conf file instead of a .txt file  
9\) Click Save.  
  
From this point, you should be able to reopen your DeepOnion wallet and start seeing connections to the network. The blockchain should download and your wallet be fully functional. Hover over the bar menu in the bottom right portion of your wallet and see the number of connections.

