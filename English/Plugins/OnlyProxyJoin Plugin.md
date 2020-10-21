# OnlyProxyJoin Plugin

### Overview
OnlyProxyJoin is a plugin created by TutorialMakerHD, designed to prevent users from using the [UUID Spoof](https://github.com/NexTre-dev/Minecraft-Server-Griefing/blob/main/English/Exploiting/UUIDSpoofing.md) vulnerability, by not allowing connections from other places apart from the Bungeecord server.

### Analyzation
OnlyProxyJoin relies on the `onPlayerJoin` event, which means that the plugin will only trigger, if a player joins. This is dependent on the player's ip.
```java
  @EventHandler(priority = EventPriority.HIGHEST)
  public void onPlayerLogin(PlayerLoginEvent event) {
    if (!event.getAddress().getHostAddress().equals(this.plugin.getConfig().getString("settings.proxyIP")))
      event.disallow(PlayerLoginEvent.Result.KICK_OTHER, this.plugin.getConfig().getString("settings.playerKickMessage").replaceAll("&", ")); 
  }
```

### Exploiting
Since OnlyProxyJoin relies on the `onPlayerJoin` event, the IP addresses listed below, are ignored and instead skipped, leaving the server vulnerable to UUID Spoofing:
* 0.0.0.0 (unknown or non routable address ([Read more about it here](https://en.wikipedia.org/wiki/0.0.0.0))
* 127.0.0.1 (localhost address ([Read more aobut it here](https://en.wikipedia.org/wiki/Localhost))
These IP addresses can be easily achieved using [UUID Spoofing](https://github.com/NexTre-dev/Minecraft-Server-Griefing/blob/main/English/Exploiting/UUIDSpoofing.md), as most today's clients have an IP address spoofing included.
