# Midokuni Data

Structured Blue Archive data for machine-readable retrieval by MCP tools and LLMs.

This repository combines two deliberately separate sources:

- **Midokuni analysis** — curated opinions, recommendations, and reasoning.
- **SchaleDB data** — objective game data such as students, stages, items, raids, drops, and crafting.

## Repository contents

```text
midokuni-data/
├── midokuni.json
└── schaledb/
    ├── README.md
    └── *.json
```

### `midokuni.json`

A single JSON document containing one object per student.

Each student object has a stable, fixed schema. Fields that do not apply to a student are retained with `null` values rather than being omitted.

The Midokuni fields include:

- Availability: `both`, `banner`, or `farmable`
- Banner guidance: TL;DR, must-roll conditions, skip guidance, use cases, investment recommendations, and thoughts
- Farmable guidance: farming source, farming type, investment advice, alternatives, and farming thoughts
- General thoughts: TL;DR, low-investment use, and late-game use

This file represents **Midokuni’s curated analysis**, not objective game data.

### `schaledb/`

A manually maintained snapshot of structured data from [SchaleDB](https://github.com/SchaleDB/SchaleDB).

See [`schaledb/README.md`](schaledb/README.md) for the file map and lookup
