# Blue Archive Data

This repository brings together three complementary Blue Archive data sources in a format suitable for machine-readable lookup and LLM-assisted questions. It does auto update from stokesia's sheet and midokuni's.

- **[Midokuni Student Insights](https://docs.google.com/spreadsheets/d/e/2PACX-1vSy6oQtuHdRctuG8RIiwpwHFe2iS6D08WHWxdWQo4eCYlbQBVaZ8DWwtsgfokZRZ4gDxDqz25-jDlQZ/pubhtml)** — curated advice on student roles, banners, farming, and investment.
- **[Stokkie’s Raid Rating](https://docs.google.com/spreadsheets/d/1VSzm_ioCt2AdRvkfL9HKNNZSbyslayVERXxVxR6nzh4/edit)** — community-maintained raid performance ratings and notes.
- **[SchaleDB](https://github.com/SchaleDB/SchaleDB)** — objective game data, including students, skills, items, stages, equipment, crafting, and raids.

The repository separates raw game data from curated recommendations:

- `schaledb/` contains the SchaleDB snapshot.
- `midokuni/` contains Midokuni’s exported student insights and glossary.
- `stokesia/` contains Stokesia/Causew’s raid-performance export.

For guidance on using these files in an automated or LLM workflow, see [AGENTS.md](AGENTS.md). Each source folder also contains a README describing its data and intended use (for the agents).

*Many thanks to the people who create, maintain, and publish these resources. <3 Their work made this possible, i'm just a filthy LLM user*

These are snapshots and are probably already outdated. i play with old units. Please visit the original sources above for the latest data, corrections, explanations, and update history.
