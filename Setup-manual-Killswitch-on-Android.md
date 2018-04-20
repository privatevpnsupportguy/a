Setup manual Kill switch on Android 7 (Nougat) or newer devices with PrivateVPN app (works for OpenVPN for Android client too)
--
With advent of powerful mobile devices, especially on an open platform like Android, people are using it for multi-tasking like download torrents, accessing Netflix, BBC etc online.

For a very long time, there has been a constant struggle for developing a **Kill switch** on Android with VPN apps owing to the limited access to the core system. Although starting with Android Nougat 7+, Android OS now comes with a dedicated **VPN killswitch.** If do not wish to expose yourself while switching networks or owing to an abrupt disconnection. Kindly continue.

**Step 1 - Disconnect from PrivateVPN App**

Disconnect from PrivateVPN app and make sure the server you wish to connect to is select from Server list in homescreen of App. 

For the purpose of this guide, I am guide I am going to use PrivateVPN's Icelandic VPN.

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/134/Screenshot_20180420-133304.medium.jpg)

**Step 2 - Configure Android system settings for persistent connection and kill switch**

Navigate to Android's Settings - *Wireless & networks* - *VPN* page as shown in the image below.

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/135/Screenshot_20180420-134004.medium.jpg)

Click on gears like icon to the right of **PrivateVPN** label to enter PrivateVPN app specific settings for VPN as seen in the image below.

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/136/Screenshot_20180420-134714.medium.jpg)

Enable/toggle **Always-on VPN** option to **ON** as seen in the image below.

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/137/Screenshot_20180420-140323.medium.jpg)

Make sure you get VPN connection as seen in the image below.

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/138/Screenshot_20180420-1403042.medium.jpg)

Once you have a VPN connection. Enable/toggle **Block connections without VPN** to **ON** as seen in the image below.

![](https://media.vakil.win/mgoblin_media/media_entries/139/Screenshot_20180420-1405152.medium.jpg)

Android OS, will prompt you a question, tap **TURN ON** to finally enable your manual killswitch for VPN. See the image below.

![](https://media.vakil.win/mgoblin_media/media_entries/140/Screenshot_20180420-140333.medium.jpg)

**Voila! You have successfully deployed a manual killswitch on your Android phone with PrivateVPN app for Android. It can also be done with OpenVPN for Android App.**

**Step 3 - Testing your manual Kill switch**

Goto PrivateVPN app and Disconnect the VPN connection from there and check if you still have any Internet access on your Android device.

Also try switch Wifi networks or from Wifi to Mobile data and vice-versa and check if you can access Internet unless you connect to VPN by navigating to PrivateVPN app or OpenVPN for Android app manually.

In my testing, this method is robust and blocks all Internet access without a valid VPN connection via PrivateVPN app or OpenVPN for Android App, whatever is configured for kill switch.

---

*Deploy it on your own Android device and enjoy robust kill switch protection on your Android Nougat (7+) or newer device right now.* 
