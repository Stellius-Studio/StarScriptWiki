## Description
Registers a raw advancement JSON definition into the server at runtime, using Bukkit's
`UnsafeValues#loadAdvancement`. Malformed JSON is caught and logged, not thrown. See the
[Advancement Definition](https://minecraft.wiki/w/Advancement_definition) page on the
Minecraft Wiki for the JSON format.


## Attributes
| Attribute | Aliases | Description                                                    | Default |
|-----------|---------|--------------------------------------------------------------------|---------|
| key       |         | The namespaced key the new advancement is registered under         | none (required) |
| json      |         | The advancement's JSON definition (supports placeholders)          | none (required) |


## Examples
```yaml
Skills:
- loadadvancement{key=myplugin:custom/first_kill;json="{\"display\":{\"icon\":{\"id\":\"minecraft:diamond_sword\"},\"title\":{\"text\":\"First Blood\"},\"description\":{\"text\":\"Kill a mob\"}},\"criteria\":{\"kill\":{\"trigger\":\"minecraft:player_killed_entity\"}}}"} @trigger
```


## Aliases
None.
