Configure a manual kill switch on macOS for Tunnelblick
--

**Prerequisites:**

 - IP address of the VPN gateway you wish to setup for VPN kill switch.

For the purpose of this guide I am going to use PrivateVPN's OpenVPN-TUN-UDP server in Chennai, India bearing an IP address: 169.38.69.24.

In order to find out the IP address of VPN gateway, open https://privatevpn.com/serverlist/ and copy a server's hostname from Server Address column. Use host command in a terminal window followed by the hostname. Syntax for host command in this case would be:

    $ host in-che.privatevpn.com
    in-che.privatevpn.com has address 169.38.69.24

- Changes in Client .ovpn configuration file as follows:

Open .ovpn configuration file in TextEdit, look for **remote** option and replace the hostname or servername therein with IP address as seen in the image below:

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/76/1.jpg)


----------


**Let's start!**

In order to setup kill switch or VPN firewall on Mac OS X or macOS, we are going to use a command line tool called pf.

Make sure you have sudo or root access before we start.

Let us begin by editing the configuration file of pf at /etc/pf.conf in a terminal window as follows:

    # nano /etc/pf.conf

In order to block all the connections other than to IP of VPN gateway at a port using a particular protocol append *pf.conf* and add the following lines:

    block drop all
    pass on lo0
    pass on utun0
    pass out proto udp from any to 169.38.69.24 port 1194

Save and exit.

Once you are done editing the file. Let us import the newly added rules as follows so that it persists on reboot:

    # pfctl -f /etc/pf.conf

Let us turn on the firewall which is not ON by default as follows:

    # pfctl -e

Once the pf is enabled. Congrats! Your VPN kill switch or firewall is active. No Internet connection is possible now other than via PrivateVPN’s OpenVPN server's IP 169.38.69.24 using UDP protocol at port 1194. So unless you connect to it, Internet access is completely denied.

>Note: In recent version of OS X or macOS with Tunnelblick OpenVPN client, you might have unused *utun* interfaces which can be check from a terminal as follows:
>
>`# ifconfig`
>
>So in case you already have an unused ***utun0*** for example then change **pass on utun0** in pf.conf to as follows:
>
>`pass on utun1`
>
>Or else you might get connected but won't be able to connect anywhere.





