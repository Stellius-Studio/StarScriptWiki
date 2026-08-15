## Description
Scans around the targeted location using MythicEnchants' custom enchanting-table power algorithm
and writes the summed power into a skill variable. Writes `0` if the location's world is unloaded
or the custom table feature is disabled.


## Attributes
| Attribute | Aliases | Description                                       | Default |
|-----------|---------|-------------------------------------------------------|---------|
| var       |         | The skill variable name to store the table power into  | tablepower |


## Examples
```yaml
Skills:
- getmenchtablepower{var=power} @trigger ~onInteract @location
- message{m="Table power: <skill.var.power>"} @trigger
```


## Aliases
None.
