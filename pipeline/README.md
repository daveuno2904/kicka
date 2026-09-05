# Pipeline

Ingestion and transformation code that converts external data sources into
KICKA-formatted events, or consumes KICKA events downstream.

This directory is a placeholder for v0.1. Planned contents:

- Adapters that convert third-party providers' event data into
  [`schemas/v0.1/event.schema.json`](../schemas/v0.1/event.schema.json)
- Validation utilities used before publishing a dataset under `data/samples/`
- Export/serialization helpers
