# VPN Cheat Sheet
VPN Cheat Sheet with the most needed stuff..











<br><br>


# Nordvpn




<br><br>
____________________________________________________________
<br><br>



## Server
- https://nordvpn.com/de/servers/tools/?_ga=2.77794711.2041510557.1610927844-1299169374.1610927844

<br><br>

# VPN example
```
# double vpn - UDP - netherlands -> switzerland
sudo openvpn /etc/openvpn/ovpn_udp/nl-ch10.nordvpn.com.udp.ovpn

```
















<br><br>
____________________________________________________________
<br><br>

## openvpn (https://support.nordvpn.com/Connectivity/Linux/1047409422/How-can-I-connect-to-NordVPN-using-Linux-Terminal.htm)

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
```



<br><br><br><br>




#### Auto sign-in

1. Create txt file and place it anywhere with this layout:
```bash
username
password
```

2. Open up your .ovpn in your favourite text editor and enter the following line:
```bash
auth-get-token
auth-user-pass /location/pass.txt
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



<br><br>


## Known Problem



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
