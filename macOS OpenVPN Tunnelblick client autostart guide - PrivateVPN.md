
Configure Tunnelblick on macOS to auto-connect on boot
--

[PrivateVPN.com](https://privatevpn.com) offers an easy to use [VPN application for macOS](https://privatevpn.com/client/PrivateVPN1.1.pkg).

That being so, our VPN client is not mandatory to enjoy our OpenVPN servers. In this guide we are going to configure Tunnelblick openvpn client to auto-connect on boot as the title suggests.

Before, we start, I assume you already installed Tunnelblick on your Mac, if not then go through our other guide first.

**Let's start**

**Step 1 - Pick a single client configuration**

In order for this guide to function, you need to make sure that you only have a single configuration imported in Tunnelblick. For the purpose of this guide we are going to use OpenVPN-TUN TCP configuration from Stockholm in Sweden because my Mac is behind an office firewall mostly.

**Step 2 - Configure Tunnelblick client**

Navigate to **VPN Details** option from Tunnelblick icon at your top Menu Bar on Mac.

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/77/Screen_Shot_2017-11-09_at_7.06.20_PM.png)

In VPN details,  click on the **Settings** tab. In Settings tab page, change the **Connect** option to **"When Tunnelblick launches"** and click on Advanced button.

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/78/Screen_Shot_2017-11-09_at_7.07.09_PM.png)

In **Advanced Settings** page, under **Connecting & Disconnecting** tab, tick **Keep connected** option to enable it and you may now close all option Tunnelblick settings pages. That's all.

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/79/Screen_Shot_2017-11-09_at_7.07.33_PM.png)

>Note: It does not mean you should 'Quit Tunnelblick' from Top Menu Bar now, if you do this guide would not work for you. As Tunnelblick is set to auto-start on boot by default unless you manual quit it. 

**Step 3 - Connect to configured VPN server**

Navigate to the **Connect** option  (**Connect PrivateVPN-SE-Stockholm-TUN-443** in my case) from Tunnelblick icon at your top Menu Bar on Mac again and click to connect.

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/77/Screen_Shot_2017-11-09_at_7.06.20_PM.png)

A dialog box appears requiring your **PrivateVPN** username and password. Kindly input your credentials and check/tick **Save in Keychain** option for both as shown in the image below. Click **OK** to continue. 

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/82/Screen_Shot_2017-11-09_at_9.59.25_PM.png)

If everything is good, it will connect successfully. 

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/81/Screen_Shot_2017-11-09_at_7.18.32_PM.png)

**Step 4 - Restart your Mac**

The reason why we configured our client is to get our VPN up automatically when Mac starts. So, you need to restart your Mac and you should automatically get connected to the configured PrivateVPN location. 

Visit [PrivateVPN.com](https://privatevpn.com) to make sure it works!





