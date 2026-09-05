# Event Taxonomy — v0.1

Every KICKA event has a required `type` and an optional `subtype` that refines it.

## Event Types

| Type | Description |
|---|---|
| `pass` | A deliberate transfer of the ball from one player toward a teammate |
| `shot` | An attempt to score by sending the ball toward the opponent's goal |
| `goal` | A shot (or other action) that results in a goal being scored |
| `tackle` | A challenge to win the ball from an opponent in possession |
| `foul` | An infringement of the laws of the game |
| `save` | A goalkeeper (or outfield player) action preventing a goal |
| `interception` | Reading and cutting out an opponent's pass |
| `clearance` | Removing the ball from a dangerous area without a specific target |
| `dribble` | Running with the ball past an opponent |
| `cross` | A pass delivered from a wide area into the box |
| `corner` | A restart taken from the corner arc |
| `throw_in` | A restart taken by hand from the touchline |
| `offside` | An offside infringement |
| `card` | A yellow or red card issued to a player |
| `substitution` | A player is replaced by another |

## Subtypes (examples)

Subtypes are free-form strings that add detail within a type. Common examples:

- `pass`: `through_ball`, `long_ball`, `short_pass`, `switch`
- `shot`: `open_play`, `free_kick`, `penalty`, `header`
- `goal`: `open_play`, `free_kick`, `penalty`, `own_goal`
- `card`: `yellow`, `second_yellow`, `red`

New subtypes may be added without a version bump; new **types** require a minor
version bump (see [event-schema.md](./event-schema.md)).

## Outcomes

Where relevant, events carry an `outcome` describing their result (e.g.
`complete`/`incomplete` for passes, `on_target`/`off_target`/`blocked`/`saved`
for shots). See [data-dictionary.md](./data-dictionary.md) for the full list.
