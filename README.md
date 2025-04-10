# VPN Cheat Sheet
VPN Cheat Sheet with the most needed stuff..





<br><br>
<br><br>
_____________________________________
<br><br>
<br><br>


# Proton VPN
- https://account.proton.me/u/1/vpn/dashboard




<br><br>

## Server

### WireGuard
- https://account.proton.me/u/1/vpn/WireGuard

### OpenVPN
- https://account.proton.me/u/1/vpn/OpenVpnIKEv2








<br><br>
<br><br>



## Install
- https://protonvpn.com/support/official-linux-vpn-debian/
- https://protonvpn.com/support/vpn-login/





### Wireguard
- https://protonvpn.com/support/wireguard-linux?srsltid=AfmBOopBQjZC5GQ7iHGk2_W5oV9xC9oNZQj6viHQfsywS1LcfSnOXY5-

1. Install wireguard
```shell
sudo apt install wireguard
```

2. Sign in to account.protonvpn.com, go to Downloads → WireGuard configuration, and download a WireGuard configuration file. Note that WireGuard can be picky about the length of .conf names, so please ensure the the downloaded .conf file name is under 15 characters (you may need to rename the default suggested name to achieve this). 

3. Move the downloaded .conf configuration file to the /etc/wireguard/ directory.
```shell
sudo cp /home/UsernameHere/Documents/vpn/protonvpn/wireguard/udp/main_os-CH-AT-1.conf /etc/wireguard/main_os-CH-AT-1.conf
sudo ls /etc/wireguard
```

4. Connect
```shell
sudo wg-quick up main_os-CH-AT-1
```

Your privacy is now protected by Proton VPN! To verify that the connection is running, enter:
```shell
sudo wg
```


You can also visit ip.me to confirm that everything is working correctly.

You can disconnect with:
```
sudo wg-quick down main_os-CH-AT-1
```




<br><br>
<br><br>

### OpenVPN



<br><br>
<br><br>

### GUI

<br><br>

#### Ubuntu
```
cd ~/Downloads
wget https://repo.protonvpn.com/debian/dists/stable/main/binary-all/protonvpn-stable-release_1.0.6_all.deb
sudo dpkg -i ./protonvpn-stable-release_1.0.6_all.deb && sudo apt update
sudo apt install proton-vpn-gnome-desktop
sudo apt install libayatana-appindicator3-1 gir1.2-ayatanaappindicator3-0.1 gnome-shell-extension-appindicator
```







<br><br>
<br><br>

## Deinstall

<br><br>

### Ubuntu
```
sudo apt purge "protonvpn*" proton-vpn-gnome-desktop && sudo apt autoremove
```




<br><br>
<br><br>

## FAQ

<br><br>

### How to disable the kill switch if you have uninstalled the app

<details><summary>Click to expand..</summary>

You can easily turn off the kill switch inside our Linux app, but this isn’t possible if you”ve already uninstalled it. In this case, you can remove the kill switch and restore access to the internet as follows:

a) Identify the Proton VPN connection name with the command:
```shell
nmcli connection show --active
```

his will show a list of your system’s active connections.

b) Look for any connections that begin with prefix pvpn- This usually includes pvpn-killswitch and pvpn-ipv6leak-protection, and may include pvpn-routed-killswitch. Delete all these connections using the following command:

```shell
nmcli connection delete [connection name]
```

For example:
```shell
nmcli connection delete pvpn-killswitch
```

c) Re-run the following command to check that all Proton VPN connections have been removed:
```shell
nmcli connection show --active
```

If you see any Proton VPN connections left, delete them as described above.

</details>





































<br><br>
<br><br>
_____________________________________
<br><br>
<br><br>

# Mega VPN

## Linux
- https://www.reddit.com/r/MEGA/comments/1fu7dle/mega_vpn_on_linux_cli/?rdt=64718


u/SupportMEGA avatar
SupportMEGA
•
3mo ago
•
Profile Badge for the Achievement Top 1% Commenter Top 1% Commenter

As of this moment, we do not have a proprietary MEGA VPN client for Linux yet. As general information, it is currently being developed to be released in a not-too-distant future. 

In the meantime, you could generate the VPN credentials, to be used in the WireGuard client for Linux. In order to do that, please refer to the guide below:

    Access https://www.wireguard.com/install/ and download the version that matches with your system.
    Copy the install command from the site and paste it in your Linux terminal. Note that the system will request your admin password.

    Access your MEGA account through a browser, then navigate to Settings - VPN (or click here https://mega.nz/fm/account/vpn).
    On the credential section, select the country you want to connect and click on 'Generate VPN credentials'.
    The system will create a QR code with a download button, please download the credential.

    On your Linux system, open /etc and open the Wireguard folder (note that this is a system folder, therefore, it will be necessary to enter your administrator credentials).
    Copy the VPN file from the location you downloaded it and paste it in the Wireguard folder.
    Note that we recommend you rename the file name to one that you will easily identify. I.e. Spain if you create a credential to connect to Spain.

    Open your terminal and execute the command sudo wg-quick up 'vpn filename'
    This will connect your VPN.
    Note: 'vpn filename' has to be introduced without apostrophes ('), and without the extension file name. E.g., to use 'Spain.conf' file, please introduce 'wg-quick up Spain'

    If during the connection attempt the system returns with an error /usr/bin/wg-quick: line 32: resolvconf: command not found then it means that your system will need an additional package for the VPN.
    Simply execute sudo apt install openresolv to install the missing package.

    Once installed, please execute the connection command again.

    To disconnect the VPN, simply execute sudo wg-quick down 'vpn filename'
    ^TT








<br><br>
<br><br>
_____________________________________
<br><br>
<br><br>

# Nordvpn

<br><br>

## API
- https://sleeplessbeastie.eu/2019/02/18/how-to-use-public-nordvpn-api/






<br><br>
<br><br>


## Server
- https://nordvpn.com/de/servers/tools/?_ga=2.77794711.2041510557.1610927844-1299169374.1610927844



## Double VPN

```
ca-us63.nordvpn.com
ca-us64.nordvpn.com
ca-us65.nordvpn.com
ca-us66.nordvpn.com
ca-us67.nordvpn.com
ca-us68.nordvpn.com
ca-us69.nordvpn.com
ca-us70.nordvpn.com
ca-us71.nordvpn.com
ca-us72.nordvpn.com
ca-us73.nordvpn.com
ca-us74.nordvpn.com
ca-us75.nordvpn.com
ca-us76.nordvpn.com
ch-nl13.nordvpn.com
ch-nl14.nordvpn.com
ch-nl15.nordvpn.com
ch-nl16.nordvpn.com
ch-se13.nordvpn.com
ch-se14.nordvpn.com
ch-se16.nordvpn.com
fr-uk10.nordvpn.com
fr-uk11.nordvpn.com
fr-uk16.nordvpn.com
fr-uk17.nordvpn.com
fr-uk20.nordvpn.com
fr-uk21.nordvpn.com
hk-tw3.nordvpn.com
nl-ch8.nordvpn.com
nl-ch9.nordvpn.com
nl-ch10.nordvpn.com
nl-ch11.nordvpn.com
nl-se10.nordvpn.com
nl-se12.nordvpn.com
nl-se13.nordvpn.com
nl-uk10.nordvpn.com
nl-uk11.nordvpn.com
nl-uk12.nordvpn.com
nl-uk13.nordvpn.com
se-ch11.nordvpn.com
se-ch12.nordvpn.com
se-ch13.nordvpn.com
se-ch14.nordvpn.com
se-nl11.nordvpn.com
se-nl12.nordvpn.com
se-nl13.nordvpn.com
se-nl14.nordvpn.com
tw-hk7.nordvpn.com
uk-fr10.nordvpn.com
uk-fr11.nordvpn.com
uk-fr16.nordvpn.com
uk-fr17.nordvpn.com
uk-fr18.nordvpn.com
uk-fr19.nordvpn.com
uk-nl10.nordvpn.com
uk-nl11.nordvpn.com
uk-nl12.nordvpn.com
uk-nl13.nordvpn.com
us-ca74.nordvpn.com
us-ca75.nordvpn.com
us-ca76.nordvpn.com
us-ca77.nordvpn.com
us-ca78.nordvpn.com
us-ca79.nordvpn.com
us-ca80.nordvpn.com
us-ca81.nordvpn.com
us-ca82.nordvpn.com
us-ca83.nordvpn.com
us-ca84.nordvpn.com
us-ca85.nordvpn.com
us-ca86.nordvpn.com
us-ca87.nordvpn.com
us-ca88.nordvpn.com
us-ca89.nordvpn.com
us-ca90.nordvpn.com
us-ca91.nordvpn.com
us-ca92.nordvpn.com
us-ca93.nordvpn.com
us-ca94.nordvpn.com
us-ca95.nordvpn.com

Double-VPN Servers: 80
```


### Random double vpn
```shell
nordvpn connect --group double_vpn
nordvpn c --group double_vpn
```











<br><br>

# VPN example
```
# double vpn - UDP - netherlands -> switzerland
sudo openvpn /etc/openvpn/ovpn_udp/nl-ch10.nordvpn.com.udp.ovpn

```

## List
```
ua - ukraine
```
















<br><br>
____________________________________________________________
<br><br>

## OpenVPN (https://support.nordvpn.com/Connectivity/Linux/1047409422/How-can-I-connect-to-NordVPN-using-Linux-Terminal.htm)


<br><br>

## ufw
- Check here for all neded rules (https://github.com/CyberT33N/ufw-cheat-sheet/blob/main/README.md#deny-forward-incoming--outgoing)




## Step by step Ubuntu
**In order to use OpenVPN with NordVPN server make sure to get service credentials by login in to nordvpn.com > Settings > NordVPN > set up nordvpn manually**


0. The nordvpn linux app will automatically set the dns to the nordvpn servers However, in when you use the openvpn linux client you must ensure to set them by yourself. You can achieve this by doing:
```
sudo gedit /etc/resolv.conf

# add
nameserver 103.86.96.100
nameserver 103.86.99.100

sudo systemctl restart systemd-resolved
```



1. Disbale IPV6
```bash
sudo gedit /etc/sysctl.conf
net.ipv6.conf.all.disable_ipv6 = 1
net.ipv6.conf.default.disable_ipv6 = 1
net.ipv6.conf.lo.disable_ipv6 = 1
net.ipv6.conf.tun0.disable_ipv6 = 1
# reboot
```

<br>

2. Install OpenVPN
```bash
sudo apt-get install openvpn
```

<br>

3. Navigate to the OpenVPN configuration directory with the command:
- cd /etc/openvpn

<br>

4. Download the OpenVPN configuration files with the command:
```bash
sudo wget https://downloads.nordcdn.com/configs/archives/servers/ovpn.zip
```

<br>

In case you get ERROR: The certificate of `nordvpn.com’ is not trusted., install the ca-certificates package with the command:
```bash
sudo apt-get install ca-certificates
```

<br>

5. If you do not have the unzip package installed, download it by typing:
```bash
sudo apt-get install unzip
```

<br>

6. Extract ovpn.zip with the command:
```bash
sudo unzip ovpn.zip
```

<br>

7. Remove the files you will no longer use:
```bash
sudo rm ovpn.zip
```



<br>


8. Enter the directory where the server configurations are located. These folders are named either ovpn_udp or ovpn_tcp:
- cd /etc/openvpn/ovpn_udp/
- cd /etc/openvpn/ovpn_tcp/
 
 
<br> 
 
 
9. To see the list of all available servers, enter the following command:
```bash
ls -al
```


<br>

Choose a server to connect to. For this tutorial, we used us2957.nordvpn.com, but you should connect to the server suggested to you at  https://nordvpn.com/servers/tools/. You can find the server hostname right under the server title.


<br>

10. Start OpenVPN with a chosen configuration by entering:
```bash
sudo openvpn [file name]
sudo openvpn us2957.nordvpn.com.udp.ovpn
sudo openvpn /etc/openvpn/ovpn_udp/us2957.nordvpn.com.udp.ovpn
sudo openvpn /etc/openvpn/ovpn_udp/za151.nordvpn.com.udp.ovpn
```



<br><br><br><br>




#### Auto sign-in

1. Create txt file and place it anywhere with this layout:
```bash
username
password
```
- **Username and password will not work with nordvpn anymore you must create now service credentials in the settings are of your account**

2. Open up your .ovpn in your favourite text editor and enter the following line:
- sudo gedit /etc/openvpn/ovpn_udp/ch-nl15.nordvpn.com.udp.ovpn
```bash
auth-user-pass /home/userName/Documents/nordvpn.txt
```
- ~ tilde not allowed use absolute path starting with /home/username/..

3. Set chmod
```shell
sudo chmod 600 /home/userName/Documents/nordvpn.txt
```



















<br><br>
____________________________________________________________
<br><br>



## Linux

#### Install
```bash
sh <(curl -sSf https://downloads.nordcdn.com/apps/linux/install.sh)
```



<br><br>

#### Connect
```bash
# Checz Republic
nordvpn c cz

# Germany
nordvpn c de
```



<br><br>

#### Remove 
```bash
sudo apt-get --purge remove 'nordvpn *'
```

<br><br>

#### Options

```bash
nordvpn login - Log in.

nordvpn connect or nordvpn c - Connect to VPN. To connect to specific servers, use nordvpn connect <country_code server_number> (eg. nordvpn connect uk715)
nordvpn c cz

nordvpn disconnect or nordvpn d - Disconnect from VPN.

nordvpn set or nordvpn s - Set a configuration option. Possible options:
nordvpn set cybersec on or off - Enable or disable CyberSec
nordvpn set killswitch on or off - Enable or disable Kill Switch

nordvpn set autoconnect on or off - Enable or disable auto-connect. You can set a specific server for automatic connection using nordvpn set autoconnect on country_code+server_number. Example: nordvpn set autoconnect on us2435.
nordvpn set autoconnect on cz

nordvpn set notify on or off - Enable or disable notifications

nordvpn set dns 1.1.1.1 1.0.0.1 - Set custom DNS (you can set up a single DNS or two like shown in this command).
nordvpn set dns 103.86.96.100 103.86.99.100

nordvpn set protocol udp or tcp - Switch between UDP and TCP protocols
nordvpn set obfuscate on or off - Enable or disable Obfuscated Servers.

nordvpn set technology - Set connection technology (OpenVPN or NordLynx)
nordvpn set technology nordlynx

nordvpn whitelist add port 22 - Add a rule to whitelist a specified incoming port. You can also whitelist multiple ports — just separate their numbers with a space.
nordvpn whitelist remove port 22 - Remove the rule to whitelist a specified port.
nordvpn whitelist add subnet 192.168.0.0/16 - Add a rule to whitelist a specified subnet.
nordvpn whitelist remove subnet 192.168.0.0/16  - Remove the rule to whitelist a specified subnet.

nordvpn account - See account information
nordvpn register - Register a new user account
nordvpn rate - Rate your last connection quality (1-5)
nordvpn settings - See the current settings.
nordvpn status - See the connection status.
nordvpn countries - See the country list.
nordvpn cities - See the city list.
nordvpn groups - See a list of available server groups.
nordvpn logout - Log out.

nordvpn help or nordvpn h - See the list of available commands or help for a specific command.
```




## groups
```shell
nordvpn groups
```

















<br><br>
_______________________________________________________________________

<br><br>


# NetworkManager

<br><br>

## Config File
- /etc/NetworkManager/system-connections
  - In this folder you can find the config files for all of your connections

## Auto Reconnect
```
[connection]
autoconnect=true
autoconnect-retries=0

[vpn]
persistent=true
```














<br><br>
_______________________________________________________________________

<br><br>


# DNS

<br><br>

## DNS over TLS

<br><br>

### Hostnames
dns2.nordvpn.com
dns1.nordvpn.com





















<br><br>
_______________________________________________________________________

<br><br>


## Known Problem


<br><br>

#### Disconeects on Linux

<br><br>

##### Method #1
- Connect via .ovpn files instead of the nordvpn CLI. Then reduce the ping & ping-restart to:
```
ping 2
ping-restart 2
```

<br><br>

##### Method #2
- If you get disconnects via linux cli and aswell via the openvpn client with udp then try:
```
nordvpn set technology openvpn                                               
nordvpn set protocol tcp
```
  - Now you can connect again via nordvpn cli `nordvpn c ca` or via openvpn tcp `sudo openvpn /etc/openvpn/ovpn_tcp/ch-nl14.nordvpn.com.tcp.ovpn`




<br><br>


#### Internet not working after uninstalling Nordvpn
```bash
sudo gedit /etc/NetworkManager/NetworkManager.conf

# Add to main section
[main]
rc-manager=unmanaged


sudo gedit /etc/resolv.conf

# Add those nameserver or google DNS 8.8.8.8
nameserver 103.86.96.100
nameserver 103.86.99.100

sudo systemctl restart NetworkManager.service
# Check if internet is working
ping -c2 google.com
```



<br><br>


#### Regular timeouts to l2tp VPN
- For me it worked to activate the guest WLAN in my Router. There is any missconfiguration in my FritzBox for my main Internet.
