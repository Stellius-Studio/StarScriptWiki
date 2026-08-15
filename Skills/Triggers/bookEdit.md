## Description
Fires when a player edits a book (`PlayerEditBookEvent`).


## Config
| Attribute | Description                                    | Default |
|-----------|---------------------------------------------------|---------|
| signing   | Only fire if the book is being signed matches this (`true`/`false`) | any     |


## Skill Variables
| Variable       | Description                    |
|------------------|------------------------------------|
| `event-signing`    | `true` if the book is being signed |


## Examples
```yaml
Skills:
- message{m="<aqua>Book signed!"} @trigger ~onBookEdit{signing=true}
```
