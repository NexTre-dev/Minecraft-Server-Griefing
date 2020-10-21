##### This is only working with servers with `online-mode` turned on.
##### You can read more about UUID Spoofing [here](https://github.com/NexTre-dev/Minecraft-Server-Griefing/blob/main/English/Exploiting/UUIDSpoofing.md)

# UUID Spoof Fix | Plugin Bypasses

### Overview
UUIDSpoof-Fix is a plugin created by **zPirroZ3007**, it's created to prevent users from UUID Spoofing.

### Analizing the plugin
The plugin has a feature to whitelist certain users from UUID Spoofing.
```java
@EventHandler(priority = EventPriority.MONITOR)
public void onPlayerLogin(final PlayerLoginEvent event) {
    ...
    if (ConfigManager.exempt().getList("whitelist").contains(event.getPlayer().getName())) {
        return;
    }
    ...
 }
```
The plugin by default whitelists the user `zPirroZ3007`, which means that anyone with that username can freely UUID Spoof.
```yml
# All players in this list will be exempted from UUID check
whitelist:
- "zPirroZ3007"
```
Since a lot of server admins don't change the default config, you may be able to target servers with this vulnerability.

### Exploiting

By setting your username to `zPirroZ3007`, and your UUID to whatever, you can freely join the server while UUID Spoofing
