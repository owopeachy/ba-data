# SchaleDB data

This directory contains a manually maintained snapshot of objective Blue Archive game data from [SchaleDB](https://github.com/SchaleDB/SchaleDB).

It is separate from [`midokuni.json`](../midokuni.json):

- **SchaleDB files** contain objective game data such as IDs, stats, drops, stages, raids, items, and recipes.
- **`midokuni.json`** contains Midokuni’s curated opinions, recommendations, and reasoning.

## File map

| Data type | File |
| --- | --- |
| Students, stats, skills, IDs, and requirements | `students.json` |
| Raid bosses and mechanics | `raids.json` |
| Stages, rewards, and drop locations | `stages.json` |
| Items, materials, and uses | `items.json` |
| Crafting recipes and requirements | `crafting_global.json` |
| Equipment and gear | `equipment.json` |
| Furniture | `furniture.json` |
| Currency definitions | `currency.json` |
| Enemies | `enemies.json` |
| Summoned units | `summons.json` |
| Text and localized names | `localization.json` |

Prefer unminified JSON files for retrieval and inspection. Minified copies are only optimization artifacts.

## Retrieval guidance

- For student recommendations, consult the relevant student object in `../midokuni.json`.
- For objective student facts, use `students.json`.
- For drops and farming locations, use `stages.json` together with `items.json`.
- For crafting and item-counting questions, use `items.json` and `crafting_global.json`.
- For raid questions, use `raids.json`; consult stage and item data when rewards or farming are involved.
- When combining sources, clearly distinguish objective SchaleDB data from Midokuni’s curated analysis.
- Preserve SchaleDB field names and IDs when replacing files.
- Treat this directory as a dated snapshot. Record the snapshot date in the commit message whenever the data is refreshed.
- Missing, empty, and zero values are different; do not treat a missing field as zero.

## Source and freshness

The upstream SchaleDB repository is archived, so this folder may not include the latest game updates. Check the snapshot date before relying on time-sensitive data.

Upstream English data:

<https://github.com/SchaleDB/SchaleDB/tree/main/data/en>

GitHub API directory listing:

<https://api.github.com/repos/SchaleDB/SchaleDB/contents/data/en>
