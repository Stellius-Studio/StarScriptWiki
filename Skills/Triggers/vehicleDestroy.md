## Description
Fires when a vehicle is destroyed (`VehicleDestroyEvent`). Fires with a player context if a
player destroyed it, otherwise a location context. The target is the vehicle.


## Config
| Attribute | Description                                | Default |
|-----------|-------------------------------------------------|---------|
| vehicle   | Only fire if the vehicle's entity type matches     | any     |


## Skill Variables
| Variable       | Description                 |
|------------------|-----------------------------------|
| `event-vehicle`    | The vehicle's entity type name       |


## Examples
```yaml
Skills:
- message{m="<red>Boat destroyed!"} @trigger ~onVehicleDestroy
```
