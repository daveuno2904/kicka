# KICKA

An open standard for representing football (soccer) match event data in a
consistent, machine-readable format.

## Repository structure

```
├── docs/
│   └── standard/
│       └── v0.1/
│           ├── README.md            — overview of the v0.1 standard
│           ├── taxonomy.md          — event types & subtypes
│           ├── data-dictionary.md   — field-by-field reference
│           ├── event-schema.md      — guide to the JSON Schema
│           └── examples/            — sample events (pass, shot, goal)
│
├── schemas/
│   └── v0.1/
│       └── event.schema.json        — machine-readable JSON Schema
│
├── data/
│   └── samples/
│       └── v0.1/                    — sample datasets
│
├── annotation/                      — manual annotation tools & guidelines
├── pipeline/                        — ingestion/transformation code
└── tests/                           — schema & data validation tests
```

## Getting started

Start with [`docs/standard/v0.1/README.md`](docs/standard/v0.1/README.md) for
an overview of the standard, then see
[`schemas/v0.1/event.schema.json`](schemas/v0.1/event.schema.json) for the
formal schema definition.

## Status

v0.1 — draft. Field names, enums, and structure may change before v1.0.
