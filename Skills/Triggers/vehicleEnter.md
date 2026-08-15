## Description
Fires when a player enters a vehicle (`VehicleEnterEvent`). The target is the vehicle.


## Config
| Attribute | Description                                | Default |
|-----------|-------------------------------------------------|---------|
| vehicle   | Only fire if the vehicle's entity type matches     | any     |


## Skill Variables
| Variable       | Description                   |
|------------------|-------------------------------------|
| `event-vehicle`    | The vehicle's entity type name        |


## Examples
```yaml
Skills:
- message{m="<aqua>Entered a boat!"} @trigger ~onVehicleEnter{vehicle=BOAT}
```


## See Also
- [vehicleExit](Skills-Triggers-vehicleExit) — the counterpart trigger.
