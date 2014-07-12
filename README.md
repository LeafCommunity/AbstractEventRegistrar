AbstractEventRegistrar
======================

This library allows for any developer to listen to abstract events in the Bukkit API. This is handy for listening to all events of a certain nature, like PlayerEvents or InventoryEvents. This can also listen to every Event.

Usage
```java
@Override
public void onEnable() {
  final AbstractEventRegistrar aer = new AbstractEventRegistrar(this);
  aer.registerAbstractListener(PlayerEvent.class, new Listener() {
    @EventHandler
    public <T extends PlayerEvent> void onPlayerEvent(T event) {
      getLogger().info("Player's name was " + event.getPlayer().getName());
    }
  }, EventPriority.NORMAL);
}
```
