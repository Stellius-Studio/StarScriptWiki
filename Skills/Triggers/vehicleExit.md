## Description
Fires when a player exits a vehicle (`VehicleExitEvent`). The target is the vehicle.


## Config
| Attribute | Description                                | Default |
|-----------|-------------------------------------------------|---------|
| vehicle   | Only fire if the vehicle's entity type matches     | any     |


## Skill Variables
| Variable       | Description                  |
|------------------|------------------------------------|
| `event-vehicle`    | The vehicle's entity type name       |


## Examples
```yaml
Skills:
- message{m="<aqua>Exited the boat!"} @trigger ~onVehicleExit
```


## See Also
- [vehicleEnter](Skills-Triggers-vehicleEnter) — the counterpart trigger.
