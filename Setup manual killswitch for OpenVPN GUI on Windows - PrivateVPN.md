Setup manual kill switch for OpenVPN GUI on Windows
--

>**PrivateVPN** offers easy to use application for [Windows OS](https://privatevpn.com/support/getting-started/windows/windows-10/privatevpn-app). Our VPN client includes solid kill switch and other leaks protection, it is highly recommended that you use it.

Albeit, if you wish to use opensource OpenVPN GUI client to connect to our service. You should read further on how to setup a basic kill switch to prevent unencrypted Internet access causing leaks upon an abrupt disconnection.

It is really important for example when your PC is torrenting while you are away from keyboard.

**Step 1 - Connect to PrivateVPN OpenVPN server of your choice**

Follow the remaining steps only when have successful connected.

**Step 2 - Open Command Prompt as Adminstrator**

Search for Command Prompt in Start Menu and right click it to open it as Administrator, grant Administrative rights when prompted to continue.

**Step 3 - Delete the default Internet route**

Use route command to delete the default Internet route to prevent Internet access at all when VPN disconnects.

    route delete 0.0.0.0


![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/67/1.medium.jpg)

Command Prompt would return **OK!** as confirmation. You have successfully setup a basic VPN kill switch for Windows OS. In order to restore your default routes again follow the below step.

---

**Restore default Internet route**

In order to restore default Internet route, all you need to do is Disable and Enable your main network adapter. 

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/68/2.jpg)

Navigate to Network Connections in Control Panel. Select and right click on your main network adapter and click **Disable**. **Enable** it again similarly. 

![enter image description here](https://media.vakil.win/mgoblin_media/media_entries/69/3.jpg)

That is all. You have restored your default Internet routes.





