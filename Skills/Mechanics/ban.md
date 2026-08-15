## Description
Bans a player (by name or IP) with an optional reason and duration.


## Attributes
| Attribute | Aliases | Description                                                        | Default  |
|-----------|---------|----------------------------------------------------------------------|----------|
| reason    | r       | The ban reason shown to the player                                   | Banned   |
| ip        |         | If `true`, bans the player's IP address instead of their profile     | false    |
| kick      |         | If `true`, immediately kicks the player if they're online             | true     |
| expires   | duration | Ban duration in seconds. Omit (or `-1`) for a permanent ban          | permanent |


## Examples
```yaml
BanCheater:
  Skills:
  - ban{reason=Cheating;expires=86400} @trigger
```
> Bans the trigger's player for 24 hours (86400 seconds) with the reason "Cheating".

```yaml
BanIpPermanent:
  Skills:
  - ban{reason="Repeat offender";ip=true} @trigger
```
> Permanently bans the player's IP address.


## Aliases
None.
