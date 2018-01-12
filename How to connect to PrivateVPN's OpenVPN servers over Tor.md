How to connect to PrivateVPN's OpenVPN servers over Tor?
--

Most people using VPNs are privacy conscious and then there are some paranoid ones. We won't judge you given a lot of revelations about intelligence agencies worldwide in recent times.

**What is VPN over Tor?**

A phrase used to define a VPN connection that uses Tor network to connect to the VPN servers. So, it is like this:

You > Tor > VPN > World

In other words, it basically means connecting to PrivateVPN without exposing your home IP to PrivateVPN as Tor acts as a bridge in between. Tor is a solid anonymity tool. Hence providing you with a dual layer to privacy, security and anonymity.

**Step 1 - Download and install TBB (Tor Browser Bundle)**

A fresh copy of TBB for your operating system can be downloaded from [here.](https://www.torproject.org/download/download-easy.html.en)

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/90/Screenshot_20171112_015530.png)

Navigate to Downloads folder, look **.exe** or .**dmg** file for Tor Browser Bundle on Windows or Mac respectively and double click to install. Installation is easy and straight forward. On GNU/Linux you just need to download tar file and extract it like I did.

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/83/Screenshot_20171112_004014.png)

On first run, a dialog box appears asking you to either **Connect** to Tor or configure it with other settings. 

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/85/Screenshot_20171112_013215.png)

Click on the **Connect** button and let it connect. 

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/86/Screenshot_20171112_013346.png)

Upon successful connection a screen as shown below will appear:

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/87/Screenshot_20171112_013405.png)

Now open [PrivateVPN](https://privatevpn.com) or any other website of your choice in TBB and click on the green Onion button to the left of address bar in TBB. There you will find the tor's current circuit information containing your **Entry | Middle | Exit** nodes as seen in the image below. The first node is the **entry or guard node** is important to us as it does not change to often, please make a note of it. Here the Entry or Guard node is **95.211.224.12**.

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/91/Screenshot_20171112_020200.png)

>Tor Entry or Guard node doesn't change too often at all. But in case it does after a while or upon a fresh download of TBB by you, Make sure you replace it in the .ovpn file.


**Step 2 - Pick a PrivateVPN TCP OpenVPN configuration and edit it**

You can download raw OpenVPN configuration files (UDP & TCP) for PrivateVPN in **.zip** file from [here.](https://privatevpn.com/client/PrivateVPN-TUN.zip)

Since Tor works with TCP protocol only, I am going to use **PrivatVPN-IN-Chennai-TUN-443.ovpn** from TCP folder for the purpose of this guide. 

Open **.ovpn** in a text editor and add the following lines: 

    # tor options
    socks-proxy 127.0.0.1 9150
    route [Entry or Guard node IP] 255.255.255.255 net_gateway

> For GNU/linux, **net_gateway** will not work and hence you have to use your default gateway IP which you can find using **route** command very easily. For example my default gateway is 192.168.0.1, so above route entry in my case would be:
>
> `route [Entry or Guard node IP] 255.255.255.255 192.168.0.1`



You need to replace [Entry or Guard node IP] with the Entry node's IP. In my case Entry or Guard node is **95.211.224.12**. So, I would edit my .ovpn as follows:

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/92/Screenshot_20171112_021010.png)

Save the edit .ovpn configuration file and exit.

**Step 3 - Connect to PrivateVPN's OpenVPN server over Tor**

Import the edited .ovpn file in OpenVPN client for your OS respectively and connect as usual. Make sure Tor Browser Bundle is running and it should work fine. 

Congrats! You are now connected to our OpenVPN server over Tor.

Thanks! Have fun.