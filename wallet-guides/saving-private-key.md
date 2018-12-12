# Saving Private Key

First of all I'd like to recommend that you encrypt your wallet. Choose **Settings** -&gt; **Encrypt Wallet**. If successful, restart your wallet. When encrypting wallet make sure you choose a password that is easy to remember. Without the correct password you will be unable to access your funds.

Now you can go to **File** -&gt; **Backup Wallet** to save your wallet's dat file on a USB stick/your Dropbox etc. Secure it well. Remember the password to your wallet. You must remember it.  
  
Now most importantly, if you want to save the private key of a particular **DeepOnion address**, do the following.

{% hint style="info" %}
As long as you know the private key of an address, you can always access its ONION. You don't need the wallet dat file. The wallet dat file saves all of your private keys, as often times one has many different addresses. The private keys of your addresses are what you essentially need to have access to.
{% endhint %}

In your DeepOnion Wallet, go to **Help** -&gt; **Debug Window**.  
  
Write: 

```text
dumpprivkey YourPrivateKey
```

Your private key will be revealed. Take great care of it. Your private key represents all of the ONION saved on its particular address.  
  
With the use of private keys, you can generate DeepOnion cold storage paper wallets for long-term holding.

