# KICKA Standard v0.1

KICKA is an open standard for representing football (soccer) match event data
in a consistent, machine-readable format.

This directory documents version **0.1** of the standard.

## Contents

- [taxonomy.md](./taxonomy.md) — the event types and subtypes recognized by the standard
- [data-dictionary.md](./data-dictionary.md) — field-by-field definitions for every attribute
- [event-schema.md](./event-schema.md) — narrative guide to the JSON Schema in [`schemas/v0.1/event.schema.json`](../../../schemas/v0.1/event.schema.json)
- [examples/](./examples) — sample events (`pass.json`, `shot.json`, `goal.json`)

## Status

v0.1 is a draft. Field names, enums, and structure may change before v1.0.

## Related directories

- `schemas/v0.1/` — machine-readable JSON Schema
- `data/samples/v0.1/` — sample datasets conforming to this version of the standard
- `annotation/` — tools and guidelines for manually annotating match events
- `pipeline/` — ingestion/transformation code that produces or consumes KICKA events
- `tests/` — validation tests for the schema and sample data
