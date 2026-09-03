# Blue Archive Data Repository

This repository combines three complementary sources for answering Blue Archive questions:

- `schaledb/` — objective game data.
- `midokuni/midokuni.json` — curated student advice.
- `midokuni/glossary.json` — Midokuni terminology.
- `stokesia/stokesia.json` — raid-specific performance analysis.
- Folder README files — source-specific interpretation and usage guidance.

The goal is to answer questions with the right source, keep facts separate from opinions, and avoid treating one dataset as a replacement for another.

## Source-selection rule

Start by identifying what kind of question the user is asking.

| Question type | Primary source |
|---|---|
| “What are this student’s stats or skills?” | `schaledb/` |
| “What materials or items do I need?” | `schaledb/` |
| “Where does this item drop?” | `schaledb/` |
| “What can I craft?” | `schaledb/` |
| “Should I pull this student?” | `midokuni/midokuni.json` |
| “Should I farm this student?” | `midokuni/midokuni.json` |
| “How much should I invest?” | Midokuni, then verify requirements in SchaleDB |
| “What is this student good for early game?” | Midokuni |
| “How does this student perform in Binah/Kaiten/etc.?” | `stokesia/stokesia.json` |
| “Who should I use for this raid?” | Stokesia, with SchaleDB used to verify mechanics and types |
| “What does this term mean?” | `midokuni/glossary.json` |
| “What does this raid mechanic do?” | `schaledb/`, then supporting raid notes |

When a question spans multiple categories, combine the sources rather than choosing only one.

## Recommended lookup workflow

### 1. Classify the request

Separate the question into:

- Objective facts.
- Calculations.
- Curated recommendations.
- Raid performance.
- Terminology.

A single user question may contain several of these.

### 2. Find the relevant record

Use the appropriate folder and search by name. Prefer stable IDs when available.

Be careful with:

- Student variants and limited versions.
- Localized names and transliterations.
- Duplicate item names.
- Different stage or raid difficulties.
- Server-specific content.

Do not merge records only because their display names look similar.

### 3. Follow references

SchaleDB records often reference other records by ID. Resolve those links before answering.

For example:

- Student → skills.
- Skill → effects.
- Equipment → required items.
- Stage → drops.
- Recipe → input and output items.
- Raid → phases, types, and mechanics.

Keep the identifiers while reasoning, then use readable names in the final response.

### 4. Add interpretation only where appropriate

Use Midokuni to explain practical value:

- Early-game progression.
- Late-game and raid context.
- Banner decisions.
- Farming priorities.
- Investment recommendations.
- Alternatives and substitutes.

Use Stokesia to explain raid-specific usefulness and ratings.

Label these as analysis or recommendations. Do not present them as objective game mechanics.

### 5. Verify calculations

For totals involving materials, drops, skills, equipment, or crafting:

1. Identify the exact target record.
2. Resolve all referenced item and upgrade records.
3. Distinguish one-step costs from total costs.
4. Distinguish guaranteed rewards from per-run drops.
5. Account for difficulty, event, and server differences.
6. Show the calculation or assumptions.

If the repository does not contain enough information, state what is missing instead of guessing.

## Combining the sources

A strong answer often follows this pattern:

1. **SchaleDB:** establish the factual game data.
2. **Stokesia:** explain raid performance if a specific raid is involved.
3. **Midokuni:** explain whether the student is worth obtaining, farming, or investing in.
4. **Glossary:** clarify unfamiliar terminology.

Example:

> “What should I do with Mika for Binah?”

- Look up Mika’s skills, damage type, armor type, and upgrade requirements in SchaleDB.
- Look up Mika’s Binah rating and raid notes in `stokesia/stokesia.json`.
- Look up Midokuni’s banner, farming, and student-thoughts records for investment and account-context advice.
- Use the glossary if the notes contain terms such as hypercarry, effectiveness buff, or reposition.

## Handling missing values

The JSON exports use a fixed schema. A field may be `null` because it does not apply or because the source has no entry.

Do not interpret null as:

- The student is bad.
- The student cannot perform the role.
- The item has no drops.
- The source explicitly recommends against it.

Check the source section, related records, and other datasets before drawing a conclusion.

## Handling disagreements

If sources appear to disagree, preserve the distinction:

- SchaleDB describes what exists in the game.
- Midokuni explains practical account and investment decisions.
- Stokesia describes curated raid performance.

For example, SchaleDB may show that a student has a particular skill effect, while Midokuni may still recommend low investment because the effect is rarely needed. This is not necessarily a contradiction.

## Freshness

The repository contains exported or manually maintained snapshots. Data may lag behind the live game because of:

- New students and equipment.
- Balance changes.
- New stages or raids.
- Event reruns.
- Translation changes.
- Different regional schedules.

For current banners, availability, or newly released content, verify the relevant server and current game state separately.

## Final-answer conventions

When answering from this repository:

- Use the narrowest relevant source first.
- Name the student, item, stage, raid, or internal ID used.
- Separate facts, calculations, and recommendations.
- Preserve variants and difficulty levels.
- Mention important assumptions.
- Use concise tables for lists and comparisons.
- Say when a value is missing, uncertain, or snapshot-dependent.
- Do not invent data that is absent from the repository.

The repository is designed as a layered reference:

```text
SchaleDB  →  what exists
Midokuni  →  what to do with it
Stokesia  →  how it performs in raids
Glossary  →  what the terminology means
```
