# VPN Cheat Sheet
VPN Cheat Sheet with the most needed stuff..


# Nordvpn

<br><br>

## Server
- https://nordvpn.com/de/servers/tools/?_ga=2.77794711.2041510557.1610927844-1299169374.1610927844

<br><br>

## Linux

#### Install
```bash
sh <(curl -sSf https://downloads.nordcdn.com/apps/linux/install.sh)
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
