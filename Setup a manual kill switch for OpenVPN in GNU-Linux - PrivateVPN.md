Setup a manual kill switch for OpenVPN in GNU/Linux
--

**Mission:**

Create a manual kill switch or VPN firewall for GNU/Linux to prevent any leaks including but not limited to DNS leaks outside VPN network at all by completely denying Internet access on a given system without an active encrypted **PrivateVPN** connection.

>Note: Other online guides might suggest you to allow DNS queries via your default gateway but I don’t recommend it. So, if you wish to allow it, you are at liberty to do so.

**Prerequisites:**

 - IP address of the VPN gateway you wish to setup for VPN kill switch.

For the purpose of this guide I am going to use PrivateVPN's OpenVPN-TUN-UDP server in Chennai, India bearing an IP address: 169.38.69.24.

In order to find out the IP address of VPN gateway, open https://privatevpn.com/serverlist/ and copy a server's hostname from Server Address column. Use host command in a terminal window followed by the hostname. Syntax for host command in this case would be:

    $ host in-che.privatevpn.com
    in-che.privatevpn.com has address 169.38.69.24

-	Name of the network interface connected to your default gateway or Internet. 

For the purpose of this guide I am going to use ***wlp6s0*** as network interface.

In order to find out your Internet facing network interface name use **route** command. Keep in mind it requires root or sudo access. Syntax for route command would be:

    # route

![enter image description here](https://technofaq.org/wp-content/uploads/2017/08/Screenshot_20170806_182215.png "route command output")

- Changes in Client .ovpn configuration file as follows:

Open .ovpn configuration file in a text editor, look for **remote** option and replace the hostname or servername therein with IP address as seen in the image below:

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/76/1.jpg)


----------

**Let's roll.**

Majority of GNU/Linux users either use iptables or ufw to manage their firewall. We have written separate sections for both tools below for your convenience. 

**a. VPN killswitch or firewall using *iptables***

(Note: You are advised to backup your current iptables ruleset with *iptables-save*)

*iptables* ruleset is already written for you.  Here take a look:

    #!/bin/bash
    iptables --flush
    iptables --delete-chain
    iptables -t nat --flush
    iptables -t nat --delete-chain
    iptables -P OUTPUT DROP
    iptables -A INPUT -j ACCEPT -i lo
    iptables -A OUTPUT -j ACCEPT -o lo
    iptables -A OUTPUT -j ACCEPT -d 169.38.69.24/32 -o wlp6s0 -p udp -m udp --dport 1194
    iptables -A INPUT -j ACCEPT -s 169.38.69.24/32 -i wlp6s0 -p udp -m udp --sport 1194
    iptables -A INPUT -j ACCEPT -i tun0
    iptables -A OUTPUT -j ACCEPT -o tun0


Above iptable rule set expunges every pre-exiting rule set in iptables and outrightly drops every outgoing connection other than to PrivateVPN's OpenVPN server's IP in India that to at a particular port (port 1194) using a specific protocol (udp). Also all incoming and outgoing connections are allowed over virtual network interface *tun0* exclusively.

You can copy *iptables* rule set from above and save it as **iptables-ks.sh** for your convenience to edit/execute them.

In order to activate *iptables* rule set in *iptables-ks.sh* for deploying a Kill switch, open a terminal with root/sudo rights and do as follows:

    # chmod +x iptables-ks.sh
    # ./iptables-ks.sh

Congrats! Your VPN kill switch or firewall is active

These settings are temporary and would be wiped upon reboot. In order to prevent it you might need to install “**iptables-persistent**” package for your distribution.

Or set it to run on boot by adding this line to the end of /etc/crontab:

    @reboot root /path/iptables-ks.sh

**b. Hello “ufw” users.**
(Note: We recommend you to backup your current firewall ruleset.)

I already wrote ufw ruleset for you.  Here take a look:

    ufw --force reset
    ufw default deny incoming
    ufw default deny outgoing 
    ufw allow in on tun0
    ufw allow out on tun0
    ufw allow out on wlp6s0 to 169.38.69.24 port 1194  proto udp
    ufw allow in on wlp6s0 from 169.38.69.24 port 1194 proto udp
    ufw enable

You can copy the ufw rules from above and save it as ufw-ks.sh for your convenience to edit/execute them.

Open a terminal and gain sudo access or root access and do as follows:

    # chmod +x ufw-ks.sh
    # ./ufw-ks.sh

Congrats! Your VPN kill switch or firewall is active. 

You can add multiple-servers in the same kill switch script. Just add additional lines for that particular server too. 

For example these two lines to above mentioned *ufw-ks.sh* would also allow connection to Icelandic server other than Indian VPN server:

    ufw allow out on wlp6s0 to 82.221.113.210 port 1194  proto udp
    ufw allow in on wlp6s0 from 82.221.113.210 port 1194 proto udp


----------
Thanks for reading! Enjoy!

 
















 











