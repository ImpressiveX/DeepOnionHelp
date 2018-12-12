# Sending Encrypted Messages

Sending encrypted messages is important for discussing transactions and private/proprietary information between wallet holders. Both parties involved must have a **public key** setup for their address in order to communicate. This insures only the sender and receiver will know who the message is from without having to worry about prying eyes.

**Creating Public Key and Setup**

1. In the DeepOnion wallet, copy your address to the clipboard. a. “Receive coins” tab &gt; right click &gt; Copy address. b. You should also rename your wallet to whatever you wish.
2. In the file menu click “Help” &gt; “Debug Window”.
3. In the debug console type the following and click enter a. smsgscanchain
4. Wait for response saying “Scan Chain Completed”.
5. Now in the debug console type the following and click enter. a. smsggetpubkey \#Your Wallet Address\# b. Replace \#Your Wallet Address\# with the address you copied to your clipboard.

{% hint style="info" %}
Your address will now have a public key on the DeepOnion network and is now available to send encrypted messages over the TOR network.
{% endhint %}

**Sending Messages**

1. Go to “Messages” tab of the DeepOnion wallet and click “New Conversation”.
2. “Address From:” should be your wallet address. a. You can view and save contacts via “Address Book”.
3. “Send To:” should be the other persons address you wish to talk to. a. As long as they have a public key on the DeepOnion network, it should auto-load the rest of the information in the window once you add the other wallet holders address.
4. Type your message, then click “Send”.

This guide will show you how to send encrypted messages over the TOR network via the DeepOnion wallet.

{% hint style="success" %}
The DeepOnion encrypted messaging feature is very similar to any other chat console. But you have the security of knowing your conversations are anonymous and protected over the TOR network.
{% endhint %}

