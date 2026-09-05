# Data Dictionary — v0.1

Field-by-field reference for the KICKA event object. See
[`schemas/v0.1/event.schema.json`](../../../schemas/v0.1/event.schema.json) for the
authoritative machine-readable definition.

| Field | Type | Required | Description |
|---|---|---|---|
| `event_id` | string | yes | Unique identifier for this event |
| `match_id` | string | yes | Identifier of the match this event belongs to |
| `team_id` | string | yes | Identifier of the team performing the event |
| `player_id` | string | yes | Identifier of the player performing the event |
| `type` | string (enum) | yes | Event type — see [taxonomy.md](./taxonomy.md) |
| `subtype` | string \| null | no | Optional refinement of the event type |
| `timestamp` | number | yes | Seconds elapsed since the start of the period |
| `period` | integer | yes | Match period (1 = first half, 2 = second half, 3/4 = extra time, 5 = penalties) |
| `location` | object `{x, y}` | yes | Pitch coordinates where the event occurred (0–100 scale, both axes) |
| `end_location` | object `{x, y}` \| null | no | Pitch coordinates where the event concluded (e.g. pass destination) |
| `outcome` | string (enum) \| null | no | Result of the event |
| `related_event_id` | string \| null | no | Identifier of a related event (e.g. the pass that led to a shot) |
| `metadata` | object | no | Additional freeform attributes specific to the event type |

## Coordinate system

The pitch is normalized to a 100×100 grid regardless of actual pitch
dimensions:

- `x`: 0 = own goal line, 100 = opponent's goal line
- `y`: 0 = left touchline, 100 = right touchline (from the perspective of a
  team attacking from x=0 to x=100)

## Outcome values

| Value | Applies to |
|---|---|
| `complete` / `incomplete` | passes, crosses |
| `on_target` / `off_target` / `blocked` | shots |
| `saved` | shots |
| `successful` / `unsuccessful` | dribbles, tackles, interceptions |

## Metadata conventions

`metadata` is intentionally open-ended so the standard can evolve without
breaking changes. Known keys in use today:

| Key | Used by | Type |
|---|---|---|
| `recipient_player_id` | pass, cross | string |
| `pass_length` | pass | `short` \| `medium` \| `long` |
| `body_part` | shot, goal, pass | `left_foot` \| `right_foot` \| `head` \| `other` |
| `xg` | shot, goal | number (0–1) |
| `assist_player_id` | goal | string |
| `under_pressure` | any | boolean |
