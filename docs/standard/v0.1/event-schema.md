# Event Schema — v0.1

The canonical, machine-readable definition of a KICKA event lives at
[`schemas/v0.1/event.schema.json`](../../../schemas/v0.1/event.schema.json)
(JSON Schema draft 2020-12).

## Validating an event

Any standard JSON Schema validator can check a KICKA event against the schema.

```bash
npx ajv-cli validate -s schemas/v0.1/event.schema.json -d docs/standard/v0.1/examples/pass.json
```

or in Python:

```python
import json
from jsonschema import validate

schema = json.load(open("schemas/v0.1/event.schema.json"))
event = json.load(open("docs/standard/v0.1/examples/pass.json"))
validate(instance=event, schema=schema)
```

## Versioning

- The standard is versioned as `vMAJOR.MINOR`.
- Adding an optional field or a new `subtype` value: no version bump required.
- Adding a new event `type`, changing a field's meaning, or removing a field:
  bump `MINOR` (or `MAJOR` once the standard reaches v1.0) and publish a new
  `docs/standard/vX.Y/` and `schemas/vX.Y/` directory pair. Prior versions are
  never modified in place.

## Examples

See [examples/](./examples) for complete, valid events of each core type:
[`pass.json`](./examples/pass.json), [`shot.json`](./examples/shot.json),
[`goal.json`](./examples/goal.json).
