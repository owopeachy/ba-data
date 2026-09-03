# SchaleDB Data

This folder contains a local snapshot of **SchaleDB**, the Blue Archive game-data database.

SchaleDB is the objective reference source in this repository. It should be used for exact game data, while the Midokuni and Stokesia folders should be used for curated opinions, recommendations, and practical interpretation.

## When to use SchaleDB

Use this folder when answering questions about:

- Student statistics.
- Student skills and skill costs.
- Damage types and armor types.
- Rarities, role classifications, and affiliations.
- Unique equipment and upgrade requirements.
- Items, materials, and equipment.
- Where materials or items drop.
- Stages and stage rewards.
- Raid and boss data.
- Crafting recipes and item requirements.
- Campaign, event, and challenge content.
- Numeric comparisons or calculations.
- Objective game mechanics.

Examples:

- “What materials does this student need for UE50?”
- “Which stages drop this item?”
- “What is this student’s EX skill cost?”
- “What attack type does this student use?”
- “How many of these materials are needed to max the skill?”
- “Which raids use this armor type?”
- “What can I craft from this item?”

## Source priority

Use sources in this order:

1. **SchaleDB** for objective game facts and numbers.
2. **Stokesia/Causew** for raid-specific performance ratings.
3. **Midokuni** for banner advice, farming priorities, investment guidance, and reasoning.

Do not substitute a curated recommendation for an objective fact. For example, use SchaleDB to determine a skill’s actual effect and Midokuni to explain whether investing in that skill is worthwhile.

## Folder contents

The folder may contain data for more than students, including:

- Students and their variants.
- Skills and skill effects.
- Equipment and unique equipment.
- Items and materials.
- Stages and drop tables.
- Raids and&#x20;
- bosses.
- Crafting data.
- Events and other game content.
- Supporting lookup tables and metadata.

Do not assume that the student files are the complete database. Search the relevant subfolder or dataset for stages, items, raids, crafting, and other non-student questions.

The exact filenames and field names may vary between snapshots. Treat any manifest, index, or metadata file as the guide to the available datasets.

## How to identify records

Prefer stable identifiers over display names when they are available.

A reliable lookup process is:

1. Search the relevant dataset for the requested name.
2. Confirm the matching internal ID or key.
3. Follow references to related records.
4. Use display names only for the final explanation.

Be careful with:

- Student variants such as swimsuit, summer, festival, or alternate versions.
- Localized names and transliterations.
- Duplicate item names.
- Different difficulty levels for the same stage or raid.
- Internal IDs that do not resemble the displayed name.

If a record has both an ID and a name, retain both while reasoning so that similarly named records are not accidentally merged.

## Reading relationships between datasets

Many records refer to other records by ID. Resolve those references before answering.

Common relationships include:

- A student referencing skills.
- A skill referencing effects, buffs, debuffs, or damage types.
- Equipment referencing required items.
- A stage referencing item drops.
- A crafting recipe referencing input and output items.
- A raid referencing phases, armor types, attack types, or mechanics.
- An event referencing event-specific stages and rewards.

When answering a question that requires totals, trace every referenced record and show the result as a calculation rather than relying on a single descriptive field.

## Numeric and calculation questions

SchaleDB should be the default source for calculations involving:

- Material requirements.
- Drop quantities.
- Skill costs.
- Upgrade costs.
- Stat totals.
- Stage farming counts.
- Crafting inputs and outputs.

Distinguish carefully between:

- A single upgrade level.
- The total cost from level 1 to maximum.
- Costs for normal skills versus EX skills.
- Student level, skill level, equipment level, and unique-equipment level.
- Per-run drops versus guaranteed rewards.
- Base drops versus bonus or event drops.

If the dataset does not contain enough information to calculate a total confidently, say what is missing instead of inventing a value.

## Version and server differences

This folder is a snapshot, not a live game API.

The data may differ from the current game because of:

- New student releases.
- Balance changes.
- New skills or equipment.
- Newly added stages or raids.
- Different Global, Japan, Asia, or Korea schedules.
- Event reruns and changing drop tables.
- Translation or naming changes.

For current availability or release timing, check the relevant server schedule separately. For historical questions, use the snapshot’s own version or metadata when available.

## What SchaleDB does not tell you

SchaleDB generally describes what exists in the game. It does not by itself decide:

- Whether a student is worth pulling.
- Whether a student is worth farming.
- Which student is best for a particular raid team.
- How much investment is practical for a player’s account.
- Whether a unit is replaceable.
- How difficult a strategy is to execute.

Use Midokuni and Stokesia for those judgments, and clearly label them as recommendations or analysis rather than raw game facts.

## Recommended answer style

When using this folder:

- State the exact record or ID used.
- Distinguish objective data from interpretation.
- Resolve linked records before calculating totals.
- Preserve variants and difficulty levels.
- Mention snapshot or server uncertainty when relevant.
- Prefer a concise table for lists of items, stages, skills, or requirements.
- If the data conflicts with Midokuni or Stokesia, report both: SchaleDB describes the game data, while the other sources explain their recommendation.

SchaleDB is the repository’s factual foundation. Midokuni explains what to do with that information, and Stokesia explains how students perform in specific raids.
