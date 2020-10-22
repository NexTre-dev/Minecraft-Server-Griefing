# Port Scanning

### Overview
Port Scanning is a method to determine which ports are open on a network that could be receiving or sending data.
In Minecraft server griefing, this can be used to find open ports on a network.

### Analyzing
The most popular form of port scanning is with the usage of [Nmap](https://nmap.org/), if you are looking for a portscanner with a GUI, I recommend [ZenMap](https://nmap.org/zenmap/).

If you downloaded Nmap, type this command into cmd: `nmap -p 20000-35000 -T4 -A -v <IP Address>`

This scans the provided IP Address from port 20000 to 35000, which is the most popular port range for Minecraft networks.

Once it finds an open port, try joining that.

### Exploiting
If a port is open on a bungeecord network, that means that you can join that port without having to go through the process of logging into an account.
If you find an open port, but it doesn't let you join it (ex.: It kicks you, or connecting infinitely), the server may be using [OnlyProxyJoin](https://github.com/NexTre-dev/Minecraft-Server-Griefing/blob/main/English/Plugins/OnlyProxyJoin%20Plugin.md).

If you find an open port, and it lets you join it, you can freely join with any administrator account you want.
