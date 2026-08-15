## Description
Pushes updated recipe data and the recipe book to every connected client — useful right after
registering/removing recipes at runtime so already-online players see the change.


## Attributes
None.


## Examples
```yaml
Skills:
- registercraftingrecipe{id=myplugin:fancy_stick;result=STICK;shaped=false;ingredients=IRON_INGOT}
- updateserverrecipes
```


## Aliases
None.
