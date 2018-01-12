How to proxify a web browser with PrivateVPN?
--

A lot of people want a private browser with a secure setup for their **private browsing** habits or to access their favorite content provider like **Netflix, BBC** etc.

Although [PrivateVPN](https://privatevpn.com) recommends you to use more secure VPN protocols like OpenVPN or IKEv2 but if routing whole of your Internet traffic via VPN gateway is not what you desire this guide might attract you. 

In order to proxify a web browser, we recommend [SOCKS5](https://en.wikipedia.org/wiki/SOCKS#SOCKS5) protocol with authentication owing to added benefit including but not limited to support for UDP, DNSlookups etc. 

**Step 1 - Download and install latest Mozilla Firefox on your OS**

When it comes to privacy, [Firefox](https://www.mozilla.org/en-US/firefox/new/) is only browser that comes to my mind. 

Kindly download, install latest version of Firefox and keep it ready.

**Step 2 - Install & configure 'Proxy SwitchyOmega' Firefox Add-on**

Latest version of Proxy SwitchyOmega can be found [here.](https://addons.mozilla.org/en-US/firefox/addon/switchyomega/)

Click **Add to Firefox**

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/94/Screenshot_20171116_182329.medium.png)

Click **Add** again to grant permission for installation

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/95/Screenshot_20171116_182409.png)

Voila! SwitchyOmega is installed. Click **Skip guide** to continue.

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/96/Screenshot_20171116_182421.png)

SwitchyOmega interface appears. Click on **proxy** under Profiles section on the left and select **SOCKS5** protocol from drop down menu as show in the image below. 

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/97/Screenshot_20171116_182452.medium.png)

Visit [PrivateVPN's Server list](https://privatevpn.com/serverlist/) page and pick a server hostname of your choice. Hong Kong's hostname is being used for the purpose of this guide. You can always pick UK or USA if you wish to use it for Netflix, BBC or whatever.

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/98/Screenshot_20171116_182547.png)

Input the server hostname in the Server input field and Port as 1080 in the respective fields as shown in the image below. Click on the **lock icon** to the right to continue.

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/99/Screenshot_20171116_182611.medium.png)

A dialog box appears, input your PrivateVPN credentials here. Click **Save changes** to continue. You can notice lock icon now goes green.

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/100/Screenshot_20171116_182641.png)

Click on **Apply changes** under Actions Menu to continue.

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/101/Screenshot_20171116_182653.medium.png)

Click on Interface tab under Settings to change the **Startup Profile** to **proxy**. Click **Apply changes** again to save it.

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/102/Screenshot_20171116_182726.medium.png)

**Step 3 - Restart Firefox to enjoy your proxified browser**

Once you restart Firefox, navigate to whatismyipaddress.com to check if it is working you!

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/103/Screenshot_20171116_183115.medium.png)

----
You have sucessfully configured PrivateVPN SOCKS5 proxy on Firefox Web Browser. Now all the traffic in the browser including DNS queries would be routed via PrivateVPN.

>**Important tips for privacy:**
>
>Install [HTTPS everywhere](https://www.eff.org/https-everywhere) and [Privacy Badger](https://www.eff.org/privacybadger) Firefox Add-ons developed by [EFF](https://eff.org).
>
>Configure Firefox to clear history etc on exit. A guide by Mozilla is made available [here.](https://support.mozilla.org/en-US/kb/delete-browsing-search-download-history-firefox#w_how-do-i-make-firefox-clear-my-history-automatically) Check it out!

