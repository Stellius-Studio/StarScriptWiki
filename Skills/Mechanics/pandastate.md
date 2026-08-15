## Description
Toggles a Panda's animation-state flags (rolling/sneezing/on-back/eating) and/or its personality
genes.


## Attributes
| Attribute  | Aliases | Description                                              | Default |
|------------|---------|--------------------------------------------------------------|---------|
| rolling    |         | Sets whether the Panda is rolling                             | unset   |
| sneezing   |         | Sets whether the Panda is sneezing                             | unset   |
| onback     |         | Sets whether the Panda is lying on its back                    | unset   |
| eating     |         | Sets whether the Panda is eating                               | unset   |
| maingene   |         | Sets the Panda's main personality gene (e.g. `NORMAL`, `LAZY`, `WORRIED`, `PLAYFUL`, `BROWN`, `WEAK`, `AGGRESSIVE`) | unset   |
| hiddengene |         | Sets the Panda's hidden personality gene (same values as `maingene`) | unset   |


## Examples
```yaml
MakePandaRoll:
  Skills:
  - pandastate{rolling=true} @target
```

```yaml
SetPandaPersonality:
  Skills:
  - pandastate{maingene=playful;hiddengene=lazy} @target
```


## Aliases
None.
